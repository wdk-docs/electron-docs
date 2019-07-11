angular-electron
==================

|Angular Logo|
|Electron Logo|

|Travis Build Status|
|Dependencies Status|
|Make a pull request|
|License|

|Watch on GitHub|
|Star on GitHub|
|Tweet|



Bootstrap and package your project with Angular 8 and Electron (Typescript + SASS + Hot Reload) for creating Desktop applications.

Currently runs with:

-  Angular v8.0.0
-  Electron v5.0.2
-  Electron Builder v20.41.0

With this sample, you can :

-  Run your app in a local development environment with Electron & Hot reload
-  Run your app in a production environment
-  Package your app into an executable file for Linux, Windows & Mac

Angular 8.0 CLI needs Node 10.9 or later to work.

Getting Started
---------------

Clone this repository locally :

.. code:: bash

   git clone https://github.com/maximegris/angular-electron.git

Install dependencies with npm :

.. code:: bash

   npm install

There is an issue with ``yarn`` and ``node_modules`` that are only used
in electron on the backend when the application is built by the
packager. Please use ``npm`` as dependencies manager.

If you want to generate Angular components with Angular-cli , you
**MUST** install ``@angular/cli`` in npm global context. Please follow
`Angular-cli documentation <https://github.com/angular/angular-cli>`__
if you had installed a previous version of ``angular-cli``.

.. code:: bash

   npm install -g @angular/cli

To build for development
------------------------

-  **in a terminal window** -> npm start

Voila! You can use your Angular + Electron app in a local development
environment with hot reload !

The application code is managed by ``main.ts``. In this sample, the app
runs with a simple Angular App (http://localhost:4200) and an Electron
window. The Angular component contains an example of Electron and NodeJS
native lib import. You can disable “Developer Tools” by commenting
``win.webContents.openDevTools();`` in ``main.ts``.

Included Commands
-----------------

+------------------------------+---------------------------------------------------------------------------------------------------------------+
|           Command            |                                                  Description                                                  |
+==============================+===============================================================================================================+
| ``npm run ng:serve:web``     | Execute the app in the browser                                                                                |
+------------------------------+---------------------------------------------------------------------------------------------------------------+
| ``npm run build``            | Build the app. Your built files are in the /dist folder.                                                      |
+------------------------------+---------------------------------------------------------------------------------------------------------------+
| ``npm run build:prod``       | Build the app with Angular aot. Your built files are in the /dist folder.                                     |
+------------------------------+---------------------------------------------------------------------------------------------------------------+
| ``npm run electron:local``   | Builds your application and start electron                                                                    |
+------------------------------+---------------------------------------------------------------------------------------------------------------+
| ``npm run electron:linux``   | Builds your application and creates an app consumable on linux system                                         |
+------------------------------+---------------------------------------------------------------------------------------------------------------+
| ``npm run electron:windows`` | On a Windows OS, builds your application and creates an app consumable in windows 32/64 bit systems           |
+------------------------------+---------------------------------------------------------------------------------------------------------------+
| ``npm run electron:mac``     | On a MAC OS, builds your application and generates a ``.app`` file of your application that can be run on Mac |
+------------------------------+---------------------------------------------------------------------------------------------------------------+

**Your application is optimised. Only /dist folder and node dependencies are included in the executable.**

You want to use a specific lib (like rxjs) in electron main thread ?
--------------------------------------------------------------------

You can do this! Just by importing your library in npm dependencies (not
devDependencies) with ``npm install --save``. It will be loaded by
electron during build phase and added to the final package. Then use
your library by importing it in ``main.ts`` file. Easy no ?

Browser mode
------------

Maybe you want to execute the application in the browser with hot reload
? You can do it with ``npm run ng:serve:web``. **Note that you can’t use
Electron or NodeJS native libraries in this case.** Please check
``providers/electron.service.ts`` to watch how conditional import of
electron/Native libraries is done.

Branch & Packages version
-------------------------

-  Angular 4 & Electron 1 : Branch `angular4 <https://github.com/maximegris/angular-electron/tree/angular4>`__
-  Angular 5 & Electron 1 : Branch `angular5 <https://github.com/maximegris/angular-electron/tree/angular5>`__
-  Angular 6 & Electron 3 : Branch `angular6 <https://github.com/maximegris/angular-electron/tree/angular6>`__
-  Angular 7 & Electron 3 : Branch `angular7 <https://github.com/maximegris/angular-electron/tree/angular7>`__
-  Angular 8 & Electron 5 : (master)

.. |Angular Logo| image:: https://www.vectorlogo.zone/logos/angular/angular-icon.svg
   :target: https://angular.io/
.. |Electron Logo| image:: https://www.vectorlogo.zone/logos/electronjs/electronjs-icon.svg
   :target: https://electronjs.org/
.. |Travis Build Status| image:: https://travis-ci.org/maximegris/angular-electron.svg?branch=master
   :target: https://travis-ci.org/maximegris/angular-electron
.. |Dependencies Status| image:: https://dependencyci.com/github/maximegris/angular-electron/badge
   :target: https://dependencyci.com/github/maximegris/angular-electron
.. |Make a pull request| image:: https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square
   :target: http://makeapullrequest.com
.. |License| image:: http://img.shields.io/badge/Licence-MIT-brightgreen.svg
   :target: LICENSE.md
.. |Watch on GitHub| image:: https://img.shields.io/github/watchers/maximegris/angular-electron.svg?style=social
   :target: https://github.com/maximegris/angular-electron/watchers
.. |Star on GitHub| image:: https://img.shields.io/github/stars/maximegris/angular-electron.svg?style=social
   :target: https://github.com/maximegris/angular-electron/stargazers
.. |Tweet| image:: https://img.shields.io/twitter/url/https/github.com/maximegris/angular-electron.svg?style=social
   :target: https://twitter.com/intent/tweet?text=Check%20out%20angular-electron!%20https://github.com/maximegris/angular-electron%20%F0%9F%91%8D
