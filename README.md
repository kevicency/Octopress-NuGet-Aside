# Octopress NuGet Aside

This is a simple aside for <a href="http://www.octopress.org">Octopress</a> that uses the Nuget Gallery API to dislay the most downloaded NuGet packages where you are an author. The loading time isn't that great currently because the NuGet Search API doesn't support JSON (JSONP) and returns all versions of every package. I also have to reroute the request using the [Google Feed API](https://developers.google.com/feed/v1/).

## Setup

First of all you need to these copy files:

* *nuget.html* into *source/_includes/custom/asides/*
* *nuget.js* into *source/javascripts/*
* *nuget_32_gray.png* into *source/images/*
* *nuget_32_gray_fail.png* into *source/images/*
* *_nuget.scss* into *sass/partials/sidebar/*

Then you need to update these file:

### _config.yml

* add *'custom/asides/nuget.html'* to *default_asides*
* add NuGet settings at the end of the file:

```
# NuGet packages
nuget_user: "your_username"
nuget_author: "your_author_name"
nuget_package_count: 5
```

The author is used for the search. This means that the author should equal the
author you put in your NuGet spec. Search by user is not possible.

### sass/partials/_sidebar.scss

* Add *'@import "sidebar/nuget";'* at the end of the file

## Preview

Check my [blog](http://kmees.github.com) for a preview.
