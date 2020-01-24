FROM maven:3.6-amazoncorretto-11

RUN curl https://packages.microsoft.com/config/rhel/7/prod.repo >> /etc/yum.repos.d/microsoft.repo \
    && yum update -y \
    && yum install -y \
    git \
    powershell \
    && yum clean all

# The following is adopted from: 
# https://github.com/PowerShell/PowerShell-Docker/blob/master/release/stable/centos7/docker/Dockerfile
# PowerShell Docker Files
# Copyright (c) Microsoft Corporation. All rights reserved.

# Define ENVs for Localization/Globalization
ENV DOTNET_SYSTEM_GLOBALIZATION_INVARIANT=false \
    LC_ALL=en_US.UTF-8 \
    LANG=en_US.UTF-8 \
    # set a fixed location for the Module analysis cache
    PSModuleAnalysisCachePath=/var/cache/microsoft/powershell/PSModuleAnalysisCache/ModuleAnalysisCache

# Initialize powershell module cache
RUN pwsh \
        -NoLogo \
        -NoProfile \
        -Command " \
          \$ErrorActionPreference = 'Stop' ; \
          \$ProgressPreference = 'SilentlyContinue' ; \
          while(!(Test-Path -Path \$env:PSModuleAnalysisCachePath)) {  \
            Write-Host "'Waiting for $env:PSModuleAnalysisCachePath'" ; \
            Start-Sleep -Seconds 6 ; \
          }"

# Use PowerShell as the default shell
# Use array to avoid Docker prepending /bin/sh -c
CMD [ "pwsh" ]