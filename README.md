<p align="center">
	<a href="https://opensource.org/licenses/MIT" target="_blank">
        <img src="https://img.shields.io/github/license/industriousone/industrious-redux" alt="MIT" />
    </a>
    <a href="https://twitter.com/industrious" target="_blank">
        <img src="https://img.shields.io/twitter/follow/industrious.svg?style=social&label=Follow">
    </a>
</p>

# Industrious.Redux

**A predictable state container for .NET applications, following the [Redux][rdx] model.**

**Industrious.Redux** is a [.NET Standard 2.0](https://docs.microsoft.com/en-us/dotnet/standard/net-standard) project which should build and run anywhere you can .NET. I have not yet published a NuGet package for it; I'd like to get collection support, more documentation, and another example or two into place first.

At the time of this writing, all of the core concepts are in place and ready to go: stores, reducers, actions, and observers. Only one example is currently provided, though more are on the way:

- [Counter](tree/master/Examples.Counter) implements the [canonical Redux counter example](https://github.com/reduxjs/redux/tree/master/examples/counter-vanilla), and provides the simplest introduction to working with Redux concepts

The examples use [Xamarin.Forms](https://docs.microsoft.com/en-us/xamarin/xamarin-forms/) and currently include targets for iOS and Android.

## Stay in touch

- Website - https://industriousone.com/
- Twitter - [@industrious](https://twitter.com/industrious)

## License

[MIT](https://opensource.org/licenses/MIT)

## Credits

- [@dan_abramov](https://twitter.com/dan_abramov) and the [Redux][rdx] project
- [@guillaume_slls](https://twitter.com/guillaume_slls) and the [Redux.NET](rnt) project
- [@dcolthorp](https://twitter.com/dcolthorp) and [Atomic Object](https://atomicobject.com) for [the "projections" concept](prj)


[rdx]: https://redux.js.org
[rnt]: https://github.com/GuillaumeSalles/redux.NET
[prj]: https://spin.atomicobject.com/2017/03/13/adapting-redux-c-sharp-xamarin/
