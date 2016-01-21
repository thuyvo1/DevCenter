---
layout: tutorial
title: MobileFirst development in Cordova applications
relevantTo: [cordova]
weight: 1
---

## Overview
From [http://cordova.apache.org/](http://cordova.apache.org/):

> Apache Cordova is an open-source mobile development framework. It allows you to use standard web technologies such as HTML5, CSS3, and JavaScript for cross-platform development, avoiding each mobile platforms' native development language. Applications execute within wrappers targeted to each platform, and rely on standards-compliant API bindings to access each device's sensors, data, and network status.

IBM MobileFirst Platform Foundation provides an SDK in the form of a standard Cordova plug-in. Learn how to [Add the MobileFirst Platform Foundation SDK to Cordova applications](../../adding-the-mfpf-sdk/adding-the-mfpf-sdk-to-cordova-applications).

The MobileFirst SDK feature set provides the following:

* Use MobileFirst `ResourceRequest` API to retrieve data from backend systems
* Protect applications using the MobileFirst SecurityChecks and other security features such as Application Authentcity Protection
* Ability to navigate and share data between web and native views and/or call Native code using the MobileFirst `SendAction` API
* Update an application's web resources using Direct Update
* And more...

> For a complete list of MobileFirst SDK abilities [visit the user documentation](http://www-01.ibm.com/support/knowledgecenter/SSHS8R_8.0.0/wl_welcome.html).

## Application development
### Cordova plug-ins
Cordova applications can be enhanced by integerating **Cordova plug-ins**. Using Cordova plug-ins can provide enhancements such as adding native UI elements (dialogs, tabbars, spinners and the like), as well as more advanced functionalities such as Mapping and Geolocation, loading of external content, custom keyboards, Device integration (camera, contacts, sensors, and so on).

You can find Cordova plug-ins in the official [Cordova plug-ins repository](https://cordova.apache.org/plugins/), as well as on [GitHub.com](https://github.com) and in popular Cordova blogs, such as [Plugreg](http://plugreg.com/).

Example plug-ins:

- [cordova-plugin-dialogs](https://www.npmjs.com/package/cordova-plugin-dialogs)
- [cordova-plug-inprogress-indicator](https://www.npmjs.com/package/cordova-plugin-progress-indicator)
- [cordova-plugin-statusbar](https://www.npmjs.com/package/cordova-plugin-statusbar)

### 3rd-party frameworks
Cordova application development can be further enhanced by using frameworks such as [Ionic](http://ionicframework.com/), [AngularJS](https://angularjs.org/), [jQuery Mobile](http://jquerymobile.com/), [Backbone](http://backbonejs.org/) and many others.

### 3rd-party packages
Applications can be modified using 3rd party packages to achieve requirements such as Minification &amp; Concatenation of the application's web resources and more. Popular packages to do so are:

- [uglify-js](https://www.npmjs.com/package/uglify-js)
- [clean-css](https://www.npmjs.com/package/clean-css)

## Further reading
Learn more about Cordova:

- [Cordova Overview](https://cordova.apache.org/docs/en/5.4.0/guide/overview/index.html)
- [Cordova best practices, testing, debugging, cosiderations and keeping up](https://cordova.apache.org/docs/en/5.4.0/guide/next/index.html#link-10)
- [Get started with Cordova applications development](https://cordova.apache.org/#getstarted)

## Tutorials to follow next
Get started by [adding the MobileFirst SDK to your Cordova application](../../adding-the-mfpf-sdk/adding-the-mfpf-sdk-to-cordova-applications), and review MobileFirst-provided features in the [All Tutorials](../../all-tutorials/) section.