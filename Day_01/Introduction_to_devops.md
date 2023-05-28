# `Devops` :-
- Made up of two generic tasks ie. `development` + `operations`.
- In simple words it means `CODE TO PROD`. means from coding to production and folllowing best practices.
- `development` : writing code.
- `operations`  : build, test, security analysis, deploy, manage/monitor.

## `CI/CD` :-
- ***`CI`*** : Continious Integration.
    - `Continuous Integration (CI) is a software development practice that involves frequently integrating code changes from multiple developers into a shared repository. The goal of CI is to catch and address integration issues early in the development cycle`.
    - `multiple changes done by multiple developers that can be integrated into the shared repository without effecting the live application or production environment`.
    - Developers make seperate branches in the repository for specific features like {feature-1, feature-2, feature-3, etc.}. They make their changes in and commit it into respective branch.
    build their code with that branch(by running PIPELINE with that branch), deploy(in temporary server) and test it in different environments without effecting the `main` branch of repository.
    - all the seperate feature branch can be deployed and tested at the same time w/o effecting the main branch.
    - This whole process of continious change in specific feature branches w/o effecting the main branch is called continious integration.

    #### Process invlved in CI :-
    1. `Version Control` : 
        - Developers work on their local copies of the code and use a version control system (such as Git) to manage the codebase. They commit their changes to a shared repository(specific feature branch), typically hosted on a platform like GitHub or Bitbucket.

    2. `Automated Build` : 
        - Whenever changes are committed to the repository, a build process is triggered automatically. The build process involves compiling the code, resolving dependencies, and generating executable files or artifacts. This process ensures that the codebase is always in a buildable state.
        <details>
        <summary> Artifacts </summary>
        
        - In the context of Continuous Integration (CI), an artifact refers to a deliverable that is generated as a result of the build and testing process. 
        - It is a tangible output produced by the CI system, which can be used for various purposes such as deployment, testing, or release.
        - Here are a few examples of artifacts commonly generated in CI :
            1. `Compiled Executables` : For projects written in languages like Java, C#, or C++, the artifact may be the compiled executable files, such as JAR files, DLLs, or binaries. These artifacts can be deployed to different environments for testing or deployment purposes.

            2. `Deployment Packages` : In web development or application deployment scenarios, the artifact can be a package or archive containing the necessary files and resources to deploy the software. It could include HTML, CSS, JavaScript files, configuration files, and any other required assets.

            3. `Libraries or Modules` : In modular or library-based projects, the artifact may be a compiled library or module that can be imported or integrated into other projects. These artifacts are typically published to a repository or package manager for easy consumption by other developers.

            4. `Docker Images` : In containerized environments, the artifact can be a Docker image. This image encapsulates the application code, dependencies, and runtime environment, allowing for consistent deployment and easy scaling across different environments.

            5. `Test Reports` : Test reports generated during the CI process can also be considered artifacts. These reports provide detailed information about the test results, including passed and failed tests, code coverage metrics, and other relevant data. They help identify issues and track the progress of the software's quality.

            6. `Documentation` : In some cases, the artifact may include documentation files, such as API documentation, user guides, or release notes. These documents provide important information about the software and its usage, facilitating collaboration and understanding for developers and end-users.
        - The specific artifacts generated in a CI process depend on the project type, programming languages, and the desired outcome. CI tools typically provide options to configure the artifacts to be generated and specify where they should be stored or deployed. 
        - These artifacts are then made available to other stages of the software development lifecycle, such as deployment pipelines or release management processes.
        </details>

    3. `Testing` : 
        - After the build process, automated tests are executed. These tests include `unit tests`, `integration tests`, and other types of tests relevant to the project. The tests verify that the code changes haven't introduced any regressions or bugs and that the overall functionality of the software is maintained.

    4. `Code Analysis` : 
        - Static code analysis tools may be used to analyze the codebase for potential issues, such as `coding style violations`, `code complexity`, or `potential bugs`. The results of the code analysis are typically reported back to the development team.

    5. `Reporting` : 
        - The results of the build, tests, and code analysis are consolidated and made available to the development team. This includes information about the status of the build (success or failure), test results (pass or fail), and any code quality issues that were identified.

    6. `Feedback and Collaboration` : 
        - If any issues are identified during the CI process, the development team is notified, and appropriate actions can be taken to fix the problems. Developers collaborate to address the issues and make the necessary code changes. This iterative feedback loop helps ensure that code quality remains high.

    7. `Deployment` : 
        - In some cases, a CI process can include automated deployment steps, where the tested and validated code changes are automatically deployed to a staging environment or even to production. This allows for rapid and frequent deployment of new features or bug fixes.

    8. `Continuous Integration Server` : 
        - To facilitate the CI process, a dedicated CI server or service is often used. Examples include Jenkins, Travis CI, CircleCI, or GitLab CI/CD. These tools automate the build, testing, and reporting steps, making the continuous integration process smoother and more efficient.

