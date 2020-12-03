# Situ-Theme

This package is used to apply the Situ theme to a project.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

This package requires that bootstrap and angular material is installed

```
npm install --save bootstrap-scss @angular/material
```

### Installing

To install this package, simply run this command

```
npm install --save @situlive/situ-theme
```

You can then import the theme directly into your application:

```
@import "~@situlive/situ-theme/sass/situ-theme";
```

Once imported, it will import and configure angular material and import the unitility styles for bootstrap:

```
@import "~bootstrap-scss/functions";
@import "~bootstrap-scss/variables";
@import "~bootstrap-scss/mixins";
@import "~bootstrap-scss/reboot";
@import "~bootstrap-scss/grid";
@import "~bootstrap-scss/utilities";
```

Which gives you access to the grid system aswell as the utlity classes like `mb-0` and `d-flex`, etc.

### Usage

To use the situ theme, import your variables and overrides first:

```
@import "./variables"; // Your application variables

$situ-font-path: "~@situlive/situ-theme/fonts";
```

And then import the theme:

```
@import "~@situlive/situ-theme/sass/situ-theme";
```

Then you can the core mixin:

```
@include core();
```

Your styles.scss should look something like this:

```
@import "./variables"; // Your application variables

$situ-font-path: "~@situlive/situ-theme/fonts";

@import "~@situlive/situ-theme/sass/situ-theme";
@include core();

@import "./components"; // Your application components

```

---

In some cases you may want to completely overhall the fonts, in that case you can just call the create-theme mixin and omit the core include:

```
@include create-theme();
```

### Performance

When using in angular universal applications, you may need to preload the fonts.
While the above version is the easiest to setup, a more preffered way would be to copy the fonts to your assets directory (so that they retain their original names when build --prod is used) and then add the following to your index.html head section:

```
<link rel="preload" href="/assets/fonts/euclidtriangle-semibold.woff2" as="font" crossorigin="anonymous">
```

This will ensure the fonts are preloaded and won't affect performance.
To copy the fonts over to your assets folder, open your angular.json and paste the following into the assets section:

```
{
  "glob": "*.woff2",
  "input": "./node_modules/@situlive/situ-theme/fonts",
  "output": "./assets"
}
```

The whole section might look something like this:

```
"assets": [
  "src/robots.txt",
  "src/web.config",
  "src/assets",
  {
    "glob": "*.woff2",
    "input": "./node_modules/@situlive/situ-theme/fonts",
    "output": "./assets"
  }
],
```

Once you have followed these steps, change your font path in your styles.scss to this:

```
@import "./variables"; // Your application variables

$situ-font-path: "/assets/fonts";

@import "~@situlive/situ-theme/sass/situ-theme";
@include core();

@import "./components"; // Your application components

```

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/situlive/situ-theme/tags).

## Authors

- **Jaymie Jeffrey** - _Initial work_ - [Situ Live](https://github.com/situlive)

See also the list of [contributors](https://github.com/situlive/situ-theme/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details
