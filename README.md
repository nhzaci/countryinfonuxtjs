# Country.Info Static Website

> Home and about pages are not done up, search page has cards done up with a
potential call to image library if there is one to update banner pictures
of each country onto the card, but for now it's just a single static picture

> This static website done in nuxt.js with css done using the tailwind css framework
 talks to the restcountries.eu api to get information about each country 
presented in the search page. API doesn't have a way to limit the number
of objects per call so not able to do pagination 

## Build Setup

``` bash
# install dependencies
$ npm run install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm run start

# generate static project
$ npm run generate
```

For detailed explanation on how things work, check out [Nuxt.js docs](https://nuxtjs.org).
