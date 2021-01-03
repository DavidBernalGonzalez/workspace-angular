# Table of Contents:
- [Table of Contents:](#table-of-contents)
- [Install Angular](#install-angular)
- [Create Monorepo Workspace for save multiple projects in Angular {#custom-id}](#create-monorepo-workspace-for-save-multiple-projects-in-angular-custom-id)
- [Create a component use Angular CLI](#create-a-component-use-angular-cli)
- [Use a component](#use-a-component)
- [Git Hub asociate repository to my Project](#git-hub-asociate-repository-to-my-project)
- [Git Hub push changes on my repository](#git-hub-push-changes-on-my-repository)

# Install Angular
1. Download and install node.js (Recomended LTS version) + node -v in Terminal
2. Download and install VSC
3.  ```npm install -g @angular/cli``` and check ng --version 

# Create Monorepo Workspace for save multiple projects in Angular {#custom-id}

1.  ```ng new workspace-angular --strict --create-application=false ```
2.  ```cd workspace-angular ``` (change directory)
3.  ```code . ``` (open the project)
4. ng generate application app-name (adding apps in the monorepo)
5. In  ```angular.json ``` file select  ```defaultProject ``` and set default project of list of projects
6. Run projects:
    - For run default project: 
        -  ```ng serve -o ```
        -  ```npm start ```
    - For run others projects: 
        -  ```npm serve nameProject ```
        -  ```npm start nameProject  ```
        -  ```npm run start nameProject ```

# Create a component use Angular CLI
For create component use:
1. Complete form:    ```ng generate component name-component ```
2. Abreviated form:  ```ng g        c         name-component ```

# Use a component
For call component in HTML file:
1. Go to the selector atribute located in the file ```nameComponent.component.ts``` and copy the value
2. Paste the selector in other component HTML ```<app-component-name></app-component-name>```

# Git Hub asociate repository to my Project
1. Go to gitHub page and create repository New > write RepositoryName (ex. workspace-angular) and push Create Repository
2. ```git remote add origin URL``` example https://github.com/yourUserNameGit/yourRepositoryName.git```
3. ```git branch -M main```
4. ```git push -u origin main```

# Git Hub push changes on my repository
1. make changes in repository
2. ```git status``` (for see the changes)
3. ```git add .``` (for add all changes) or ```git add file``` (for add only one file)
4. ```git status``` (for check adding files to upload to repository)
5. ```git commit -m "description commit message"```
6. 

