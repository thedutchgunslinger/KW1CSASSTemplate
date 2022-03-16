# KW1C Sass Workshop Template
In deze les gaan we kijken hoe we met met sass kunnen werken. Hiervoor moeten we eerst node installeren. 
Doormiddel van node kunnen we sass installeren in ons project, ook zetten we er een live browser sync erin en een auto prefixer.

# Wat is:
## het doel van deze les?
Aan het einde van de les kunnen jullie sass installeren en gebruiken. 
## node?
Node is een javascript runtime die je kunt gebruiken om javascript code te downloaden.
## sass?
Sass is een preprocesor die je kunt gebruiken om je css te maken. het ondersteund meer functionalieteit en logica dan normale css.
## live browser sync?
Live browser sync is een tool die je kunt gebruiken om je css te laten zien in de browser zodra je iets hebt gewijzigd.
## autoprefixer?
Autoprefixer is een tool die je kunt gebruiken om automatisch de browser prefixes te zetten als je klaar bent met je project.

# Hoe installeer ik sass?
## stap 1
eerst moeten we node installeren. Dit kan je via deze link doen: [node.js](https://nodejs.org/en/).
## stap 2
Nu we node hebben moeten we een specifieke mappen structuur hebben. deze ziet er als volgt uit: 
```
└───src
|   ├───assets
|   └───sass
|   |   └───styles.scss
|   └───index.html
└───package.json
```

## stap 3
In de package.json zetten we deze code:
```	
{
  "name": "project",
  "version": "0.1.0",
  "description": "SASS compile|autoprefix|minimize and live-reload dev server using Browsersync for static HTML",
  "main": "public/index.html",
  "author": "Noah Beij",
  "scripts": {
    "build:sass": "sass  --no-source-map src/sass:public/css",
    "copy:html": "copyfiles -u 1 ./src/*.html public",
    "copy:assets": "copyfiles -u 1 ./src/assets/**/* public",
    "copy": "npm-run-all --parallel copy:*",
    "watch:html": "onchange \"src/*.html\" -- npm run copy:html",
    "watch:assets": "onchange \"/src/assets/**/*\" -- npm run copy:assets",
    "watch:sass": "sass  --no-source-map --watch src/sass:public/css",
    "watch": "npm-run-all --parallel watch:*",
    "serve": "browser-sync start --server public --files public",
    "start": "npm-run-all copy --parallel watch serve",
    "build": "npm-run-all copy:html build:*",
    "postbuild": "postcss public/css/*.css -u autoprefixer cssnano -r --no-map"
  },
  "dependencies": {
    "autoprefixer": "^10.4.2",
    "browser-sync": "^2.27.7",
    "copyfiles": "^2.4.1",
    "cssnano": "^5.0.17",
    "npm-run-all": "^4.1.5",
    "onchange": "^7.1.0",
    "postcss-cli": "^9.1.0",
    "sass": "^1.49.8"
  }
}
```
## stap 4

Nu we onze code erin hebben staan open we ```src``` map in de terminal. 

In de terminal runnen we de command:
```
npm install
```
Nu zal node alle benodigde packages installeren.

## stap 5

Alles is nu geinstaleerd, en we kunnen nu sass gebruiken. om een live server met sass te starten runnen we de command in de terminal:
```
npm run start
```

Happy coding!

# Waar kan ik meer leren over sass?
- [Sass Docs](https://sass-lang.com/documentation)
- [Sass crash course](https://www.youtube.com/watch?v=nu5mdN2JIwM)
- [Sass introduction](https://www.youtube.com/watch?v=Zz6eOVaaelI)
- [Sass full course](https://www.youtube.com/watch?v=_a5j7KoflTs)

# vragen?
Als je ergens niet uit komt kun je me altijd je vraag mailen. Je kan me bereiken via: n.beij@kw1c.nl
