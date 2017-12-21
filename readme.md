# Spring PetClinic Sample Application 

This is a mirror of Spring's PetClinic project. It has been used for learning continuous integration by using Jenkins with a few plugins for static analysis and code coverage.
The modified/added files are:
* pom.xml, with the configuration for each to work with jenkins;
* findbugs-rules.xml, with findbugs rules;
* checkstyle-rules.xml, with checkstyle rules;
* pmd-rules.xml, with PMD rules;
* Jenkinsfile, with the pipeline script to be run inside the job.
Note that Maven and JDK must be configured and the plugins must be enabled in Jenkins, in order to get the results.