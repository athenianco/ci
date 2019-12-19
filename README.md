# ci
Contains common CI/CD configuration for Athenian projects.

## Usage
### Environment variables that should be set
```shell script
# google-related credentials
GOOGLE_DOCKER_IMAGE
GOOGLE_CREDENTIALS
GOOGLE_PROJECT
GOOGLE_PUBSUB_TOPIC
# k8s-related entity names
K8S_DEPLOYMENT
K8S_NAMESPACE
# credentials required in CI
CODECOV_TOKEN
```

### Including in your Makefile
```shell script
PROJECT = your-project
COMMANDS ?= # or cmd/your-command

CI_REPOSITORY ?= https://github.com/athenianco/ci
CI_BRANCH ?= master
CI_PATH ?= .ci
MAKEFILE := $(CI_PATH)/Makefile.main
$(MAKEFILE):
	git clone --quiet --depth 1 -b $(CI_BRANCH) $(CI_REPOSITORY) $(CI_PATH);
-include $(MAKEFILE)
```
