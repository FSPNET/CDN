# Telescopium

![Uptime status](https://img.shields.io/uptimerobot/status/m781676682-63e6c6681418d666efe2478c.svg?style=flat-square)
![Uptime status 7 days](https://img.shields.io/uptimerobot/ratio/7/m781676682-63e6c6681418d666efe2478c.svg?style=flat-square)

A free static resources and open source software reverse proxy and mirror.

We provides mirrors for [cdnjs](https://github.com/cdnjs/cdnjs), npm, GitHub, WordPress plugins, Steam CDN, Steam API and custom endpoints for several other projects with special requirements.

## Feature

All of our endpoints support HTTP2 offering better performance to all users.

- `cdn.addones.org`
    
    provides mirrors for cdnjs, npm, GitHub, WordPress plugins.
- `steamcdn.addones.org`

    provides mirrors for Steam Images.

- `steamapi.addones.org`

    provides mirrors for Steam Web API.

### cdnjs

This is [cdnjs](https://github.com/cdnjs/cdnjs) reverse proxy service. we can support the rapid loading of the world.

You can replace `cdnjs.cloudflare.com/ajax/libs` to `cdn.addones.org` like this:

before:
```
cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/4.1.1/css/bootstrap.min.css
```

after:
```
cdn.addones.org/twitter-bootstrap/4.1.1/css/bootstrap.min.css

or

cdn.addones.org/bootstrap/4.1.1/css/bootstrap.min.css
```

> For now only twitter-bootstrap can rewrite to bootstrap.
>
> If you want to support rewrite more libraries you can [new issues](https://github.com/FSPNet/cdn/issues/new).
>
> If you want to add a library please [new issues](https://github.com/cdnjs/cdnjs/issues/new) in CDNJS,
> when your request is approved for review, you can use it immediately on the `cdn.addones.org`
>
> Thank you 💓

### npm CDN

We can instantly serve any file from any npm package in the public registry.

New versions pushed to npm are instantly available via our CDN as well. No maintenance is required.

If a package, version or file gets removed from npm then Telescopium will continue to serve that file from our permanent storage without breaking any websites using it. 

Load any project hosted on npm:

```
/npm/package@version/file
```

Load exact version:

```
/npm/jquery@3.1.0/dist/jquery.min.js
```

Use a version range instead of an exact version:

```
/npm/jquery@3/dist/jquery.min.js
/npm/jquery@3.1/dist/jquery.min.js
```

Load by tag: (Not recommended for production usage)

```
/npm/jquery@beta/dist/jquery.min.js
```

Omit the version completely or use "latest" to load the latest one: (Dev environment only)

```
/npm/jquery@latest/dist/jquery.min.js
/npm/jquery/dist/jquery.min.js
```

Add ".min" to any JS/CSS file to get a minified version - if one doesn't exist, we'll generate it for you. All generated files come with source maps and can be easily used during development:

```
/npm/github-markdown-css@2.4.1/github-markdown.min.css
```

Get a directory listing:

```
/npm/jquery@3.1.0/
/npm/jquery@3.1.0/dist/
```

### GitHub

Load any GitHub release, commit, or branch:

```
/gh/user/repo@version/file
```

Load exact version:

```
/gh/jquery/jquery@3.1.0/dist/jquery.min.js
/gh/jquery/jquery@32b00373b3f42e5cdcb709df53f3b08b7184a944/dist/jquery.min.js
```

Use a version range instead of an exact version (only works with valid semver versions):

```
/gh/jquery/jquery@3/dist/jquery.min.js
/gh/jquery/jquery@3.1/dist/jquery.min.js
```

Omit the version completely or use "latest" to load the latest one (only works with valid semver versions): (Dev environment only)

```
/gh/jquery/jquery@latest/dist/jquery.min.js
/gh/jquery/jquery/dist/jquery.min.js
```

Add ".min" to any JS/CSS file to get a minified version - if one doesn't exist, we'll generate it for you. All generated files come with source maps and can be easily used during development:

```
/gh/sindresorhus/github-markdown-css@v2.4.1/github-markdown.min.css
```

Get a directory listing:

```
/gh/jquery/jquery@3.1.0/
/gh/jquery/jquery@3.1.0/dist/
```

### Combine multiple files

Our combine endpoint has the following format:

```
/combine/url1,url2,url3
```

All features that work for individual files (version ranges, minification, main modules) work here as well. All combined files come with source maps and can be easily used during development.

Examples:

```
/combine/gh/jquery/jquery@3.1/dist/jquery.min.js,gh/twbs/bootstrap@3.3/dist/js/bootstrap.min.js
/combine/npm/bootstrap@3.3/dist/css/bootstrap.min.css,npm/bootstrap@3.3/dist/css/bootstrap-theme.min.css
```

### WordPress

Our WordPress endpoint works for plugins hosted in the [WordPress.org plugin directory](https://WordPress.org/plugins), and mirrors [the WordPress.org plugins SVN repo](https://plugins.svn.wordpress.org/) has the following format:

```
/wp/project/tags/version/file
```

Load exact version:

```
/wp/wp-slimstat/tags/4.6.5/wp-slimstat.js
```

Load latest version:  (Dev environment only)

```
/wp/wp-slimstat/trunk/wp-slimstat.js
```

### Steam 

#### Images 

You can use [Replace Steam CDN](https://github.com/teakowa/Replace-Steam-CDN)

> For now we can only support the fast loading of image resources.

#### Web API

This is [Steam Web API](https://developer.valvesoftware.com/wiki/Steam_Web_API) reverse proxy service. we can support the rapid loading of the world.

You can replace `api.steampowered.com` to `steamapi.addones.org` like this:

before:
```
api.steampowered.com/ISteamApps/GetAppList/v2
```

after:
```
steamapi.addones.org/ISteamApps/GetAppList/v2
```

---

And we also support a proxy for the store API. 

You can replace `store.steampowered.com/api` to `steamapi.addones.org/api` like this:

before:
```
store.steampowered.com/api/appdetails/?appids=839500&cc=CN&l=Chinese&v=1
```

after:
```
steamapi.addones.org/api/appdetails/?appids=839500&cc=CN&l=Chinese&v=1
```

### Google

* `fonts.gstatic.com` => `fonts.addones.org`
* `fonts.googleapis.com` => `fonts.addones.org/css`
* `secure.gravatar.com` => `gravatar.addones.org`

## Privacy Policy

- cdn.addones.org
- ajax.addones.org
- fonts.addones.org
- gravatar.addones.org
- steamcdn.addones.org
- steamapi.addones.org

Telescopium might use information about downloaded files to build download stats per project and per file.

Telescopium does not store any user data and does not track any users in any way.

Here are the relevant policies of our CDN providers:

- [Cloudflare](https://www.cloudflare.com/security-policy/)
- [jsDelivr](https://www.jsdelivr.com/privacy-policy-jsdelivr-net)

Enjoy 💓

---
