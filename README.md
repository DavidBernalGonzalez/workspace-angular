# Table of Contents:
- [Table of Contents:](#table-of-contents)
- [Install Angular ↑](#install-angular-)
- [Creating the first angular project ↑](#creating-the-first-angular-project-)
- [Flow inside Angular application ↑](#flow-inside-angular-application-)
- [Create Monorepo Workspace for save multiple projects in Angular ↑](#create-monorepo-workspace-for-save-multiple-projects-in-angular-)
- [Create a component use Angular CLI ↑](#create-a-component-use-angular-cli-)
- [Adding component ↑](#adding-component-)
- [Git Hub asociate repository to my Project ↑](#git-hub-asociate-repository-to-my-project-)
- [Git Hub push changes to repository GitHub ↑](#git-hub-push-changes-to-repository-github-)
- [Change compact folder configuration in VSC  ↑](#change-compact-folder-configuration-in-vsc--)

# Install Angular [↑](#table-of-contents)
1. Download and install node.js (Recomended LTS version) and check **```node -v```** in Terminal
2. Download and install VSC
3.  **```npm install -g @angular/cli```** and check **```ng --version ```** in Terminal

# Creating the first angular project [↑](#table-of-contents)
1. Open terminal in VSC: Terminal > New Terminal or CNTL + Ñ
2. **```ng new```**
3. What name would you like to use for the application? my-first-app
4. Would you like to add Angular routing? **```N```** (for the moment)
5. Which stylesheet format would you like to use? (Use arrow keys) **```CSS```** (for the moment)
6. **```cd my-first-app```** (change to the directory of the application)
7. **```code .```** (open the project)
8. **```ng serve -o```** (run the application the flag -o open the browser on transpile code to JS)
9. See default Angular application

# Flow inside Angular application [↑](#table-of-contents)
1. Main.js in promise **```platformBrowserDynamic().bootstrapModule(AppModule)
  .catch(err => console.error(err));```** call the Root module AppModule of my application
2. App.module.ts under the decorator **```@NgModule```** call in bootstrap array the  Root Component AppComponent
3. Components are subdivide in:
    - app.component.ts: Define the JS and call app.component.css and app.component.html templates. IT's the minimun file required for a functional component if declare template and styles (not needed).
      - Minimun component with '' only one line for template and style
      ``` js
      import { Component } from '@angular/core';

      @Component({
        selector: 'app-root',
        template: '<h1>Hello World</h1>',
        styles: [ ' h1 {color: red} ']
      })
      export class AppComponent {
        title = 'my-first-app';
      }
      ```
      - Minimun component with ` multiline for template and style

      ``` js
      import { Component } from '@angular/core';

      @Component({
        selector: 'app-root',
        template: `<h1>Hello World</h1>
                   <p>Text</p>`,
        styles: [ ` h1 {color: red}
                    p { color: blue } `]
      })
      export class AppComponent {
        title = 'my-first-app';
      }
      ```
    - If use templateUrl: [] and styleUrls: [] in component needs

      ``` js
        import { Component } from '@angular/core';

        @Component({
          selector: 'app-root',
          templateUrl: './app.component.html',
          styleUrls: [ './app.component.css']
        })
        export class AppComponent {
          title = 'my-first-app';
        } 
      ```
      - app.component.css: Define the styles of component
      - app.component.html: Define the structure of component
    - app.component.spec.ts: Define test of the component

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

# Change compact folder configuration in VSC  [↑](#table-of-contents)
1. Go to File > Preferences > Features & Uncheck compact folders
