# 🚀 **MAVEN GOALS PRACTICE — FULL STEP-BY-STEP GUIDE**

## ✅ **Step 1: Install Java & Maven (Local System)**

1️⃣ Amazon Linux 2023
```bash
sudo dnf install java-17-amazon-corretto -y
```

2️⃣ Install Maven
```bash
sudo dnf install maven -y
```
3️⃣ Install Git
```bash
sudo dnf install git -y
```

Check Maven
```bash
mvn -version
```

Check Java:
```bash
java -version
```

Check Git:
```bash
git -version
```

## ✅ **Step 2: Clone Your Maven Project**

```bash
git clone https://github.com/VLingarao/maven-project.git
cd maven-project
```

---

# ⭐ **Now Practice Maven Goals One by One**

---

# 1️⃣ `mvn validate`

Checks whether your `pom.xml` is correct.

```bash
mvn validate
```

---

# 2️⃣ `mvn compile`

Compiles your Java code → output in `target/classes/`

```bash
mvn compile
```

---

# 3️⃣ `mvn test`

Runs unit test cases inside `src/test/java`

```bash
mvn test
```

---

# 4️⃣ `mvn package`

Packages your project → JAR or WAR in `/target/`

```bash
mvn package
```

Check output:

```bash
ls target
```

---

# 5️⃣ `mvn clean`

Deletes the entire `target/` directory.

```bash
mvn clean
```

---

# 6️⃣ `mvn clean package`

Clean → compile → test → package

```bash
mvn clean package
```

---

# 7️⃣ `mvn clean install`

Clean → compile → test → package → install in local repo `~/.m2`

```bash
mvn clean install
```

---

# 8️⃣ Skip Tests (Faster Build)

```bash
mvn clean package -DskipTests
```

---

# 9️⃣ Show Dependency Tree

```bash
mvn dependency:tree
```

---

# 🔟 Download All Dependencies

```bash
mvn dependency:resolve
```

---

# 1️⃣1️⃣ Verify Lifecycle

Runs all steps + integration tests.

```bash
mvn verify
```

---

# 1️⃣2️⃣ Generate Documentation (HTML Reports)

```bash
mvn site
```

Output:

```
target/site/index.html
```

---

# ⭐ **Bonus: Run Your Built JAR**

After packaging:

```bash
cd target
java -jar maven-project-1.0-SNAPSHOT.jar
```

---

# 🏁 **Daily Practice Flow (Best Sequence)**

```bash
mvn clean
mvn validate
mvn compile
mvn test
mvn package
mvn clean install
mvn dependency:tree
```

---
