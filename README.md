# react-native-client-template

TODO

## Table of contents

- [About this repository](#about-this-repository)
- [Software requirements](#software-requirements)
- [Setup and run](#setup-and-run)
- [Style enforcement](#style-enforcement)
- [Visual Studio Code optional useful extensions](#visual-studio-code-optional-useful-extensions)
- [How to trigger CD to generate an APK on release](#how-to-trigger-cd-to-generate-an-apk-on-release)

## About this repository

### Technologies used:

![Typescript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![Node](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)
![React-Native](https://img.shields.io/badge/React_Native-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![NPM](https://img.shields.io/badge/NPM-%23000000.svg?style=for-the-badge&logo=npm&logoColor=white)
![ESLint](https://img.shields.io/badge/ESLint-4B3263?style=for-the-badge&logo=eslint&logoColor=white)
![Prettier](https://img.shields.io/badge/prettier-1A2C34?style=for-the-badge&logo=prettier&logoColor=F7BA3E)
![Dependabot](https://img.shields.io/badge/dependabot-025E8C?style=for-the-badge&logo=dependabot&logoColor=white)

### Automation:

![CD](https://github.com/Tale152/react-native-client-template/actions/workflows/CD.yml/badge.svg)

### Repository activities:

![GitHub last commit](https://img.shields.io/github/last-commit/Tale152/react-native-client-template)
![GitHub release (latest by date including pre-releases)](https://img.shields.io/github/v/release/Tale152/react-native-client-template?include_prereleases)
![GitHub Release Date](https://img.shields.io/github/release-date/Tale152/react-native-client-template)
![GitHub commits since latest release (by date)](https://img.shields.io/github/commits-since/Tale152/react-native-client-template/latest)

## Software requirements

### Must have:

- Node
- NPM

### Recommended

- Visual Studio Code

## Setup and run

Launch the following command to install globally expo-cli; this is required to run the application on [Expo](https://expo.dev/).

```console
npm install -g expo-cli
```

Then, move inside the project's root folder and install all the dependencies running this command:

```console
npm i
```

Download the [Expo client app](https://play.google.com/store/apps/details?id=host.exp.exponent&hl=en_US&gl=US) on your mobile device and, after that, run the following command to start the application generating the QR scan that you will scan from the Expo client app:

```console
npm start
```

If everything is fine you should be seeing the application on your device.  
That's it. Happy coding :)

## Style enforcement

Among the installed dependencies, you will get [Eslint](https://eslint.org/) and [Prettier](https://prettier.io/).  
To trigger the Eslint check run the following command:

```console
npm run lint
```

Similarly, to run Prettier, execute the following command (**warning**: it will write on files that do not respect the style rules):

```console
npm run prettier:write
```

## Visual Studio Code optional useful extensions

Upon opening the project, Visual Studio Code will ask you if you want to install the suggested dependencies; proceed to install them.
Alternatively, recommended dependencies can be found under the extensions tab typing @recommended in the search bar.

Among said optional extensions, you can find automation for style enforcing every time you save a file, autocomplete for React Native and much more.

You can find a list of the recommended extensions for this project [here](https://github.com/Tale152/interconnected-mobile-client/blob/master/.vscode/extensions.json).

## How to trigger CD to generate an APK on release

First, [register on the Expo portal](https://expo.dev/signup). Once logged in, use the web client to create an access token. Then, [create a new secret for the repository](https://github.com/Azure/actions-workflow-samples/blob/master/assets/create-secrets-for-GitHub-workflows.md) (naming it **EXPO_TOKEN**) containing the token that you previously created.

When you want to create a new release (with an attached APK of your application), first create a new tag, including a message that sums up the notes for the new release.

```console
git tag -a v<VERSION> -m "<RELEASE NOTES>"
```

Then push the new tag to the remote repository, triggering [this](https://github.com/Tale152/interconnected-mobile-client/blob/master/.github/workflows/CD.yml) workflow, crating automatically a new [release](https://github.com/Tale152/interconnected-mobile-client/releases/latest) with the compiled APK file.

```console
git push origin --tags
```

You can also find the APK on the Expo portal.
