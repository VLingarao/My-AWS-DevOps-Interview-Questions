# ✅ **Top SonarQube Interview Questions & Answers (Most Asked)**

---

## **1. What is SonarQube?**

**Answer:**
SonarQube is a **code quality and security scanning platform** that performs **static code analysis** to detect:

* Bugs
* Code smells
* Security vulnerabilities
* Duplications
* Technical debt

---

## **2. What is a Quality Gate in SonarQube?**

**Answer:**
A **Quality Gate** is a set of **conditions** that must be met for the code to be considered *clean*.

Example checks:

* Code coverage > 80%
* No critical vulnerabilities
* Duplications < 3%

If conditions fail → **Quality Gate = Failed**.

---

## **3. What are SonarQube scanners?**

**Answer:**
Tools used by SonarQube to analyze code.

Examples:

* Sonar Scanner CLI
* Jenkins Sonar Scanner plugin
* Maven Scanner (`sonar:sonar`)
* Gradle Scanner
* SonarScanner for .NET

---

## **4. What languages does SonarQube support?**

**Answer:**
Over **25+ languages**, including Java, JavaScript, Python, C#, C/C++, Go, Kotlin, PHP, TypeScript, Terraform, Kubernetes YAML, etc.

---

## **5. What is a SonarQube project?**

**Answer:**
A project in SonarQube represents a **codebase** that is scanned and monitored for quality and security.

---

## **6. How do you integrate SonarQube with Jenkins?**

**Answer:**
Steps:

1. Install **SonarQube plugin** in Jenkins
2. Add **SonarQube server** in Jenkins global config
3. Install **Sonar Scanner** in Jenkins
4. Add the scanner stage in your Jenkins Pipeline:

```groovy
stage('SonarQube Analysis') {
  steps {
    sonarQubeScanner(
      installationName: 'MySonarServer',
      additionalArguments: '-Dsonar.projectKey=sample -Dsonar.sources=src'
    )
  }
}
```

---

## **7. What are the components of SonarQube architecture?**

**Answer:**

* **SonarQube Server** (web UI + compute engine)
* **Database** (PostgreSQL, MySQL older versions)
* **Scanner** (runs on CI/CD or locally)
* **Plugins** (language + security plugins)

---

## **8. What databases does SonarQube support?**

**Answer:**
Only **PostgreSQL** (latest versions).

---

## **9. What is SonarLint?**

**Answer:**
SonarLint is an IDE plugin that gives **real-time code quality feedback** in:

* VS Code
* IntelliJ
* Eclipse

It detects issues *before* committing code.

---

## **10. What is Leak Period (New Code)?**

**Answer:**
Leak period defines the time window for analyzing **newly added or modified code**.

New code must pass:

* No new bugs
* No new vulnerabilities
* No new code smells
* Required coverage

---

## **11. What is Technical Debt?**

**Answer:**
Time required to fix all code issues (bugs, smells, duplications).
Shown in **hours or days**.

---

## **12. What is Code Smell?**

**Answer:**
A maintainability issue in the code (not a bug or security issue).
Example: Long methods, unused variables.

---

## **13. How does SonarQube calculate Code Coverage?**

**Answer:**
Using test reports from tools like:

* JUnit
* Jacoco
* Jest
* pytest

Coverage =
**Lines covered by tests / total lines of code**

---

## **14. What is Duplication in SonarQube?**

**Answer:**
Portions of code copied/pasted in multiple places.
High duplication increases maintenance cost.

---

## **15. What is the difference between SonarQube and SonarCloud?**

| Feature   | SonarQube       | SonarCloud             |
| --------- | --------------- | ---------------------- |
| Type      | Self-hosted     | SaaS (cloud)           |
| Cost      | Free/Enterprise | Paid                   |
| Setup     | Manual          | No setup               |
| Ideal for | Private repos   | Public + Private repos |

---

## **16. How do you run SonarQube scan using Maven?**

Command:

```
mvn clean verify sonar:sonar \
 -Dsonar.projectKey=my-app \
 -Dsonar.host.url=http://localhost:9000 \
 -Dsonar.login=<token>
```

---

## **17. How do you generate a token in SonarQube?**

**Steps:**

* Login
* Go to **My Account → Security**
* Generate **User Token**

Used in Jenkins, Maven, and CI/CD.

---

## **18. What are SonarQube rules?**

**Answer:**
Rules are built-in checks that detect:

* Bugs
* Security hotspots
* Smells

Every language has its own rule set.

---

## **19. What is a Security Hotspot?**

**Answer:**
Code that **might** be risky — needs manual review.
Example: Hardcoded credentials.

---

## **20. What are the main metrics SonarQube measures?**

* Bugs
* Vulnerabilities
* Code smells
* Coverage
* Duplications
* Security hotspots
* Maintainability
* Reliability
* Security rating
* Technical debt

---

Just say: **"Yes, create PDF"**
