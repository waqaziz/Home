# Getting Started with ASP.NET 5 and DNX

This guide is designed to get you started building applications with the latest development versions ASP.NET 5 and DNX. This means nightly builds and potentially broken or unstable packages.

If you want a more stable, released, experience then you should go to http://www.asp.net/vnext.

## What you need

The key part of working with development feeds is getting your environment set up so that you can acquire and switch to new builds of the DNX. Once you have that then it is just a matter of pulling the latest packages from the development MyGet feed.

In order to be able to get new builds of the DNX, and switch between them, you need to get the .NET Version Manager (DNVM) command line tool.

## Getting Started

There are getting started guides for Windows, Mac OS X and Linux on the [ASP.NET Documentation Site](http://docs.asp.net). We suggest installing and using the .NET Version Manager (DNVM) to allow you to manage multiple different versions of the DNX. Instructions for installing DNVM are provided on the relevant Getting Started pages on the documentation site:

* [Windows](http://docs.asp.net/en/latest/getting-started/installing-on-windows.html)
* [Mac OS X](http://docs.asp.net/en/latest/getting-started/installing-on-mac.html)
* [Linux](http://docs.asp.net/en/latest/getting-started/installing-on-linux.html)

# Running an application

Now that you have DNVM, you need to use it to download a DNX to run your applications with:

```
dnvm upgrade
```

> DNVM has the concept of a stable and unstable feed. Stable defaults to NuGet.org while unstable defaults to our dev MyGet feed. So if you add `-u` or `-unstable` to any of the install or upgrade commands you will get our latest CI build of the DNX instead of the one last released on NuGet.

DNVM works by manipulating your path. When you install a runtime it downloads it and adds the path to the dnx binary to your `PATH`. After doing upgrade you should be able to run `dnvm list` and see an active runtime in the list.

You should also be able to run `dnx` and see the help text of the `dnx` command.

## Running the samples

1. Clone the ASP.NET 5 Home repository: https://github.com/aspnet/home
2. Change directory to the folder of the sample you want to run
3. Run ```dnu restore``` to restore the packages required by that sample.
4. You should see a bunch of output as all the dependencies of the app are downloaded from MyGet.
5. Run the sample using the appropriate DNX command:
    - For the console app run  `dnx . run`.
    - For the web apps run `dnx . web` on Windows or `dnx . kestrel` on OS X/Linux.
6. You should see the output of the console app or a message that says the site is now started.
7. You can navigate to the web apps in a browser by navigating to `http://localhost:5001` or `http://localhost:5004` if running on OS X/Linux.

# Documentation and Further Learning

## [Community Standup](http://www.youtube.com/playlist?list=PL0M0zPgJ3HSftTAAHttA3JQU4vOjXFquF)
The community standup is held every week and streamed live to YouTube. You can view past standups in the linked playlist.

If you have questions you can also jump online during the next standup and have them answered live.

## [Wiki Documentation](https://github.com/aspnet/Home/wiki)
We have some useful documentation on the wiki of this Repo. This wiki is a central spot for docs from any part of the stack.

If you see errors, or want some extra content, then feel free to create an issue or send a pull request (see feedback section below).

## [ASP.NET/vNext](http://www.asp.net/vnext)
The vNext page on the ASP.NET site has links to some TechEd videos and articles with some good information about vNext.

## Repos and Projects

These are some of the most common repos:

* [DependencyInjection](https://github.com/aspnet/DependencyInjection) - basic dependency injection infrastructure and default implementation
* [EntityFramework](https://github.com/aspnet/EntityFramework) - data access technology
* [Identity](https://github.com/aspnet/Identity) - users and membership system
* [DNX](https://github.com/aspnet/DNX) - core runtime, project system, loader
* [MVC](https://github.com/aspnet/Mvc) - MVC framework for web apps and services
* [SignalR-Server](https://github.com/aspnet/SignalR-Server) - real-time

A description of all the repos is [here](https://github.com/aspnet/Home/wiki/Repo-List).

# Feedback

Check out the [contributing](CONTRIBUTING.md) page to see the best places to log issues and start discussions.

