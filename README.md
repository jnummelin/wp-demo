
#

## Why yet-another-custom-wp-image (YACWPI)?

The official image does some things wonderfully and some things utterly "wrong" in my opinion.

Yes, it works pretty nicely when running a single container with docker-compose and manually updating plugins and things via the admin UI. But we're talking about running things with containers. Think about your CI/CD pipeline, how would you ensure your new plugin actually works? You certailnly don't go and do point-and-click installtion through the admin UI during the CI/CD process.

So I built another image, the main idea is:
- have everything bundled in the image itself, no copying WP stuff over during startup
- have our custom theme baked in
- startup script will run the installation "wizard", if not done already



## Running locally

### Post start

**Enable the theme**

```
www-data@42b83e362c09:~/html$ wp theme activate my-theme
```


## Running on cluster

