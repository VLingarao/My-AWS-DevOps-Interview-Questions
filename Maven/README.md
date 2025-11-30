---

# ✅ **Complete Guide: How to Practice Maven Goals on EC2 Using Your Project**

## **1️⃣ Launch EC2 Instance**

Use **Amazon Linux 2023** or **Ubuntu 22.04**.

Recommended:

* **t2.micro** (Free tier)
* Security group: Allow SSH (22)

Connect via SSH:

```bash
ssh -i your-key.pem ec2-user@<EC2-Public-IP>
```

---

# **2️⃣ Install Java (JDK 17 or 11)**

### **Amazon Linux 2023**

```bash
sudo dnf install java-17-amazon-corretto -y
```

### **Verify JAVA**

```bash
java -version
```

---

# **3️⃣ Install Maven**

### **Amazon Linux 2023**

```bash
sudo dnf install maven -y
```

### **Check Maven**

```bash
mvn -version
```

---

# **4️⃣ Clone Your Maven Project**

Clone your GitHub repo:

```bash
git clone https://github.com/VLingarao/maven-project.git
cd maven-project
```

---

# **5️⃣ Practice Most Important Maven Goals**

Below are all goals you can practice + purpose + example.

---

# 🔥 **MAVEN GOALS FOR PRACTICE**

---

## **1️⃣ mvn validate**

Validates project structure, checks POM file.

```bash
mvn validate
```

---

## **2️⃣ mvn compile**

Compiles source code into `/target/classes`.

```bash
mvn compile
```

---

## **3️⃣ mvn package**

Creates `.jar` or `.war` file inside **target/** folder.

```bash
mvn package
```

After this:

```bash
ls target
```

You will see:

```
maven-project-1.0-SNAPSHOT.jar
```

---

## **4️⃣ mvn test**

Runs unit test cases.

```bash
mvn test
```

---

## **5️⃣ mvn clean**

Deletes target folder.

```bash
mvn clean
```

---

## **6️⃣ mvn clean install**

Cleans old build + compiles + tests + packages + installs JAR to local repository (`~/.m2`)

```bash
mvn clean install
```

---

## **7️⃣ mvn clean package -DskipTests**

Build faster by skipping tests.

```bash
mvn clean package -DskipTests
```

---

## **8️⃣ mvn dependency:tree**

Shows dependency hierarchy.

```bash
mvn dependency:tree
```

---

## **9️⃣ mvn verify**

Executes integration tests + verifies project.

```bash
mvn verify
```

---

## **🔟 mvn site**

Generates HTML documentation for project.

```bash
mvn site
```

Output → **target/site/index.html**

---

# 🎯 **Extra Useful Goals for Interviews**

---

## **mvn dependency:resolve**

Downloads dependencies.

```bash
mvn dependency:resolve
```

---

## **mvn archetype:generate**

Create new Maven project from template.

```bash
mvn archetype:generate
```

---

# ⭐ BONUS: Run your Java JAR on EC2

After building:

```bash
cd target
java -jar maven-project-1.0-SNAPSHOT.jar
```

If your project prints output, you will see it here.

---

# 🏁 Final Flow for Daily Practice

```bash
git clone <repo>
cd maven-project

mvn validate
mvn compile
mvn test
mvn package
mvn clean
mvn clean install
mvn dependency:tree
```

---
