# react-app-with-angular

#Steps to integrate react app with angular

Take a react app which is written in class based format and not functional format, wrap it within custom element.
Use a third party library like "react-to-webcomponent" for registering the react app as custom element.
Do this custom element registry with only App.js.
If you want to check whether the custom registration has happened, replace your index.js code ReactDOM.render(<App />, document.getElementById('root')); --> ReactDOM.render(<splunk-app />, document.getElementById('root'));
Build the react app - npm run build.
Copy the build folder to assets folder within angular app.
The assets folder content like svgs, jpg, mp3 needs to be moved to parent assets folder as the bundled js will be refering to the location which is no longer valid.
Modify the angular.json so, that it understands the new minified js files. Add it within scripts array inside build.
Modify tsconfig.json and add "jsx": "react" within compilerOptions.
In index.html add the js inside body tag.
Add CUSTOM_ELEMENTS_SCHEMA within schemas array so, that angular is able to understand the custom element.
In the component where you are planning to render this custom element (remember we created a wrapper around react element/app) use it like the way you will use any angular component.
