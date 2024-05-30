# Creating PAC PCF Components

This guide will walk you through the process of creating Power Apps Component Framework (PCF) components.

## Prerequisites

Before you begin, make sure you have the following installed:

- [Node.js](https://nodejs.org)
- [Power Apps CLI](https://aka.ms/PowerAppsCLI)
- [Visual Studio Code](https://code.visualstudio.com) (optional, but recommended)

## Step 1: Set up your development environment

1. Open a terminal or command prompt.
2. Navigate to the directory where you want to create your PCF component.
3. Run the following command to initialize a new PCF project:

    ```shell
    pac pcf init --namespace <namespace> --name <component-name> --template <template> --framework <framework> --outputDirectory <output-directory> --run-npm-install
    ```
    Replace `<namespace>` with your desired namespace, `<component-name>` with the name of your component, `<template>` with the desired template (field or dataset), `<framework>` with the rendering framework (none or react), `<output-directory>` with the output directory, and `--run-npm-install` to automatically run 'npm install' after the control is created.

    Here are some examples:

    - Example 1: Creating a component with namespace "com" and component name "sampleComponent" using the field template and no rendering framework:

        ```shell
        pac pcf init --namespace com --name sampleComponent --template field --framework none --outputDirectory ./componentName --run-npm-install
        ```

    - Example 2: Creating a component with namespace "org" and component name "customControl" using the dataset template and React rendering framework:

        ```shell
        pac pcf init --namespace org --name customControl --template dataset --framework react --outputDirectory ./componentName --run-npm-install
        ```

    - Example 3: Creating a component with namespace "myapp" and component name "myControl" using the field template and no rendering framework, and automatically running 'npm install':

        ```shell
        pac pcf init --namespace myapp --name myControl --template field --framework none --outputDirectory ./componentName --run-npm-install
        ```

## Step 2: Build and test your component

1. Open the project in your preferred code editor.
2. Customize the component by modifying the code in the `src` folder.
3. Run the following command to build the component:

    ```shell
    npm run build
    ```

4. Test the component locally by running the following command:

    ```shell
    pac pcf push --code
    ```

    This will deploy the component to your local Power Apps environment.

## Step 3: Package and distribute your component

1. Run the following command to package your component:

    ```shell
    pac pcf pack
    ```

    This will create a `.zip` file in the `pkg` folder.

2. Distribute your component by uploading the `.zip` file to the Power Apps Component Library or sharing it with others.

## Conclusion

Congratulations! You have successfully created a PAC PCF component. Refer to the official documentation for more advanced topics and customization options.
