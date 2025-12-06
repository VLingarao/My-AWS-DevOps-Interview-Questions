# 🚀 **MAVEN GOALS PRACTICE — FULL STEP-BY-STEP GUIDE**  ✅ **Top Maven Interview Questions & Answers (Most Asked)**

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

---

# ✅ **Top Maven Interview Questions & Answers (Most Asked)**

---

## **1. What is Maven?**

**Answer:**
Maven is a **build automation and project management tool** for Java projects. It handles **dependency management**, **builds**, **testing**, **packaging**, and **deployment**.

---

## **2. What is a POM file?**

**Answer:**
POM (**Project Object Model**) is the **heart of Maven**, stored as `pom.xml`. It contains:

* Project details
* Dependencies
* Plugins
* Build configurations
* Repositories

---

## **3. What is a Maven dependency?**

**Answer:**
A dependency is an external library your project needs.
It is defined inside the `<dependencies>` section of the POM file.

---

## **4. What is a Maven repository? Types?**

**Answer:**
A repository is a location where Maven stores JAR files.

### **Types:**

1. **Local Repository** – Stored on your machine (`~/.m2/repository`)
2. **Central Repository** – Default online repository
3. **Remote Repository** – Third-party or company provided repos (Nexus/Artifactory)

---

## **5. What is the Maven lifecycle?**

**Answer:**

### **Main lifecycles:**

* **validate** – Checks if project is correct
* **compile** – Compiles source code
* **test** – Runs unit tests
* **package** – Creates JAR/WAR
* **verify** – Checks integration tests
* **install** – Adds package to local repo
* **deploy** – Deploys to remote repo

---

## **6. What is the difference between `mvn install` and `mvn package`?**

**Answer:**

| Command         | Purpose                                               |
| --------------- | ----------------------------------------------------- |
| **mvn package** | Creates JAR/WAR file                                  |
| **mvn install** | Creates package + installs it into **local .m2 repo** |

---

## **7. What is the purpose of the Maven `clean` command?**

**Answer:**
`mvn clean` removes the `target/` folder to ensure a **fresh build**.

---

## **8. What are Maven plugins?**

**Answer:**
Plugins provide additional features to build, test, package, deploy, and run tasks.
Example: **Compiler plugin, Surefire plugin, Shade plugin**.

---

## **9. What is dependency scope in Maven?**

**Answer:**
Determines **where** and **when** a dependency is available.

### Common scopes:

* **compile** (default)
* **provided**
* **runtime**
* **test**
* **system**

---

## **10. What is transitive dependency?**

**Answer:**
When a dependency **brings its own dependencies**, Maven downloads them automatically.

Example: Adding Spring Boot downloads multiple sub-dependencies.

---

## **11. What is Maven’s `settings.xml`?**

**Answer:**
A configuration file (inside `~/.m2/`) used for:

* Credentials
* Proxies
* Custom repositories
* Mirror settings

---

## **12. How do you skip tests in Maven?**

**Answer:**

```
mvn install -DskipTests
```

Or inside POM:

```xml
<skipTests>true</skipTests>
```

---

## **13. What is the use of `mvn dependency:tree`?**

**Answer:**
Shows **full dependency hierarchy** (helps detect version conflicts).

---

## **14. What is the difference between Snapshot and Release version?**

**Answer:**

| Type         | Description                       |
| ------------ | --------------------------------- |
| **SNAPSHOT** | Development version, auto-updates |
| **RELEASE**  | Stable version, no auto updates   |

Example:
`1.0-SNAPSHOT` → development
`1.0` → release

---

## **15. How do you force Maven to update dependencies?**

**Answer:**

```
mvn clean install -U
```

This forces Maven to download the latest snapshot versions.

---

## **16. What is the Maven Wrapper (mvnw)?**

**Answer:**
Allows a project to run Maven **without installing it** globally.

Used for CI/CD pipelines.

---

## **17. What is the effective POM?**

**Answer:**
The **final POM** after combining:

* User POM
* Super POM
* Default settings

Command:

```
mvn help:effective-pom
```

---

## **18. What is the default directory structure in Maven?**

```
src/main/java
src/main/resources
src/test/java
src/test/resources
target/
```

---

## **19. How to specify Java version in Maven?**

```xml
<properties>
  <maven.compiler.source>17</maven.compiler.source>
  <maven.compiler.target>17</maven.compiler.target>
</properties>
```

---

## **20. What is the role of Maven Surefire plugin?**

**Answer:**
Responsible for running **unit tests** during the test phase.

---
