# Lighthouse Tests

This is a tool using Lighthouse to test all the pages in a list of sites and save the results in a MongoDB database.

## Dependencies and installation

You'll need node.js https://nodejs.org/en/download/

Then, install the Lighthouse API with

```bash
npm i lighthouse
```

Finally, you'll need to make a config.json with the following keys:<br/><br/>
"uri" (the location of your MongoDB, )<br/><br/>
"SITE_LIST" (an array of strings, each being a site with a sitemap)<br/><br/>
"LIGHTHOUSE_OPTS"<br/><br/>
"SITEMAP_OPTS" (optional; you don't need this if your sitemaps are located at /sitemap.xml)

Example of LIGHTHOUSE_OPTS (feel free to use this example):

    {
        chromeFlags: ["--headless"],
        onlyAudits: [
          "first-contentful-paint",
          "first-meaningful-paint",
          "speed-index",
          "first-cpu-idle",
          "dom-size",
          "estimated-input-latency",
          "network-payload",
          "legible-font-sizes",
          "performance-info",
          "accessibility-info",
          "best-practices-info",
          "seo-info",
          "pwa-info"
        ]
    }

To learn more, see:<br/><br/>
https://github.com/GoogleChrome/lighthouse/blob/master/docs/readme.md#using-programmatically <br/><br/>
https://github.com/GoogleChrome/lighthouse/blob/888bd6dc9d927a734a8e20ea8a0248baa5b425ed/typings/externs.d.ts#L82-L119

## Usage
Navigate with the command line to the src folder, then run
```bash
node index.js
```