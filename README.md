# ci
Contains common CI/CD configuration for Athenian projects.

## Usage
### Environment variables that should be set
```shell script
GOOGLE_DOCKER_IMAGE
GOOGLE_CREDENTIALS
GOOGLE_PROJECT
GOOGLE_PUBSUB_TOPIC
K8S_DEPLOYMENT
K8S_NAMESPACE
```

### Including in your Makefile
```shell script
CI_REPOSITORY ?= https://github.com/athenianco/ci
CI_BRANCH ?= master
CI_PATH ?= .ci
MAKEFILE := $(CI_PATH)/Makefile.main
$(MAKEFILE):
	git clone --quiet --depth 1 -b $(CI_BRANCH) $(CI_REPOSITORY) $(CI_PATH);
-include $(MAKEFILE)
```
