# Jenkins Hands-On Tasks 
## Jenkins On CMD = java -jar C//jenkins.war file path
## Task 1 – Jenkins Foundation & Tooling (Baseline Skill)

**Objective:** Prove you understand Jenkins + build tools.

**Hands-on**

* Install Jenkins
* Configure **Global Tool Configuration**

  * JDK
  * Maven
  * Ant
* Verify tools using:

  ```
  java -version
  mvn -version
  ant -version
  ```

**Deliverable**

* Jenkins dashboard accessible
* Tools visible under **Manage Jenkins → Global Tool Configuration**

---

## Task 2 – Freestyle Job with Apache Ant

**Project:** `helloworld-java-ant`

**Hands-on**

* Create Freestyle Job
* Git checkout
* Build using Ant
* Generate `.jar`

**Validation**

* Console output shows `BUILD SUCCESS`
* JAR exists in workspace

**Key Concepts**

* SCM integration
* Build lifecycle
* Workspace usage

---

## Task 3 – Freestyle Job with Maven (Critical)

**Project:** `helloworld-java-maven`

**Hands-on**

* Configure Maven job
* Run:

  ```
  mvn clean package
  ```
* Archive artifacts

**Validation**

* `target/*.jar` archived
* Unit tests executed

**Interview Mapping**

* “How does Jenkins work with Maven?”
* “What happens if tests fail?”

---

## Task 4 – Windows-Specific Job (Batch Script)

**Project:** `teamcity-batch-helloworld`

**Hands-on**

* Create Windows Freestyle Job
* Execute `.bat` script
* Handle Windows path variables

**Key Learning**

* OS-specific Jenkins jobs
* Batch scripting in CI


---

## Task 5 – Jenkins Pipeline (Declarative) – MUST

**Project:** `helloworld-java-maven`

**Hands-on**

* Convert Freestyle → Pipeline
* Create stages:

  * Checkout
  * Build
  * Test
  * Package
  * Deploy (dummy)

**Deliverable**

```groovy
pipeline {
  agent any
  stages {
    stage('Build') { ... }
    stage('Test') { ... }
    stage('Package') { ... }
    stage('Deploy') { ... }
  }
}
```

---

## Task 6 – Jenkinsfile from Git (Production Standard)

**Hands-on**

* Move pipeline code into `Jenkinsfile`
* Use SCM pipeline
* Trigger build from repo

**Key Concepts**

* Pipeline as Code
* Version control for CI/CD

---

## Task 7 – Jenkins Master–Agent Architecture

**Hands-on**

* Configure:

  * 1 Linux agent (SSH)
  * 1 Windows agent
* Verify labels

**Validation**

* Jobs run on correct nodes

**Interview Question Covered**

* “Explain Jenkins Master & Agent”

---

## Task 8 – Node-Specific Builds (Advanced)

**Hands-on**

* Java job → Linux node
* Batch/MSBuild job → Windows node
* Configure tools at node level

**Key Rule (Interview Favorite)**

> Tools must be configured at node level, not job level

---

## Task 9 – Git Webhook Integration (Real CI)

**Hands-on**

* Configure GitHub webhook
* Trigger build on push to `main`
* Validate payload delivery

**Validation**

* Jenkins auto-builds on commit

---

## Task 10 – Branch & Tag-Based Builds

**Hands-on**

* Build only:

  * `main` branch
  * Release tags (`v*`)
* Exclude feature branches

**Concepts**

* Branch strategies
* Release pipelines

---

## Task 11 – Job Chaining & Dependencies

**Hands-on**

* Job A → Job B → Job C
* Build only if upstream succeeds
* Parallel execution where applicable

**Concepts**

* Upstream/downstream
* Fan-in / fan-out

---

## Task 12 – Parameters & Environment Control

**Hands-on**

* Parameterized build:

  * ENV = dev / qa / prod
* Pass parameters between jobs

**Validation**

* Same pipeline behaves differently per ENV

---

## Task 13 – Credentials & Security (Very Important)

**Hands-on**

* Store:

  * Git credentials
  * SSH keys
* Use credentials in pipeline
* Mask secrets in logs

**Interview Mapping**

* “How does Jenkins handle secrets?”

---

## Task 14 – Jenkins Security & RBAC

**Hands-on**

* Enable authentication
* Create users
* Restrict job access by role
* Disable anonymous access

**Concepts**

* Least privilege
* Enterprise Jenkins setup

---

## Task 15 – Jenkins Backup, Restore & Maintenance

**Hands-on**

* Backup `$JENKINS_HOME`
* Restore Jenkins on another machine
* Restart, shutdown safely
* Change port from 8080

**Final Outcome**

* You understand Jenkins as an **admin + DevOps engineer**

---
