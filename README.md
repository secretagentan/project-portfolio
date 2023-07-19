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
- Create file .gitignore
- Add the text 
```
node_modules
```
to .gitignore
