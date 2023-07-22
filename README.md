## Project Setup 

### Set up Git
```
git init
git branch -M main
git remote add origin https://github.com/secretagentan/project-portfolio.git
touch README.md
git add .
git commit -m "first commit"
git push -u origin main
```

### Set up NPM & lite-server
```
npm init
npm install lite-server --save-dev
```
Edit package.json
```
"scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "npm run lite",
    "lite": "lite-server"
},
```
RUN: lite-server
```
npm start
```

### .gitignore
```
touch .gitignore
```
Add the following text inside the .gitignore file
```
node_modules
```


### jQuery, Popper.js, and Bootstrap (v4.5.2)
```
npm install jquery@3.5.1 popper.js@1.16.1
npm install bootstrap@4.5.2
```
[*INCOMPLETE*] Add the following within the "head" tag
```
<link rel="stylesheet" href="node_modules/bootstrap/dist/css/bootstrap.min.css" />
<!-- Additional CSS must be placed after Bootstrap CSS -->
<link rel="stylesheet" href="css/styles.css" />
```
[*INCOMPLETE*] Add the following below the closing "footer" tag
```
</footer>

<!-- jQuery must come first, then Popper.js, then the Bootstrap JavaScript plugins.-->
<script src="node_modules/jquery/dist/jquery.slim.min.js"></script>
<script src="node_modules/popper.js/dist/umd/popper.min.js"></script>
<script src="node_modules/bootstrap/dist/js/bootstrap.min.js"></script>
```

### Font-Awesome & Bootstrap-Social
```
npm install font-awesome@4.7.0
npm install bootstrap-social@5.1.1
```
[*INCOMPLETE*] Update the following within the "head" tag
```
<link rel="stylesheet" href="node_modules/bootstrap/dist/css/bootstrap.min.css" />
<!-- Additional CSS must be placed after Bootstrap CSS -->
<link rel="stylesheet" href="node_modules/font-awesome/css/font-awesome.min.css" />
<link rel="stylesheet" href="node_modules/bootstrap-social/bootstrap-social.css" />
<link rel="stylesheet" href="css/styles.css" />
```

### Set up SASS 
Create the following folder/file:
```
css/styles.scss
```
#### For Intel Mac - check node version:
```
node -v
```
For Node version 16.x, enter:
```
npm install --save-dev node-sass@6
```
#### For Mac w/ M1 chip:
```
npm install --save-dev sass
```

#### Add compilation script in package.json ("scss" under "scripts")
For Intel Mac:
```
"scripts": {
    "lite": "lite-server",
    "scss": "node-sass -o css/ css/",
    "start": "npm run lite",
    "test": "echo \"Error: no test specified\" && exit 1"
},
```
For M1 Mac: 
```
"scripts": {
    "lite": "lite-server", 
    "scss": "sass css:css",
    "start": "npm run lite",
    "test": "echo \"Error: no test specified\" && exit 1"
},
```

#### COMPILE: .scss to .css
```
npm run scss
```

#### Set up JS files
Create the following folder/file: 
```
js/scripts.js
```
[*INCOMPLETE*] Add the "js/scripts.js" src below the scripts under the "footer" tag: 
```
<script src="node_modules/jquery/dist/jquery.slim.min.js"></script>
<script src="node_modules/popper.js/dist/umd/popper.min.js"></script>
<script src="node_modules/bootstrap/dist/js/bootstrap.min.js"></script>
<script src="js/scripts.js"></script>
```

### Onchange & Parallelshell 
Inside project folder:
```
npm install --save-dev onchange@7.0.0
npm install --save-dev -E parallelshell@3.0.1
```
Update script object in package.json:
```
"start": "npm run watch:all",
"watch:scss": "onchange 'css/*.scss' -- npm run scss",
"watch:all": "parallelshell 'npm run watch:scss' 'npm run lite'"
```

### Copyfiles: Copy Font-Awesome fonts
Install copyfiles module (use sudo if this doesn't work):
```
npm install --save-dev copyfiles@2.2.0
```
Update the scripts object in package.json:
```
"copyfonts": "copyfiles -f node_modules/font-awesome/fonts/* dist/fonts",
```

### Imagemin-CLI: Compress and minify images
Install imagemin-cli module (use sudo if doesn't work):
```
npm install --save-dev imagemin-cli@5.1.0
```
Update scripts in package.json: 
```
"imagemin": "imagemin img/* -o dist/img",
```

### Concatenate, minify, uglify
```
npm install --save-dev usemin-cli@0.6.0
```
Update scripts (package.json): 
```
"usemin": "usemin contactus.html -d dist --htmlmin -o dist/contactus.html && usemin aboutus.html -d dist --htmlmin -o dist/aboutus.html && usemin index.html -d dist --htmlmin -o dist/index.html",
```
[*INCOMPLETE*] Wrap CSS links inside "head" with *build:css* and *endbuild* comments
```
<!-- build:css css/main.css -->
<link rel="stylesheet" href="node_modules/bootstrap/dist/css/bootstrap.min.css" />
<link rel="stylesheet" href="node_modules/font-awesome/css/font-awesome.min.css" />
<link rel="stylesheet" href="node_modules/bootstrap-social/bootstrap-social.css" />
<link rel="stylesheet" href="css/styles.css" />
<!-- endbuild -->
<link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Lobster|Open+Sans" />
```
* Do not include Google fonts.

[*INCOMPLETE*] Wrap JS scripts below closing "footer" with *build:js* and *endbuild* comments
```
<!-- build:js js/main.js -->
<script src="node_modules/jquery/dist/jquery.slim.min.js"></script>
<script src="node_modules/popper.js/dist/umd/popper.min.js"></script>
<script src="node_modules/bootstrap/dist/js/bootstrap.min.js"></script>
<script src="js/scripts.js"></script>
<!-- endbuild -->
```

### Rimraf: Automate dist/ folder cleanup
```
npm install --save-dev rimraf@3.0.2
```
package.json: 
```
"scripts": {
    "clean": "rimraf dist",
```

### Build the distribution folder
package.json:
```
"scripts": {
    "build": "npm run clean && npm run imagemin && npm run copyfonts && npm run usemin",
```
add "dist" to .gitignore:
```
node_modules
dist
```
#### RUN: build
```
npm run build
```