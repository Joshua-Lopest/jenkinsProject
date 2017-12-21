# Spring PetClinic Sample Application 

This is a mirror of Spring's PetClinic repository, used for continuous integration by using Jenkins with a few plugins for static analysis and code coverage.
The modified/added files are:
	pom.xml, with the plugin configuration to work with jenkins;
	findbugs.xml, with findbugs rules;
	checkstyle.xml, with checkstyle rules;
	pmd.xml, with PMD rules;
	Jenkinsfile, with the pipeline code to be run inside the job.
Note that Maven and JDK must be configured and the plugins must be enabled in Jenkins, in order to be possible to get the results.