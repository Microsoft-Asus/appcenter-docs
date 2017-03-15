---
title: Setting up an Xcode Project for Code Signing with Mobile Center
description: Code signing apps built with Mobile Center
keywords: code signing, ios
author: siminapasat
ms.author: siminap
ms.date: 01/20/2017
ms.topic: article
ms.assetid: 47bb8997-4d24-48f4-a0e8-f503d2c65185
ms.service: mobile-center
ms.custom: build
ms.tgt_pltfrm: ios
---

# Setting up an Xcode project for code signing

When developing an iOS app, there are two ways to configure the Code Signing settings.

## Automatic provisioning
The automatic provisioning settings let Xcode select what provisioning profile and certificate to use when signing a build. Generally, this is the approach [recommended by Apple](https://developer.apple.com/library/content/qa/qa1814/_index.html) when developing locally.

When building your project on a build service, such as Mobile Center, we recommend you use the Manual signing settings in order to make sure that locally your project is using the same signing settings as the one in Mobile Center.

When building a project locally on the device, Xcode will use the automatically detected provisioning profile and certificate. In order to build your project with Mobile Center, make sure that the files you are uploading are compatible with the code signing settings in the project and in the project targets. For instance, if the Xcode project is configured to use a development code signing identity, make sure to upload a compatible development certificate to Mobile Center.

### Xcode 7
When automatically signing an app with Xcode7, make sure to upload to Mobile Center the same type of provisioning profile as the one specified in your Xcode project configurations.
![Automatic provisioning Xcode 7][xcode-7-signing]

### Xcode 8
The Automatic signing in Xcode 8 is truly automatic. In this case, the provisioning profile does not have to be specified at all and Xcode will generate a new provisioning profile locally that will work seamlessly for signing the builds locally.

We advise you to use the manual provisioning option when running builds on Mobile Center.

## Manual provisioning
You can configure Xcode to use a specific certificate and provisioning profile to sign a build. Make sure that you upload the exact same files to Mobile Center.

[xcode-7-signing]: images/xcode-7-signing.png