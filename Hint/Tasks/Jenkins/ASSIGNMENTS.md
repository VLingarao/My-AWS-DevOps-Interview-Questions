# Jenkins Exercises – Step-by-Step Learning Flow (Easy ➜ Hard)

---

## Exercise 1 – Jenkins Job Creation (Foundation Level)

### Phase 1: Basic Freestyle Jobs (Very Important)

1. **Setup a Jenkins Job with Apache Ant Build Tool**
   Source Code: [https://github.com/scmgalaxy/helloworld-java-ant](https://github.com/scmgalaxy/helloworld-java-ant)

2. **Setup a Jenkins Job with Apache Maven**
   Source Code: [https://github.com/scmgalaxy/helloworld-java-maven](https://github.com/scmgalaxy/helloworld-java-maven)

> Why first?
> These two cover **Java + Build Tool + Jenkins integration**, which is core CI knowledge.

---

### Phase 2: OS-Specific & Script-Based Jobs

3. **Setup a Jenkins Job with Batch Script (Windows)**
   Source Code: [https://github.com/scmgalaxy/teamcity-batch-helloworld](https://github.com/scmgalaxy/teamcity-batch-helloworld)

4. **Setup a Jenkins Job with NAnt**
   Source Code: [https://github.com/scmgalaxy/teamcity-nant-helloworld](https://github.com/scmgalaxy/teamcity-nant-helloworld)

5. **Setup a Jenkins Job with .NET Code Base**
   Source Code: [https://github.com/scmgalaxy/teamcity-dotnet-service](https://github.com/scmgalaxy/teamcity-dotnet-service)

> Why here?
> This introduces **Windows jobs, .NET builds, and cross-platform CI concepts**.

---

### Phase 3: Jenkins Pipeline (Must-Know – High Priority)

6. **Setup a Jenkins Build Pipeline with stages:**

   * Build
   * Test
   * Package
   * Deploy

   Source Code: [https://github.com/scmgalaxy/helloworld-java-maven](https://github.com/scmgalaxy/helloworld-java-maven)

> Pipelines are **mandatory for real-world DevOps roles**.

---

## Exercise 2 – Jenkins Nodes & Distributed Builds (Core CI Architecture)

### Phase 4: Jenkins Master–Agent Setup

7. **Add a Linux Node (Check SSH Slaves Plugin)**

8. **Add a Windows Node**

> These steps teach **distributed Jenkins architecture**.

---

### Phase 5: Node-Based Job Assignment (Very Important)

9. **Assign a Java-based Job to Linux Node and Build It**

10. **Assign an MSBuild-based Job to Windows Node and Build It**

> Rule (Very Important):
>
> * Environment variables
> * Tool locations (Java, Maven, MSBuild)
>   **Must be configured in Node settings**, not in Jenkins jobs.

---

## Exercise 3 – Jenkins CI/CD, Git, Triggers & Administration

### Phase 6: Git Integration & Triggers (Top Interview Questions)

11. **How can I make Jenkins CI with Git trigger on pushes to master?**

12. **How do I make Jenkins build on push to a Bitbucket Git repository?**

13. **Jenkins – How to build a specific branch**

14. **Jenkins Git Plugin: How to build a specific tag?**

15. **How to exclude a Git branch from building in Jenkins**

> These questions together cover **Git + Webhooks + Branch strategy**.

---

### Phase 7: Job Scheduling & Job Flow Control

16. **How to schedule jobs in Jenkins**

17. **How do I make a Jenkins job start after multiple simultaneous upstream jobs succeed?**

18. **How to conditionally build other projects?**

19. **Same workspace for multiple jobs**

20. **Jenkins – maximum number of concurrent jobs**

> Focus: **job dependency, chaining, concurrency control**.

---

### Phase 8: Job Management & Reusability

21. **How do I clone a job in Jenkins?**

22. **Export / Import jobs in Jenkins**

23. **Checkout multiple Git repositories into the same Jenkins workspace**

24. **Jenkins – passing variables between jobs**

25. **How to promote a specific build number from another job in Jenkins?**

---

### Phase 9: Build & Test Control (Critical for CI Quality)

26. **How do I make Jenkins build fail when Maven unit tests fail?**

27. **Execute Shell Script after post-build in Jenkins**

28. **Jenkins HTML in Job description**

---

### Phase 10: Jenkins Security & User Management (Very Important)

29. **Jenkins security – hide all screens unless user is logged in**

30. **Jenkins restrict view of jobs per user**

31. **Managing SSH keys within Jenkins for Git**

---

### Phase 11: Jenkins Administration & Maintenance

32. **How to move Jenkins from one PC to another?**

33. **How to start Jenkins on a different port rather than 8080 using Command Prompt (Windows)?**

34. **How to run Jenkins as a different user**

35. **How to shutdown Jenkins safely?**

36. **How to restart Jenkins manually?**

---

### Phase 12: Jenkins Configuration & Environment

37. **Jenkins / Hudson environment variables**

38. **How to reset build number in Jenkins?**

39. **How do I clear my Jenkins / Hudson build history?**

40. **Change Jenkins default view**

---

### Phase 13: Plugin & System-Level Operations

41. **How to install a plugin in Jenkins manually?**

42. **How to get a list of installed Jenkins plugins with name and version pair?**

---

---
---
#  Jenkins Exercises – Step-by-Step Learning Flow (Easy ➜ Hard) - Solutions
---
---


