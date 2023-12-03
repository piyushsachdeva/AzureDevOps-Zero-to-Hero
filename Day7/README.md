# Day 7 - Azure Artifacts 👨‍💻

## Check out the video below for Day7 👇

[![Day7/16 - Azure Artifacts ](https://img.youtube.com/vi/wq_sn9ey4KM/sddefault.jpg)](https://youtu.be/wq_sn9ey4KM)

## Setup your Azure repos with the same application code

You can import the below repo to clone the Nike landing page sample website code to your Azure Repos:

https://github.com/piyushsachdeva/nike_landing_page.git

**Note:** You must set the app settings as below to disable all file caching:

*  WEBSITE_DYNAMIC_CACHE=0
*  WEBSITE_LOCAL_CACHE_OPTION=Never
  

## Architectural diagram used in the video

![image](https://github.com/piyushsachdeva/AzureDevOps-Zero-to-Hero/assets/40286378/f7facb49-af0d-4f6a-8e14-ae8444423c91)

## Build Pipeline YAML code:

``` YAML
trigger: 
- main

stages:
- stage: Build
  jobs:
  - job: Build
    pool:
      vmImage: 'ubuntu-latest'
    steps:
    - task: Npm@1
      inputs:
        command: 'custom'
        customCommand: 'install -D tailwindcss postcss autoprefixer'
    - task: Npm@1
      inputs:
        command: 'custom'
        customCommand: 'run build'

    - task: Npm@1
      inputs:
        command: 'publish'
        workingDir: './dist'
        publishRegistry: 'useFeed'
        publishFeed: '$FEED_DETAILS'
```



### Post-deployment inline script in the Release pipeline

```
cp -rf /home/site/wwwroot/package/* /home/site/wwwroot/
```


