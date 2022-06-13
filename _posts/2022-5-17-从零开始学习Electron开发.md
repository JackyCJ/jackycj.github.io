--
layout:     post
title:      从零开始学习Electron开发
subtitle:   支持Windows/Mac
date:       2021-04-21
author:     JackyCJ
header-img: img/post-bg-2015.jpg
catalog: true
tags:
    - Electron
    - npm
    - yarn

---


# 从零开始学习Electron开发



To check that Node.js was installed correctly, type the following commands in your terminal client:

```
node -v
npm -v
```

优先考虑npm，yarn经常失败

npm安装指定版本

```
npm install [package-name]@[version-number]
```

安装VUE

```
npm install 
npm i @vue/cli-service
```


How To Know The Specific Version of An Installed Package
If you want to see a tree-structured list of all your locally installed packages, including their dependencies, run the following command:

```
npm list
npm view [package-name] versions
npm view [package-name] version
```

创建

```
mkdir my-electron-app && cd my-electron-app
yarn init
```

## __# yarn install__

Install all the dependencies listed within package.json in the local node_modules folder.

The __yarn.lock__ file is utilized as follows:

- If __yarn.lock__ is present and is enough to satisfy all the dependencies listed in package.json, the exact versions recorded in __yarn.lock__ are installed, and __yarn.lock__ will be unchanged. Yarn will not check for newer versions.
- If __yarn.lock__ is absent, or is not enough to satisfy all the dependencies listed in package.json (for example, if you manually add a dependency to package.json), Yarn looks for the newest versions available that satisfy the constraints in package.json. The results are written to __yarn.lock__.

If you want to ensure __yarn.lock__ is not updated, use __--frozen-lockfile__.

## # <table><tr><td bgcolor=yellow>yarn install --check-files</td></tr></table>
Verifies that already installed files in __node_modules__ did not get removed.
## __# yarn install --flat__

Install all the dependencies, but only allow one version for each package. On the first run this will prompt you to choose a single version for each package that is depended on at multiple version ranges. These will be added to your package.json under a resolutions field.

"resolutions": {
  "package-a": "2.0.0",
  "package-b": "5.0.0",
  "package-c": "1.5.2"
}

## __# yarn install --force__

This refetches all packages, even ones that were previously installed.
## __# yarn install --har__

Outputs an HTTP archive from all the network requests performed during the installation. HAR files are commonly used to investigate network performance, and can be analyzed with tools such as Google’s HAR Analyzer or HAR Viewer.
## __# yarn install --ignore-scripts__

Do not execute any scripts defined in the project package.json and its dependencies.
## __# yarn install --modules-folder <path>__

Specifies an alternate location for the node_modules directory, instead of the default ./node_modules.
## __# yarn install --no-lockfile__

Don’t read or generate a __yarn.lock__ lockfile.
## __# yarn install --production[=true|false]__

Yarn will not install any package listed in devDependencies if the NODE_ENV environment variable is set to production. Use this flag to instruct Yarn to ignore NODE_ENV and take its production-or-not status from this flag instead.

    Notes: --production is the same as --production=true. --prod is an alias of --production.

## __# yarn install --pure-lockfile__

Don’t generate a ____yarn.lock____ lockfile.
## __# yarn install --focus__

Shallowly installs a package’s sibling workspace dependencies underneath its node_modules folder. This allows you to run that workspace without building the other workspaces it depends on.

Must be run inside an individual workspace in a workspaces project. Can not be run in a non-workspaces project or at the root of a workspaces project.

Learn more about focused workspaces.
## __# yarn install --frozen-lockfile__

Don’t generate a __yarn.lock__ lockfile and fail if an update is needed.
## __# yarn install --silent__

Run yarn install without printing installation log.
## __# yarn install --ignore-engines__

Ignore engines check.
## __# yarn install --ignore-optional__

Don’t install optional dependencies.
## __# yarn install --offline__

Run yarn install in offline mode.
## __# yarn install --non-interactive__

Disable interactive prompts, like when there’s an invalid version of a dependency.
## __# yarn install --update-checksums__

Update checksums in the __yarn.lock__ lockfile if there’s a mismatch between them and their package’s checksum.
## __# yarn install --audit__

Checks for known security issues with the installed packages. A count of found issues will be added to the output. Use the __yarn audit__ command for additional details. Unlike npm, which automatically runs an audit on every install, yarn will only do so when requested. (This may change in a later update as the feature is proven to be stable.)
## __# yarn install --no-bin-links__

Prevent yarn from creating symlinks for any binaries the package might contain.
## __# yarn install --link-duplicates__

Create hardlinks to the repeated modules in node_modules.
## __# yarn install --verbose__

Show additional logs while installing dependencies



# 参考

- [yarn install](https://classic.yarnpkg.com/en/docs/cli/install)
- [NPM: How To Install A Specific Version of Node.js Package](https://www.whitesourcesoftware.com/free-developer-tools/blog/npm-how-to-install-a-specific-version-of-node-js-package/)