- ***`CD`*** : Continious Deployment.
    - Different Server Environments;
        1. `dev`    : development environment.
        2. `QA`     : Testing/QA-testing environment. (quality assurance) (including unit tests, integration tests, and end-to-end tests)
        3. `PPD`    : Pre-Production environment/Staging environment. (pre release) (performance testing, user acceptance testing (UAT), and other pre-production checks.)
        4. `Prod`   : Production environment.
        5. `DR`     : Disaster Recovery environment.

    - `Continuous Deployment (CD) is a software development practice that extends Continuous Integration (CI) by automatically deploying code changes to production or customer-facing environments. The goal of CD is to enable frequent and reliable releases of software`. 

    #### The process of continuous deployment (CD) typically involves the following steps:

    1. `Version Control` : 
        - Developers work on their local copies of the code and use a version control system (such as Git) to manage the codebase. They commit their changes to a shared repository, typically hosted on a platform like GitHub or Bitbucket.

    2. `Continuous Integration (CI)` : 
        - The CI process is triggered whenever changes are committed to the repository. It involves building the code, running automated tests, and analyzing the code quality, as explained in the earlier response on continuous integration.

    3. `Artifact Generation` : 
        - After the successful completion of the CI process, the build generates artifacts. These artifacts can be compiled executables, deployment packages, Docker images, or any other deliverable format that can be deployed to a server environment.

    4. `Environment Promotion` : 
        - In the CD pipeline, the artifacts are deployed to different environments, starting from development, testing, staging, and ultimately to the production environment. The promotion of artifacts across environments is typically automated, ensuring consistency and eliminating manual errors.

    5. `Testing in Each Environment` : 
        - Automated tests are executed in each environment to ensure the stability and functionality of the software. These tests include integration tests, performance tests, security tests, and any other relevant tests specific to the environment. If any issues are identified, the deployment process may be halted, and the team is notified to address the problem.

    6. `Approval Process` : 
        - In some cases, a manual approval process may be introduced before promoting the artifacts to the next environment or deploying to production. This approval step involves stakeholders or designated approvers who review the changes and ensure that they meet the necessary criteria for the deployment.

    7. `Rollback Mechanism` : 
        - It is essential to have a rollback mechanism in place to revert to a previous known good state in case of any issues or unforeseen problems in the deployed software. This ensures that the application can quickly recover in case of failures without causing significant downtime or disruption to end-users.

    8. `Continuous Monitoring` : 
        - After deployment, continuous monitoring tools are used to track the health and performance of the software in the production environment. This includes monitoring metrics such as response time, error rates, resource utilization, and user feedback. Monitoring helps identify and address issues promptly, improving the reliability and quality of the software.

    9. `Iterative Improvement` : 
        - The CD process is continuously improved by gathering feedback, analyzing metrics, and incorporating lessons learned from each deployment. This iterative approach helps refine the process, increase automation, and minimize the risk of deployment failures.
    
    - It's important to note that the exact CD process can vary based on the organization, project requirements, and technology stack. Some teams may choose to automate deployments to specific environments only, while others may automate the entire pipeline up to production. 
    - The primary focus is to achieve frequent and reliable releases while maintaining the necessary control and quality assurance measures.

## Characteristics of using Devops model :-
1. Time saved.
2. Early bug detection.
3. Increased collaboration (between and among operations and devlopment team members or in some cases other aprties involved).
4. Improved quality.
5. Agility(move quickly and easily) and flexibility.
