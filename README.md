
# DevOps as Code by XebiaLabs

The XebiaLabs DevOps Platform is the backbone for comprehensive release orchestration, automated and standardized deployments, and full visibility into the end-to-end Continuous Delivery process. XebiaLabs' DevOps as Code approach allows teams to define deployment packages, infrastructure, environments, release templates, dashboards, and more in YAML files that they can store in source control alongside their application code. With DevOps as Code, the components of the software delivery pipeline can be version-controlled, shared across the organization, and audited with ease.

## Features

This extension adds YAML support for the XebiaLabs DevOps Platform to Visual Studio Code. The extension adds the following features:

* Syntax highlighting
* Code completion
* Code validation
* Code formatting
* Code snippets
* Context documentation

Limitations:

* Current support is limited to XL Deploy. Support for XL Release is comming soon.
* The extension currently only knows about the types of a standard product installation and the plugins that are installed by default. In a future version it will be possible to load type information from your server.

## Demo
![screencast](https://raw.githubusercontent.com/xebialabs/devops-as-code-vscode/master/images/demo.gif)

## Usage info

If you are looking for more information about how to get started with DevOps as Code, please have a look [here](https://docs.xebialabs.com/xl-platform/concept/getting-started-with-devops-as-code.html). For more information about this extension, please keep reading.

**Note:** By default, this extension provides DevOps as Code YAML support on all documents with the filename extension `.yaml`. This may conflict with other configuration file formats that also use the .yaml extension. See the section "Changing configuration" below.

When using the extension:
* You can trigger code completion using `CTRL`+`SPACE`. Code snippets are also listed as suggestions.
* You can insert Code snippets by typing the shortcut for the snippet. For example, try typing "def" and press `ENTER`. You can cycle through all template input positions by pressing `TAB`.
* You can format the code by right-mouse clicking the document and select `Format Document`. If you make a selection, only the selected part of the document will be formatted.
* The YAML is automatically validated.
	* Issues are indicated in red and are also listed in the "Problems window". You can open this window by going to menu "View" > "Problems". Keep this window open to have a nice overview of all problems in your document.
	* The validation is XL type system-aware, as the extension includes type system information of a standard installation with the default plugins installed.
* Embedded help is displayed when using code completion and when hovering over properties in the YAML document.

## Changing configuration

You can configure the files for which the extension will be enabled. By default, the extension is enabled on all files with extension `.yaml`. This behaviour may conflict with other configuration file formats that also use the `.yaml` extension.

**Note:** `xebialabs` is the schema name of the built-in support for DevOps as Code YAML.

For example, if you want editor support for both XebiaLabs and Kubernetes YAML, you can configure the extension as shown in the following example to make it possible to distinguish between the two. Ensure that you name your project files accordingly:

```
  "yaml.schemas": {
    "xebialabs": "*.xl.yaml",
    "kubernetes": "*.k8s.yaml"
 }
```

For more configuration options, see the the documentation of the [YAML Language Support by Red Hat](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml).

## Third party notice

This plugin is built on top of the [YAML Language Support by Red Hat](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml) extension. This means this extension works exactly the same, but adds built-in support for DevOps as Code from XebiaLabs. It is not recommended to enable both plugins at the same time, since some features and settings may conflict. To get the same functionality from both extensions, disable the YAML Language Support by Red Hat extension before enabeling DevOps as Code YAML support.
