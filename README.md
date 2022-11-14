<a name="readme-top"></a>

<!-- PROJECT LOGO -->
<br />
<div align="center">

  <p>
    Tailwind CLI starter guide. 
   
  </p>
  <p>There are 4 ways of using Tailwind in your project https://tailwindcss.com/docs/installation 1. Tailwind CLI, 
  2. Using PostCSS (Installing Tailwind CSS as a PostCSS plugin is the most seamless way to integrate it with BUILD TOOLS LIKE WEBPACK, Rollup, Vite, and Parcel),
  3. Framework Guides (Framework-specific guides that cover our recommended approach to installing Tailwind CSS in a number of popular environments), 4. Play CDN (Use the Play CDN to try Tailwind right in the browser without any build step. The Play CDN is designed FOR DEVELOPMENT PURPOSES ONLY, and is NOT THE BEST CHOICE FOR PRODUCTION)</p>
  <p>
</div>

<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#about-the-project">Install Tailwind</a></li>
    <li><a href="#configure-your-template-paths"></a>Configure your template paths</li>
    <li><a href="#create-css-file">Create css file</a></li>
    <li><a href="#start-the-tailwind-cli-build-process">Start the Tailwind CLI build process</a></li>
    
  </ol>
</details>

<!-- ABOUT THE PROJECT -->

## Install Tailwind

- create a project folder open it with VS Code
- npm init -y   - this will create package.json file which is simply a manifest with some information if we install any dependecies it will show in here
- npm install -D tailwindcss  - we installing it as dev dependecies no need for it in production
- npx tailwindcss init  - this will create tailwind.config.js, we are using npx so we are runnin it globally
- 

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Configure tour template paths
- this is how tailwind.config.js looks by default:
module.exports = {
  content: ["./src/**/*.{html,js}"],
  theme: {
    extend: {},
  },
  plugins: [],
 
 in 'content' it tells tailwind to look into the source folder and look for any html and js file that have tailwind classes 

 - we are not going to have src folder so we can change and tell 
 tailwind to look for any html file in the current directory:

 module.exports = {
  content: ['./*.html'],
  theme: {
    extend: {},
  },
  plugins: [],
}



<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- ACKNOWLEDGMENTS -->

## Crearte css file

- we are going to crerate input.css file in our root - can be called whatever not necessatly input
- Add the @tailwind directives for each of Tailwind’s layers to your main CSS file:
@tailwind base;
@tailwind components;
@tailwind utilities;

you might see some underlines there to get rid of them instal postCSS lungage Suport plugin (and this one stops my css code from showing sugestions)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Start the Tailwind CLI build process

- original line look like this:
npx tailwindcss -i ./src/input.css -o ./dist/output.css --watch and it says to run tailwind as an input -i in the src/input.css file and define the output -o and put it in the dist folder in the output.css file and then constantly watch the input compile into the output

- instead of running this in the terminal all the time we will create npm scripts in package.json:
 "scripts": {
    "build": "tailwindcss -i ./input.css -o ./css/style.css",
    "watch": "tailwindcss -i ./input.css -o ./css/style.css --watch"
  }, 

- now when we run: npm run build a css folder with style.css will get created, in our html file now we can link that css file to our project:
 link rel="stylesheet" href="css/style.css

-now when we run: npm run watch it will constantly watch our changes  

<p align="right">(<a href="#readme-top">back to top</a>)</p>

