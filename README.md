# Situ-Theme

This package is used to apply the Situ theme to a project.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

This package requires that bootstrap is install

```
npm install --save bootstrap
```

And if you plan on using angular material, you should install angular material

```
npm install --save @angular/material
```

### Installing

To install this package, simply run this command

```
npm install --save @situlive/situ-theme
```

Once this is done, you need to configure your project for either bootstrap or angular material

## Bootstrap only

If you are only running bootstrap, then in your `style.scss` import the boostrap sass file:

```
@import "~@situlive/situ-theme/sass/situ-bootstrap-theme";
```

This will also import the require bootstrap styles.

## Angular material

If you are using angular material, then you need to import the material theme:

```
@import "~@situlive/situ-theme/sass/situ-material-theme";
```

This still requires bootstrap, but will only import these bootstrap styles:

```
@import "~bootstrap/scss/functions";
@import "~bootstrap/scss/variables";
@import "~bootstrap/scss/mixins";
@import "~bootstrap/scss/reboot";
@import "~bootstrap/scss/grid";
@import "~bootstrap/scss/utilities";
```

Which gives you access to the grid system aswell as the utlity classes like `mb-0` and `d-flex`, etc.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/situlive/situ-theme/tags).

## Authors

- **Jaymie Jeffrey** - _Initial work_ - [Situ Live](https://github.com/situlive)

See also the list of [contributors](https://github.com/situlive/situ-theme/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details
