# Use

The syntax for running Maven:
```bash
mvn [options] [goal] [phase]
```

It has 3 built-in lifecycles and their phases:
- clean - pre-clean, clean, post-clean

- default - validate, initialize, generate-sources, process-sources, generate-resources, process-resources, compile, process-classes, generate-test-sources, process-test-sources, generate-test-resources, process-test-resources, test-compile, process-test-classes, test, prepare-package, package, pre-integration-test, integration-test, post-integration-test, verify, install, deploy

- site - pre-site, site, post-site, site-deploy


The typical invocation for building a Maven project:
```bash
mvn package
```

Just creating the package and installing it in the local repository for re-use from other projects can be done with
```bash
mvn verify
```
