# All-In-One Vidsrc & Eporner Api / Resolver

This Express Application will when deployed :

- Run the vidsrc key extractor once when first started and then every 2 hours
- This project does not depend on github key extractors and uses the locally created keys.
- Resolve Vidsrc videos using a TMDB Id and also provide subtitles.
- Has an Eporner api wrapper and an Eporner Embed Resolver which returns multiple qualities.

## # Installation

To install locally or on any vps/dedicated server do the following :

`git clone https://github.com/Inside4ndroid/AIO-StreamSource.git`

`cd AIO-StreamSource`

`npm install`

`npm run main`

or you can Deploy to Vercel :

### Vercel

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2FInside4ndroid%2FAIO-StreamSource)

## # Usage

To use the api you need to know the routes here is a break down of all the routes and options etc.

all routes return json.

## # VIDSRC

```http://localhost:3000/vidsrc/tmdbid``` : 
```This resolves and returns the video source and subtitles.```

## # EPORNER

### per_page is optional and can be a value of :

`1` to `1000`

### page is optional and can be a value of :

`1` to `1000000` but no more than `total_pages` received in response

### thumbsize is optionaland the valid values are :

`small`  - thumbnail size 190x152

`medium`  - thumbnail size 427x240

`big`  - thumbnail size 640x360

### order is optional and how results should be sorted. valid values are :

`latest` newest videos first

`longest` longest videos first

`shortest` shortest videos first

`top-rated` top rated videos first

`most-popular` most popular all time videos first

`top-weekly` most popular this week videos first

`top-monthly` most popular this month videos first

### gay is optional and the valid values are :

`0` gay content not included

`1` gay content included

`2` only gay content

### lq is otional and the valid otions are :

`0` low quality content not included

`1` low quality content included

`2` only low quality

## # EXAMPLES

This will return the default details of the video :

```http://localhost:3000/eporn/?id=epornerid?thumbsize=medium```

This will return the resolve video sources in multiple qualities :

```http://localhost:3000/eporn/?resolve=epornerid```

This will return the search results in line with your parameters :

```http://localhost:3000/eporn/?query=bbw&per_page=10&page=2&thumbsize=big&order=top-weekly&gay=1&lq=1```

This will return the predefined list of categories in the constants.js file :

```http://localhost:3000/eporn/cats```

