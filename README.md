## Project Setup 

### Setting up Git
```
git init
git branch -M main
git remote add origin https://github.com/secretagentan/project-portfolio.git
touch README.md
git add .
git commit -m "first commit"
git push -u origin main
```

### Setting up NPM & lite-server
```
npm init
npm install lite-server --save-dev
```

#### Edit package.json
```
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "npm run lite",
    "lite": "lite-server"
  },
```

#### Run lite-server
```
npm start
```

#### Set up .gitignore
```
touch .gitignore
```
Add the text 
```
node_modules
```
to .gitignore


#### Set up jQuery, Popper.js, and Bootstrap (v4.5.2)
```
npm install jquery@3.5.1 popper.js@1.16.1
npm install bootstrap@4.5.2
```
Add the following below the closing </footer> tag
```
    </footer>

    <!-- jQuery must come first, then Popper.js, then the Bootstrap JavaScript plugins.-->
    <script src="node_modules/jquery/dist/jquery.slim.min.js"></script>
    <script src="node_modules/popper.js/dist/umd/popper.min.js"></script>
    <script src="node_modules/bootstrap/dist/js/bootstrap.min.js"></script>
```
