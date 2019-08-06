DevOps is a set of practices that automates the processes between software development and IT teams, in order to build, test and release the software faster and more reliably. It describes approaches to speed up the processes by which an idea goes from development to deployment in a production environment to provide value to the user. 

 

**Origin of DevOps** 

DevOps is primarily used to integrate all the processes into a single and automated workflow for a rapid delivery of high-quality software to meet the user requirements. The various benefits of DevOps would include:

·      Faster delivery of updated features to the market

·      Resilient deployment models

·      Time-efficient innovation methodologies 

·      Less operational expenditures

 

Over the period of time the developers and operations have been considered as individual entities. However, over the period of time with the shift from waterfall to agile, DevOps creates a new dynamic that changes the capabilities. 

 ![image-20190806141919142](/Users/sparvez/Library/Application Support/typora-user-images/image-20190806141919142.png)

**DevOps Model**

**·      Plan and Identify Phase:** For any project we need to define the work goal along with the functionalities. This further involves changes and evolutions along with continuous feedback. Various tools used in this phase are Jira, Git, SVN, TFS

**·      Development Phase:** The project building involves writing code, designing infrastructure, automating processes and defining tests. All the mechanisms that are related to the building of the system and can possibly create developmental errors. Various tools used here are Maven, Packer, Ruby Rake , etc.

**·      Testing Phase:** Software testing involves checking the package and source code before it reaches the production environment. This involves creating the test cases, distributing the test load to multiple nodes and continuous testing. Various tools used are JUnit, Selenium, Cucumber etc.

**·      Deployment Phase:** The release management includes deploying the packages and configuration files which are required for release to be deployed to production server. The configuration involves all the platform infrastructure to be configured and managed using DevOps tools. Various tools used here are Ansible, Chef, Puppet etc.

**·      Management Phase:** Finally, the application performance, infrastructure, database and other services are required to be monitored. This would further involve capturing the metrics and reporting it back to the DevOps environment. The tools used for this stage include Splunk, Elastic Stack etc.

**·      Integration Phase:** Once all the build has been completed, all the codes and other components are required to be integrated and coordinated together to detect the errors quickly and locating them in an efficient way. Tools used such as Jenkins etc.

 

The main idea of DevOps is to shorten development cycles, increase deployment frequency and meet business needs by integrating the development and operations teams in order to enable rapid software delivery. A major outcome of implementing DevOps is a continuous integration and continuous deployment pipeline (CI/CD). CI/CD helps deliver apps to customers frequently and validate software quality with minimal intervention. It introduces ongoing automation and continuous monitoring throughout the lifecycle of apps, from integration and testing to delivery and deployment. 

 

This can be done several times of any given day.  After the changes have been submitted and merged together, they are validated by conducting various unit an integration tests and automated testing to ensure the smooth working of the application. If the correct procedures are followed, it allows the developers to perform the builds iteratively and more frequently and immediate rectifications of bugs , etc., if any. 

**Continuous Delivery (CD):** Focuses on automating the software delivery process to allow for better deployments to production at any time. This allows for building a production-grade release without any coordination or additional testing. A pipeline is configured which works as an automated system to execute a progressive set of test suites according to the build. In case of any failure, appropriate rectifications are made to allow for creating an end result that is deployable and verifiable in the prod environment.

 **Continuous testing:** This involves synchronization of Testing/QA with the processes defined to ensure the best user experience. It uses tools like Selenium to test the functionality of the code. Other than this it uses tools like GitHub or other internal repositories to store tests and version together with the code. 

**Continuous Deployment:** Finally, a well-designed test automation is put in place after the release of a production-ready build to a repository after which the continuous deployment automates the release of the app to production. This allows for quicker responses from the users and to release changes to apps in smaller chunks.

**Pipeline-as-code**

Pipeline refers to a set of plugins configured together to support the implementation and integration of continuous delivery to any automation tool such as Jenkins. It defines the complete build process up to the testing and delivery, in a repeatable manner through multiple stages. By improvising and modeling these tasks, the advantages of the pipeline-as-code are:

1. Allows for integration with other plugins and custom extensions to Domain-specific-langiage
2. Implementation in code and checking into source control, allowing for parallel modifications and iterations to the delivery pipeline
3. Allows for the ability to join/loop/fork and perform the work in parallel



An example of a pipeline

pipeline { 
    agent any 
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Build') { 
            steps { 
                sh 'make' 
            }
        }
        stage('Test'){
            steps {
                sh 'make check'
                junit 'reports/**/*.xml' 
            }
        }
        stage('Deploy') {
            steps {
                sh 'make publish'
            }
        }
    }
}



 

 