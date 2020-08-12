# Create React App (CRA)

## Intro
The official supported way to create SPA React Applications.
Offering a moder build setup with no configuration.

As you gain more experience and need more control, it offers a "reject" script, to remove the default build process, and 

### Create React App (CRA)
* [Documentation](https://create-react-app.dev/docs/documentation-intro)
* [Getting Started](https://create-react-app.dev/docs/getting-started)

The single build script which is built-in, means you don’t need to install or configure tools like webpack or Babel. They are preconfigured and hidden so that you can focus on the code.
If you need more advanced mechanisms, them use the Eject script.

### Quick Start
```
npx create-react-app my-app
cd my-app
npm start
```

Then open http://localhost:3000/ to see your app.

When you’re ready to deploy to production, create a minified bundle with npm run build.

To ensure your using npm rather than yarn please use, 

```
npx create-react-app my-app --use-npm
```

to ensure the correct dependencies are installed.

## React and Templates flag

You can create a new app using a specific template for example Typescript.
Simply append --template [template-name]
See Typescript below.

You can find a list of available templates by searching for "cra-template-*" on npm.
Add you can *[customise](https://create-react-app.dev/docs/custom-templates/)* your own templates.


## React and Typescript
Using Typescript can make you React Apps more readable, type safe, robust, maintainable, and stable.
Since v3.0/3.1 been more integration introduced for the both.

### Create React App with Typescript

```
npx create-react-app my-app --template typescript
```

Support for Typescript introduced support for Typescript since react-scripts 2.1 was built into the package.
We use a --typescript flag, when creating a new project.

see: [Adding Typescript](https://create-react-app.dev/docs/adding-typescript/)

Create React App 2+ supports:
* TypeScript, 
* Sass, 
* CSS Modules 
* and more 

without ejecting: https://reactjs.org/blog/2018/10/01/create-react-app-v2.html

### Eject Script

```
npm run eject
```

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you need advanced build tool and configuration choices, you can `eject` at any time. This command removes the single build dependency from your project.

It will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. 

All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.


*[]()

## Samples
* []()

## Resources
* []()

## Courses
* []()



