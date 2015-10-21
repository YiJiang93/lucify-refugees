# The flow of asylum seekers in Europe

A visualization of the flow of asylum seekers in European countries from 2012 onwards. Based on UNHCR data. See it in action [here](http://dev.lucify.com/the-flow-towards-europe/). For a more in-depth explanation, read [this blog post](https://medium.com/@lucify/a-novel-visualisation-of-the-refugee-crisis-565e40ab5a50).

This project uses a combination of [React](https://facebook.github.io/react/), [D3.js](http://d3js.org/) and [PIXI.js](http://www.pixijs.com/).


## Installation

### Dependencies

- Node + npm
- Ruby + [RubyGems](https://rubygems.org/pages/download)
- Bundler: `gem install bundler`
- GDAL: `brew install gdal`
- simplify-geojson: `npm install -g simplify-geojson`
- topojson: `npm install -g topojson`
- mocha (for running unit tests): `npm install -g mocha`

### Setup and running

Run the following in the project directory:

1. `npm install`
2. `bundle install`
3. `node ./node_modules/gulp/bin/gulp.js`

This project requires gulp 4.0, which is installed under node_modules. To be able to use the plain `gulp` command, make sure you have gulp-cli version 0.4 installed:
```
npm install gulpjs/gulp-cli#4.0 -g
```

### Tests

Unit tests are started with:

`mocha`


## Data sources

1. [UNHCR monthly asylum applications](http://popstats.unhcr.org/en/asylum_seekers_monthly)

	To update to the latest data, open the UNHCR asylum applications data portal, select the options below and click on Export / Current View / CSV:

		- Years: 2012, 2013, 2014, 2015
		- Months: All months
		- Country of asylum: All countries
		- Origin: All countries
		- Data item to display: Country of asylum, origin, year

	Save the resulting file as `data/unhcr_popstats_export_asylum_seekers_monthly.csv`, remove the first four (header) rows and run `gulp prepare-data` to generate the required JSON file for the visualization.

	Once you have new data, you can change the time period during which the visualization runs by updating the values in `src/js/model/refugee-constants.js`. Note that changing these values has not been extensively tested, and might result in glitches.

2. [Persons of Concern around Syria](http://data.unhcr.org/syrianrefugees/regional.php)


## Authors

Have feedback? Contact us!

- [Juho Ojala](https://twitter.com/ojalajuho)
- [Ville Saarinen](https://twitter.com/vsaarinen)


## License

???


