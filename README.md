# Table of Contents:
- [Table of Contents:](#table-of-contents)
- [1. Starting with Angular ↑](#1-starting-with-angular-)
  - [1.0 ¿What it's Angular? ↑](#10-what-its-angular-)
  - [1.1 Install Angular ↑](#11-install-angular-)
  - [1.2 What is the angular version?](#12-what-is-the-angular-version)
  - [1.3 Creating the first angular project with Angular CLI ↑](#13-creating-the-first-angular-project-with-angular-cli-)
  - [1.4 Flow inside Angular application ↑](#14-flow-inside-angular-application-)
  - [1.5 Components parts: ↑](#15-components-parts-)
  - [1.6 Create Monorepo Workspace for save multiple projects in Angular ↑](#16-create-monorepo-workspace-for-save-multiple-projects-in-angular-)
  - [1.7 Angular extensions:](#17-angular-extensions)
  - [1.8 Create a component use Angular CLI ↑](#18-create-a-component-use-angular-cli-)
  - [1.9 Adding component ↑](#19-adding-component-)
  - [1.10 Git Hub asociate repository to my Project ↑](#110-git-hub-asociate-repository-to-my-project-)
  - [1.11 Git Hub push changes to repository GitHub ↑](#111-git-hub-push-changes-to-repository-github-)
  - [1.12 Change compact folder configuration in VSC  ↑](#112-change-compact-folder-configuration-in-vsc--)
  - [1.13 Install Bootstrap ↑](#113-install-bootstrap-)
- [2. Bindings with Angular ↑](#2-bindings-with-angular-)
  - [2.1 String Interpolation Moustached {{}} (Send data from Model to View) ↑](#21-string-interpolation-moustached--send-data-from-model-to-view-)
  - [2.2 Property Binding [property] (Send data from Model to View) ↑](#22-property-binding-property-send-data-from-model-to-view-)
  


# 1. Starting with Angular [↑](#table-of-contents)

## 1.0 ¿What it's Angular? [↑](#table-of-contents)
    - Created for Google
    - Framework JS for create SPA (Single Page Applications)
    - TypeScript (super set JS)
    - MVC Model View Controler
    - Architecture based in component

## 1.1 Install Angular [↑](#table-of-contents)
1. Download and install VSC and open terminal in VSC: Terminal > New Terminal or CNTL + Ñ
2. Download and install node.js (Recomended LTS version) and check **```node -v```** in VSC Terminal
3. Install Angular CLI **```npm install -g @angular/cli```** and check **```ng --version ```** in VSC Terminal

## 1.2 What is the angular version?

Since version 2 of Angular, Angular is spoken of as plain Angular (no version) because all angular versions are backward compatible.
However, most developolers speak about Angular with the versión 9, 10, 11... 
When check ng --version in the terminal. If angular it's install and running correctly, show Angular version (example 11.0.5). This numbers subdivide de version of Angular in three parts, for example:

      -   11   .  0  .  5  
      -   major.minor.patch

  - major release → Major releases contain significant new features. When you updating to a new major release, you may need to run update scripts, refactor code, run additional tests, and learn new APIs.
  - minor release → contain new smaller features. Minor releases are fully backward-compatible; no developer assistance is expected during update, but you can optionally modify your apps and libraries to begin using new APIs, features, and capabilities that were added in the release. We update peer dependencies in minor versions by expanding the supported versions, but we do not require projects to update these dependencies.
  - patch release → resolve bugs fix releases. No developer assistance is expected during update.

In general, you can expect the following release cycle:

  - A major release every 6 months
  - 1-3 minor releases for each major release
  - A patch release and pre-release (next or rc) build almost every week

## 1.3 Creating the first angular project with Angular CLI [↑](#table-of-contents)
1. Open terminal in VSC (Remember Terminal > New Terminal or CNTL + Ñ)
2. **```ng new```**
3. What name would you like to use for the application? my-first-app
4. Would you like to add Angular routing? **```N```** (for the moment)
5. Which stylesheet format would you like to use? (Use arrow keys) **```CSS```** (for the moment)
6. **```cd my-first-app```** (change to the directory of the application)
7. **```code .```** (open the project)
8. **```ng serve -o```** (run the application the flag -o open the browser on transpile code to JS)
9. See default Angular application

## 1.4 Flow inside Angular application [↑](#table-of-contents)
When angular project it's serve (with ng serve) the flow of a request inside Angular App it's:
1. Index.html (tradicional HTML but have tag of selector app-root)
      ``` html
      <!doctype html>
      <html lang="en">
      <head>
        <meta charset="utf-8">
        <title>MyFirstApp</title>
        <base href="/">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <link rel="icon" type="image/x-icon" href="favicon.ico">
      </head>
      <body>
        <app-root></app-root>
      </body>
      </html>
      ```
2. Main.js in promise **```platformBrowserDynamic().bootstrapModule(AppModule)
  .catch(err => console.error(err));```** call the Root module AppModule of my application
      ``` js
      import { enableProdMode } from '@angular/core';
      import { platformBrowserDynamic } from '@angular/platform-browser-dynamic';

      import { AppModule } from './app/app.module';
      import { environment } from './environments/environment';

      if (environment.production) {
        enableProdMode();
      }

      platformBrowserDynamic().bootstrapModule(AppModule)
        .catch(err => console.error(err));
      ```
3. App.module.ts under the decorator **```@NgModule```** call in bootstrap array [] the  Root Component AppComponent set of components that are bootstrapped when this module is bootstrapped
      ``` js
      import { BrowserModule } from '@angular/platform-browser';
      import { NgModule } from '@angular/core';

      import { AppComponent } from './app.component';

      @NgModule({
        declarations: [
          AppComponent
        ],
        imports: [
          BrowserModule
        ],
        providers: [],
        bootstrap: [AppComponent]
      })
      export class AppModule { }
      ```
4. Finally, the component Root App.component.ts run HTML, CSS & TS (transpilate to JS for to be understood with the browser) defines in the app.component.ts. For example:
      ``` js
      import { Component } from '@angular/core';

      @Component({
        selector: 'app-root',
        templateUrl: './app.component.html',
        styleUrls: ['./app.component.css']
      })
      export class AppComponent {
        title = 'my-first-app';
      }
      ```

## 1.5 Components parts: [↑](#table-of-contents)
Components are subdivide in:
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

## 1.6 Create Monorepo Workspace for save multiple projects in Angular [↑](#table-of-contents)

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

## 1.7 Angular extensions:
- **```Angular Snippets```** →  This extension adds snippets for Angular for TypeScript and HTML.
- **```Bracket Pair Colorizer```** → This extension allows matching brackets to be identified with colours.
- **```Auto Import```** → This extension automatically finds, parses and provides code actions and code completion for all available imports.

## 1.8 Create a component use Angular CLI [↑](#table-of-contents)
For create component use:
1. Complete form:    **```ng generate component name-component ```**
2. Abreviated form:  **```ng g        c         name-component ```**

## 1.9 Adding component [↑](#table-of-contents)
For call component in HTML file:
1. Go to the selector atribute located in the file **```nameComponent.component.ts```** and copy the value
2. Paste the selector in other component HTML **```<app-component-name></app-component-name>```**

## 1.10 Git Hub asociate repository to my Project [↑](#table-of-contents)
1. Go to gitHub page and create repository New > write RepositoryName (ex. workspace-angular) and push Create Repository
2. **```git remote add origin URL```** URL example https://github.com/yourUserNameGit/yourRepositoryName.git
3. **```git branch -M main```**
4. **```git push -u origin main```**

## 1.11 Git Hub push changes to repository GitHub [↑](#table-of-contents)
1. make changes in repository (Working Directory → WD)
2. **```git status```** (for see the changes in WD)
3. **```git add .```** (for add all changes of WD to Staging Area → SA) or **```git add file```** (for add only one file of WD to SA)
4. **```git status```** (for verify files added to SA)
5. For unstage file added to WD for SA **```git restore --staged <file>```**
6. **```git commit -m "description commit message"```** (for save SA files in Local Repository → LR)
7. **```git push```** (for upload files to LR to Remote Repository RR) RR = GitHub Repository

## 1.12 Change compact folder configuration in VSC  [↑](#table-of-contents)
1. Go to File > Preferences > Features & Uncheck compact folders

## 1.13 Install Bootstrap [↑](#table-of-contents)
1. Install dependencies requerid for Bootstrap works correctly;
     - **```npm install bootstrap```**
     - **```npm install jquery```**
     - **```npm install popper.js```**
2. Go to the file angular.json and search depedendies boostrap, jquery, popper.js in node_modules and adding in styles and scripts the files:
      ``` json
        "build": {
          "builder": "@angular-devkit/build-angular:browser",
          "options": {
            "styles": [
              "src/styles.css",
              "./node_modules/bootstrap/dist/css/bootstrap.min.css"
            ],
            "scripts": [
              "./node_modules/jquery/dist/jquery.min.js",
              "./node_modules/popper.js/dist/umd/popper.min.js",
              "./node_modules/bootstrap/dist/js/bootstrap.min.js"
            ]
          },
      ```
3. For run jquery code **```npm i @types/jquery```** and go to the file **```tsconfig.app.json```** and adding in types of compilerOptions **```"jquery"```**
      ``` json
      /* To learn more about this file see: https://angular.io/config/tsconfig. */
      {
        "extends": "./tsconfig.json",
        "compilerOptions": {
          "outDir": "./out-tsc/app",
          "types": ["jquery"]
        },
        "files": [
          "src/main.ts",
          "src/polyfills.ts"
        ],
        "include": [
          "src/**/*.d.ts"
        ]
      }
      ```
4. Go to app.component.ts and add **```constructor(){$(() => { alert('ready!'); });}```**
      ``` js
      import { Component } from '@angular/core';

      @Component({
        selector: 'app-root',
        templateUrl: './app.component.html',
        styleUrls: ['./app.component.css']
      })
      export class AppComponent {
        title = 'my-app';
        constructor(){$(() => { alert('ready!'); });}
      }
      ```
5. Add in template.component.html:
      ``` html
        <div class="alert alert-success" role="alert">
          Testing template Bootstrap
        </div>
      ```
6. Open the app and check alert (jQuery) appear in the browser and div have a format green

# 2. Bindings with Angular [↑](#table-of-contents)
## 2.1 String Interpolation Moustached {{}} (Send data from Model to View) [↑](#table-of-contents)
in the component.ts file add:
``` js 
  greeting = 'Hello';
```
in the component.html file add:
``` html 
  <h1>{{greeting}}</h1>
```

If the var declared private in the component.ts:
``` js 
  private greeting = 'Hello';
```
You need add a getter
``` js 
  private title = 'my-app';

  getTitle(): string{
    return this.title;
  }
  // Set not required for the moment
  setTitle(title: string): void{
    this.title = title;
  }
```
And in the component.html file add the getter for print the title:
``` html 
  <h1>{{getTitle()}}</h1>
```

Under the string interpolation I can make operations for example:
``` html 
  <h1>{{1 + 1}}</h1>
```

## 2.2 Property Binding [property] (Send data from Model to View) [↑](#table-of-contents)
In default HTML disabled button code are:
``` html 
  <button class="btn btn-primary" disabled>Add</button>
```
If I like controller the disabled property of this button in the template component:
1. First, I created the property
``` js 
  isDisabled = true;
```
2. Second, use the property binding
``` html 
  <button class="btn btn-primary" [disabled]="isDisabled">Add</button>
```
3. Check the button (it's disabled)
4. Change the value of isActive for true
``` js 
  isDisabled = false;
```
5. Check the button (it's active)

Other example more dinamic its adding a setTimeOut function change status in 3000 miliseconds (3 seconds):
  ``` js 
  isActive = false;

  constructor() {
    setTimeout(() => (this.isActive = !this.isActive), 3000);
  }
```
