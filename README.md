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

#### Edit package.json
```
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "npm run lite",
    "lite": "lite-server"
  },
```

#### Running lite-server
```
npm start
```

### Set up .gitignore
```
touch .gitignore
```
Add the text 
```
node_modules
```
to .gitignore

### Set up jQuery, Popper.js, and Bootstrap (v4.5.2)
```
npm install jquery@3.5.1 popper.js@1.16.1
npm install bootstrap@4.5.2
```
[incomplete] Add the following in the <head> tag
```
<link rel="stylesheet" href="node_modules/bootstrap/dist/css/bootstrap.min.css" />
<!-- Additional CSS must be placed after Bootstrap CSS -->
<link rel="stylesheet" href="css/styles.css" />
```
[incomplete] Add the following below the closing </footer> tag
```
</footer>

<!-- jQuery must come first, then Popper.js, then the Bootstrap JavaScript plugins.-->
<script src="node_modules/jquery/dist/jquery.slim.min.js"></script>
<script src="node_modules/popper.js/dist/umd/popper.min.js"></script>
<script src="node_modules/bootstrap/dist/js/bootstrap.min.js"></script>
```

### Set up Font-Awesome and Bootstrap-Social
```
npm install font-awesome@4.7.0
npm install bootstrap-social@5.1.1
```
[incomplete] Update the following in the <head> tag
```
<link rel="stylesheet" href="node_modules/bootstrap/dist/css/bootstrap.min.css" />
<!-- Additional CSS must be placed after Bootstrap CSS -->
<link rel="stylesheet" href="node_modules/font-awesome/css/font-awesome.min.css" />
<link rel="stylesheet" href="node_modules/bootstrap-social/bootstrap-social.css" />
<link rel="stylesheet" href="css/styles.css" />
```
