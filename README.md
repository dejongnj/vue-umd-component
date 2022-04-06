# umd-component
## Problem statement
This project did a simple `vue create umd-component` selecting Vue 2, babel, eslint. I then set created a script in package.json to build a library, using the default hello world component, with output to the dist folder. I included an html file in the dist folder and root folder which will demonstrate the issue.

If you run the `yarn file-server` it will use http-server to serve up the index.html and built files umd-component.umd.js etc. The index.html demonstrates the issues I'm having:
- I am unable to import the file as a module, and get the error:
> Uncaught SyntaxError: The requested module '/umd-component.umd.js' does not provide an export named 'default' (at (index):18:10)
- However, commenting out that script and uncommenting what is commented out, will allow me to use the component. But it turns out the component is saved directly to the window with the key "umd-component". (May need to clear cache or restart http-server to see the changes).


The script used to build the default HelloWorld component into a umd.js file is:
```
 "build:library": "vue-cli-service build --target lib --name umd-component src/components/HelloWorld.vue",
```
to run the script (don't do need to do it yet, as I've included the dist folder in git history), but if you do, I've included a copy of the index.html in the root which you can then copy to the dist folder, and serve up as above.
```
yarn build:library
```

## Setup
```
yarn install
```
## To demo th


# Below this is default docs that come with `vue create umd-component`
## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn serve
```

### Compiles and minifies for production
```
yarn build
```

### Lints and fixes files
```
yarn lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
