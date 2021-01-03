# Table of Contents:
- [Table of Contents:](#table-of-contents)
- [Install Angular ↑](#install-angular-)
- [Create Monorepo Workspace for save multiple projects in Angular ↑](#create-monorepo-workspace-for-save-multiple-projects-in-angular-)
- [Create a component use Angular CLI ↑](#create-a-component-use-angular-cli-)
- [Adding component ↑](#adding-component-)
- [Git Hub asociate repository to my Project ↑](#git-hub-asociate-repository-to-my-project-)
- [Git Hub push changes to repository GitHub ↑](#git-hub-push-changes-to-repository-github-)

# Install Angular [↑](#table-of-contents)
1. Download and install node.js (Recomended LTS version) + node -v in Terminal
2. Download and install VSC
3.  **```npm install -g @angular/cli```** and check ng --version 

# Create Monorepo Workspace for save multiple projects in Angular [↑](#table-of-contents)

1. **```ng new workspace-angular --strict --create-application=false ```**
2. **```cd workspace-angular ```** (change directory)
3. **```code . ```** (open the project)
4. **```ng generate application app-name```** (adding apps in the monorepo)
5. In **```angular.json ```** file select   **```defaultProject ```** and set default project of list of projects
6. Run projects:
    - For run default project: 
        -  **```ng serve -o ```**
        -  **```npm start ```**
    - For run others projects: 
        -  **```npm serve nameProject ```**
        -  **```npm start nameProject  ```**
        -  **```npm run start nameProject ```**

# Create a component use Angular CLI [↑](#table-of-contents)
For create component use:
1. Complete form:    **```ng generate component name-component ```**
2. Abreviated form:  **```ng g        c         name-component ```**

# Adding component [↑](#table-of-contents)
For call component in HTML file:
1. Go to the selector atribute located in the file **```nameComponent.component.ts```** and copy the value
2. Paste the selector in other component HTML **```<app-component-name></app-component-name>```**

# Git Hub asociate repository to my Project [↑](#table-of-contents)
1. Go to gitHub page and create repository New > write RepositoryName (ex. workspace-angular) and push Create Repository
2. **```git remote add origin URL```** URL example https://github.com/yourUserNameGit/yourRepositoryName.git
3. **```git branch -M main```**
4. **```git push -u origin main```**

# Git Hub push changes to repository GitHub [↑](#table-of-contents)
1. make changes in repository (Working Directory → WD)
2. **```git status```** (for see the changes in WD)
3. **```git add .```** (for add all changes of WD to Staging Area → SA) or **```git add file```** (for add only one file of WD to SA)
4. **```git status```** (for verify files added to SA)
5. For unstage file added to WD for SA **```git restore --staged <file>```**
6. **```git commit -m "description commit message"```** (for save SA files in Local Repository → LR)
7. **```git push```** (for upload files to LR to Remote Repository RR) RR = GitHub Repository



