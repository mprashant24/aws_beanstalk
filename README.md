# Contrast agent deployment in AWS Beanstalk - Java

This repo is example to deploy the Contrast agent using AWS beanstalk .ebextensions configuration files. It uses .ebextensions to download the latest agent and create the common agent configuration yaml file in /opt/contrast folder.

## Prerequisites

The following items should be installed in your system:

eb cli

## Creating environment with Contrast variables

```shell
eb create <environment name> --envvars CONTRAST__API__URL=https://app.contrastsecurity.com/Contrast,CONTRAST__API__API_KEY=<value>,CONTRAST__API__SERVICE_KEY=<value>,CONTRAST__API__USER_NAME=<value>,CONTRAST__SERVER__NAME=<value>,CONTRAST__SERVER__ENVIRONMENT=<value>,JAVA_TOOL_OPTIONS="-javaagent:/opt/contrast/contrast.jar -Dcontrast.config.path=/var/contrast/contrast_security.yaml"
```

## Adding Contrast variable to existing environment

```shell
eb setenv eb setenv CONTRAST__API__URL=https://app.contrastsecurity.com/Contrast CONTRAST__API__API_KEY=<value> CONTRAST__API__SERVICE_KEY=<value> CONTRAST__API__USER_NAME=<value> CONTRAST__SERVER__NAME=<value> CONTRAST__SERVER__ENVIRONMENT=<value> JAVA_TOOL_OPTIONS="-javaagent:/opt/contrast/contrast.jar -Dcontrast.config.path=/var/contrast/contrast_security.yaml"
```

## Deploying to AWS Beanstalk


```shell
eb deploy
```

See https://docs.contrastsecurity.com/installation-javaconfig.html for more on configuring the Contrast agent.
