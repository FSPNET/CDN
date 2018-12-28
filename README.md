# Telescopium

A free static resources and open source software reverse proxy and mirror.

## Usage

### CDN

This is [cdnjs](https://github.com/cdnjs/cdnjs) reverse proxy service. we can support the rapid loading of the world.

You can replace `https://cdnjs.cloudflare.com/ajax/libs/` to `https://cdn.dawoea.net/` like this:

before:
```
https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/4.1.1/css/bootstrap.min.css
```

after:
```
https://cdn.dawoea.net/twitter-bootstrap/4.1.1/css/bootstrap.min.css

or

https://cdn.dawoea.net/bootstrap/4.1.1/css/bootstrap.min.css
```

> For now only twitter-bootstrap can rewrite to bootstrap.
>
> If you want to support rewrite more libraries you can [new issues](https://github.com/FSPNet/cdn/issues/new).
>
> If you want to add a library please [new issues](https://github.com/cdnjs/cdnjs/issues/new) in CDNJS,
> when your request is approved for review, you can use it immediately on the `cdn.dawoea.net`
>
> Thank you 💓

### Steam 

#### Images 

You can use [Replace Steam CDN](https://github.com/dawoea/Replace-Steam-CDN)

> For now we can only support the fast loading of image resources.

#### Web API

This is [Steam Web API](https://developer.valvesoftware.com/wiki/Steam_Web_API) reverse proxy service. we can support the rapid loading of the world.

You can replace `https://api.steampowered.com/` to `https://steamapi.addones.org/` like this:

before:
```
https://api.steampowered.com/ISteamApps/GetAppList/v2
```

after:
```
https://steamapi.addones.org/ISteamApps/GetAppList/v2
```

---

And we also support a proxy for the store API. 

You can replace `https://store.steampowered.com/api` to `https://steamapi.addones.org/api` like this:

before:
```
https://store.steampowered.com/api/appdetails/?appids=839500&cc=CN&l=Chinese&v=1
```

after:
```
https://steamapi.addones.org/api/appdetails/?appids=839500&cc=CN&l=Chinese&v=1
```

### Google

* `fonts.gstatic.com` => `fonts.dawoea.net`
* `fonts.googleapis.com` => `fonts.dawoea.net/css`
* `secure.gravatar.com` => `gravatar.dawoea.net`

## Privacy Policy

- cdn.dawoea.net
- ajax.dawoea.net
- fonts.dawoea.net
- gravatar.dawoea.net
- steamcdn.addones.org
- steamapi.addones.org

Telescopium might use information about downloaded files to build download stats per project and per file.

Telescopium does not store any user data and does not track any users in any way.

Here are the relevant policies of our CDN providers:

- [Cloudflare](https://www.cloudflare.com/security-policy/)

Enjoy 💓

---
