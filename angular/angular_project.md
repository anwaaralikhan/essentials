## Workspace file(s)


File name  | Reason(s)
------------- | -----------
package.json	| Configures npm package dependencies that are available to all projects in the workspace.
angular.json  | CLI configuration defaults for all projects in the workspace, including configuration options for build, serve, and test tools that the CLI uses, such as TSLint, Karma, and Protractor.
tsconfig.json |	Default TypeScript configuration for apps in the workspace, including TypeScript and Angular template compiler options.

## Environment.ts
```
..
├── environment.ts (default dev)
├── environment.prod.ts
├── environment.test.ts
.
.
```
By default is dev. How to build for a specific environment.
```
#build
$ ng build --environment=production
#shorthand
$ ng b -prod

#serve
$ ng serve --environment=production
#shorthand
$ ng s -prod
```

## Adding additional environments - not yet supported
If there are additional environments your build process needs to support, you can add more files to the /environments folder with the name of said environment such as environment.qa.ts and then use.

```#build
$ ng build --environment=environment
```
~~One drawback here is there is no -qa shorthand supported. Although the file is picked up by the CLI, there is a bug that the environments supported are only **prod or dev~~

Adding a "qa" environment.
Create a new file called environment.qa.ts in the /environment folder with the following contents:
```
export const environment = {  
  production: false,
  envName: 'qa'
};
```
Add the qa entry to the **.angular.cli.json** config:
```
  "environments": {
    "dev": "environments/environment.ts",
    "prod": "environments/environment.prod.ts",
    "qa": "environments/environment.qa.ts"
  }
```
Now the new environment is ready to use.

# angular_commands daily usage

**Install Angular CLI**

`npm install -g @angular/cli`

**Create new Angular Project**

`ng new hello_world_app`

**Start Angular Project**
> move to the project directory where package.json resides.

`ng serve`

**Run Multiple NPM Scripts in Parallel**

```
Use a package called concurrently.

npm i concurrently --save-dev

Then setup your npm run dev task as so:

"dev": "concurrently --kill-others \"npm run start-watch\" \"npm run wp-server\""
```
