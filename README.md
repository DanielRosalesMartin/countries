# World countries in JSON, CSV, XML and YAML.
#hola que hace
[![Latest Stable Version](https://img.shields.io/npm/v/world-countries.svg?style=flat)](https://www.npmjs.com/package/world-countries)
[![Latest Stable Version](https://img.shields.io/packagist/v/mledoze/countries.svg?style=flat)](https://packagist.org/packages/mledoze/countries)
[![License](https://img.shields.io/packagist/l/mledoze/countries.svg?style=flat)](https://opendatacommons.org/licenses/odbl/1.0/)
[![PHP from Packagist](https://img.shields.io/packagist/php-v/mledoze/countries.svg)](https://packagist.org/packages/mledoze/countries)

[![Build Status](https://github.com/mledoze/countries/workflows/CI/badge.svg)](https://github.com/mledoze/countries/actions)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/mledoze/countries/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/mledoze/countries/?branch=master)
[![Downloads](https://img.shields.io/npm/dm/world-countries.svg?style=flat)](https://www.npmjs.com/package/world-countries)

## Countries data
This repository contains a list of world countries, as defined by [ISO Standard 3166-1](https://en.wikipedia.org/wiki/ISO_3166-1),
in JSON, CSV, XML and YAML. **Warning:** not all entities in this project are independent countries; refer to the `independent` property to know if the country is considered a sovereign state.

Each line contains the country:

 - `name`
 	 - `common` - common name in english
 	 - `official` - official name in english
 	 - `native` - list of all native names
 	 	- key: three-letter ISO 639-3 language code
	 	- value: name object
	 		- key: official - official name translation
	 		- key: common - common name translation
 - country code top-level domain (`tld`)
 - code ISO 3166-1 alpha-2 (`cca2`)
 - code ISO 3166-1 numeric (`ccn3`)
 - code ISO 3166-1 alpha-3 (`cca3`)
 - code International Olympic Committee (`cioc`)
 - ISO 3166-1 independence status (`independent`) (denotes the country is considered a sovereign state)
 - ISO 3166-1 assignment status (`status`)
 - UN Member status (`unMember`)
 - `currencies` - list of all currencies
 	- key: ISO 4217 currency code
 	- value: currency object
 		- key: `name` name of the currency
 		- key: `symbol` symbol of the currency
 - International Direct Dialing info (`idd`)
 	- `root` - the root geographical code prefix. e.g. +6 for New Zealand, +4 for UK.
 	- `suffixes` - list of all suffixes assigned to this country. 4 for NZ, 809, 829, and 849 for Dominican Republic.
 - capital city(ies) (`capital`)
 - alternative spellings (`altSpellings`)
 - region
 - subregion
 - list of official languages (`languages`)
 	- key: three-letter ISO 639-3 language code
 	- value: name of the language in english
 - list of name translations (`translations`)
 	- key: three-letter ISO 639-3 language code
 	- value: name object
 		- key: official - official name translation
 		- key: common - common name translation
 - latitude and longitude (`latlng`)
 - `demonyms` - name of residents, translated & genderized
    - key: three-letter ISO 639-3 language code
	- value: genderized demonym object
		- key: `f` (female) or `m` (male)
		- value: genderized demonym translation
 - landlocked status (`landlocked`)
 - land borders (`borders`)
 - land area in km?? (`area`)
 - Emoji flag (`flag`)
 - calling codes (`callingCodes`)

#### Additional data
The [data](https://github.com/mledoze/countries/tree/master/data) folder contains additional data such as the countries
GeoJSON outlines and flags in SVG format.

## Examples
##### JSON
```json
{
	"name": {
		"common": "Austria",
		"official": "Republic of Austria",
		"native": {
			"bar": {
				"official": "Republik ??sterreich",
				"common": "??sterreich"
			}
		}
	},
	"tld": [".at"],
	"cca2": "AT",
	"ccn3": "040",
	"cca3": "AUT",
	"cioc": "AUT",
	"independent": true,
	"status": "officially-assigned",
	"unMember": true,
	"currencies": {"EUR": {"name": "Euro", "symbol": "\u20ac"}},
	"idd": {
		"root": "+4",
		"suffixes": ["3"]
	},
	"capital": ["Vienna"],
	"altSpellings": ["AT", "Osterreich", "Oesterreich"],
	"region": "Europe",
	"subregion": "Western Europe",
	"languages": {
		"bar": "Austro-Bavarian German"
	},
	"translations": {
		"cym": {"official": "Republic of Austria", "common": "Awstria"},
		"deu": {"official": "Republik ??sterreich", "common": "??sterreich"},
		"fra": {"official": "R??publique d'Autriche", "common": "Autriche"},
		"hrv": {"official": "Republika Austrija", "common": "Austrija"},
		"ita": {"official": "Repubblica d'Austria", "common": "Austria"},
		"jpn": {"official": "???????????????????????????", "common": "??????????????????"},
		"nld": {"official": "Republiek Oostenrijk", "common": "Oostenrijk"},
		"por": {"official": "Rep??blica da ??ustria", "common": "??ustria"},
		"rus": {"official": "?????????????????????? ????????????????????", "common": "??????????????"},
		"spa": {"official": "Rep??blica de Austria", "common": "Austria"}
	},
	"latlng": [47.33333333, 13.33333333],
	"demonyms": {
		"fra": {
			"f": "Autrichienne",
			"m": "Autrichien"
		},
		"spa": {
			"f": "Austriaco",
			"m": "Austriaca"
		}
	},
	"landlocked": true,
	"borders": ["CZE", "DEU", "HUN", "ITA", "LIE", "SVK", "SVN", "CHE"],
	"area": 83871,
	"callingCodes": ["+43"]
	"flag": "\ud83c\udde6\ud83c\uddf9"
}
```

##### GeoJSON and TopoJSON outlines
See an example for Germany: [GeoJSON](https://github.com/mledoze/countries/blob/bb61a1cddfefd09ad5c92ad0a1effbfceba39930/data/deu.geo.json) or [TopoJSON](https://github.com/mledoze/countries/blob/442472de98e80f4a44f1028960dbb0dfb1d942fe/data/deu.topo.json).

##### CSV
```csv
"name";"tld";"cca2";"ccn3";"cca3";"cioc";"currency";"idd";"capital";"altSpellings";"region";"subregion";"languages";"translations";"latlng";"demonym";"landlocked";"borders";"area"
???
"Aruba,Aruba,Aruba,Aruba,Aruba,Aruba";".aw";"AW";"533";"ABW";"ARU";"AWG";"+2,97";"Oranjestad";"AW";"Americas";"Caribbean";"Dutch,Papiamento";"Aruba,Aruba,Aruba,Aruba,Aruba,Aruba,Aruba,Aruba,Aruba,Aruba,?????????,?????????,Aruba,Aruba,Aruba,Aruba,??????????,??????????,Aruba,Aruba";"12.5,-69.96666666";"Aruban";"";"";"180"
"Afghanistan,Islamic Republic of Afghanistan,???????????? ???????????? ??????????????????,??????????????????,?? ?????????????????? ???????????? ??????????????,??????????????????,Owganystan Yslam Respublikasy,Owganystan";".af";"AF";"004";"AFG";"AFG";"AFN";"+9,3";"Kabul";"AF,Af????nist??n";"Asia";"Southern Asia";"Dari,Pashto,Turkmen";"Islamic Republic of Afghanistan,Affganistan,Islamischen Republik Afghanistan,Afghanistan,Afganistanin islamilainen tasavalta,Afganistan,R??publique islamique d'Afghanistan,Afghanistan,Islamska Republika Afganistan,Afganistan,Repubblica islamica dell'Afghanistan,Afghanistan,????????????????????????????????????????????,?????????????????????,Islamitische Republiek Afghanistan,Afghanistan,Rep??blica Isl??mica do Afeganist??o,Afeganist??o,?????????????????? ???????????????????? ????????????????????,????????????????????,Rep??blica Isl??mica de Afganist??n,Afganist??n";"33,65";"Afghan";"1";"IRN,PAK,TKM,UZB,TJK,CHN";"652230"
"Angola,Republic of Angola,Rep??blica de Angola,Angola";".ao";"AO";"024";"AGO";"ANG";"AOA";"+2,44";"Luanda";"AO,Rep??blica de Angola,????publika de an'????la";"Africa";"Middle Africa";"Portuguese";"Republic of Angola,Angola,Republik Angola,Angola,Angolan tasavalta,Angola,R??publique d'Angola,Angola,Republika Angola,Angola,Repubblica dell'Angola,Angola,?????????????????????,????????????,Republiek Angola,Angola,Rep??blica de Angola,Angola,???????????????????? ????????????,????????????,Rep??blica de Angola,Angola";"-12.5,18.5";"Angolan";"";"COG,COD,ZMB,NAM";"1246700"
???
```

##### XML
```xml
<?xml version="1.0" encoding="UTF-8"?>
<countries>
  <country name="Aruba,Aruba,Aruba,Aruba,Aruba,Aruba" tld=".aw" cca2="AW" ccn3="533" cca3="ABW" cioc="ARU" currency="AWG" idd="+2,97" capital="Oranjestad" altSpellings="AW" region="Americas" subregion="Caribbean" languages="Dutch,Papiamento" translations="Aruba,Aruba,Aruba,Aruba,Aruba,Aruba,Aruba,Aruba,Aruba,Aruba,?????????,?????????,Aruba,Aruba,Aruba,Aruba,??????????,??????????,Aruba,Aruba" latlng="12.5,-69.96666666" demonym="Aruban" landlocked="" borders="" area="180"/>
  <country name="Afghanistan,Islamic Republic of Afghanistan,???????????? ???????????? ??????????????????,??????????????????,?? ?????????????????? ???????????? ??????????????,??????????????????,Owganystan Yslam Respublikasy,Owganystan" tld=".af" cca2="AF" ccn3="004" cca3="AFG" cioc="AFG" currency="AFN" idd="+9,3" capital="Kabul" altSpellings="AF,Af????nist??n" region="Asia" subregion="Southern Asia" languages="Dari,Pashto,Turkmen" translations="Islamic Republic of Afghanistan,Affganistan,Islamischen Republik Afghanistan,Afghanistan,Afganistanin islamilainen tasavalta,Afganistan,R??publique islamique d'Afghanistan,Afghanistan,Islamska Republika Afganistan,Afganistan,Repubblica islamica dell'Afghanistan,Afghanistan,????????????????????????????????????????????,?????????????????????,Islamitische Republiek Afghanistan,Afghanistan,Rep??blica Isl??mica do Afeganist??o,Afeganist??o,?????????????????? ???????????????????? ????????????????????,????????????????????,Rep??blica Isl??mica de Afganist??n,Afganist??n" latlng="33,65" demonym="Afghan" landlocked="1" borders="IRN,PAK,TKM,UZB,TJK,CHN" area="652230"/>
  <country name="Angola,Republic of Angola,Rep??blica de Angola,Angola" tld=".ao" cca2="AO" ccn3="024" cca3="AGO" cioc="ANG" currency="AOA" idd="+2,44" capital="Luanda" altSpellings="AO,Rep??blica de Angola,????publika de an'????la" region="Africa" subregion="Middle Africa" languages="Portuguese" translations="Republic of Angola,Angola,Republik Angola,Angola,Angolan tasavalta,Angola,R??publique d'Angola,Angola,Republika Angola,Angola,Repubblica dell'Angola,Angola,?????????????????????,????????????,Republiek Angola,Angola,Rep??blica de Angola,Angola,???????????????????? ????????????,????????????,Rep??blica de Angola,Angola" latlng="-12.5,18.5" demonym="Angolan" landlocked="" borders="COG,COD,ZMB,NAM" area="1246700"/>
???
<countries>
```

##### YAML
```yaml
- { name: { common: Aruba, official: Aruba, native: { nld: { official: Aruba, common: Aruba }, pap: { official: Aruba, common: Aruba } } }, tld: [.aw], cca2: AW, ccn3: '533', cca3: ABW, cioc: ARU, currency: [AWG], idd: { root: '+2', suffixes: ['97'] }, capital: Oranjestad, altSpellings: [AW], region: Americas, subregion: Caribbean, languages: { nld: Dutch, pap: Papiamento }, translations: { deu: { official: Aruba, common: Aruba }, fin: { official: Aruba, common: Aruba }, fra: { official: Aruba, common: Aruba }, hrv: { official: Aruba, common: Aruba }, ita: { official: Aruba, common: Aruba }, jpn: { official: ?????????, common: ????????? }, nld: { official: Aruba, common: Aruba }, por: { official: Aruba, common: Aruba }, rus: { official: ??????????, common: ?????????? }, spa: { official: Aruba, common: Aruba } }, latlng: [12.5, -69.96666666], demonym: Aruban, landlocked: false, borders: {  }, area: 180 }
- { name: { common: Afghanistan, official: 'Islamic Republic of Afghanistan', native: { prs: { official: '???????????? ???????????? ??????????????????', common: ?????????????????? }, pus: { official: '?? ?????????????????? ???????????? ??????????????', common: ?????????????????? }, tuk: { official: 'Owganystan Yslam Respublikasy', common: Owganystan } } }, tld: [.af], cca2: AF, ccn3: '004', cca3: AFG, cioc: AFG, currency: [AFN], idd: { root: '+9', suffixes: ['3'] }, capital: Kabul, altSpellings: [AF, Af????nist??n], region: Asia, subregion: 'Southern Asia', languages: { prs: Dari, pus: Pashto, tuk: Turkmen }, translations: { cym: { official: 'Islamic Republic of Afghanistan', common: Affganistan }, deu: { official: 'Islamischen Republik Afghanistan', common: Afghanistan }, fin: { official: 'Afganistanin islamilainen tasavalta', common: Afganistan }, fra: { official: 'R??publique islamique d''Afghanistan', common: Afghanistan }, hrv: { official: 'Islamska Republika Afganistan', common: Afganistan }, ita: { official: 'Repubblica islamica dell''Afghanistan', common: Afghanistan }, jpn: { official: ????????????????????????????????????????????, common: ????????????????????? }, nld: { official: 'Islamitische Republiek Afghanistan', common: Afghanistan }, por: { official: 'Rep??blica Isl??mica do Afeganist??o', common: Afeganist??o }, rus: { official: '?????????????????? ???????????????????? ????????????????????', common: ???????????????????? }, spa: { official: 'Rep??blica Isl??mica de Afganist??n', common: Afganist??n } }, latlng: [33, 65], demonym: Afghan, landlocked: true, borders: [IRN, PAK, TKM, UZB, TJK, CHN], area: 652230 }
- { name: { common: Angola, official: 'Republic of Angola', native: { por: { official: 'Rep??blica de Angola', common: Angola } } }, tld: [.ao], cca2: AO, ccn3: '024', cca3: AGO, cioc: ANG, currency: [AOA], idd: { root: '+2', suffixes: ['44'] }, capital: Luanda, altSpellings: [AO, 'Rep??blica de Angola', '????publika de an''????la'], region: Africa, subregion: 'Middle Africa', languages: { por: Portuguese }, translations: { cym: { official: 'Republic of Angola', common: Angola }, deu: { official: 'Republik Angola', common: Angola }, fin: { official: 'Angolan tasavalta', common: Angola }, fra: { official: 'R??publique d''Angola', common: Angola }, hrv: { official: 'Republika Angola', common: Angola }, ita: { official: 'Repubblica dell''Angola', common: Angola }, jpn: { official: ?????????????????????, common: ???????????? }, nld: { official: 'Republiek Angola', common: Angola }, por: { official: 'Rep??blica de Angola', common: Angola }, rus: { official: '???????????????????? ????????????', common: ???????????? }, spa: { official: 'Rep??blica de Angola', common: Angola } }, latlng: [-12.5, 18.5], demonym: Angolan, landlocked: false, borders: [COG, COD, ZMB, NAM], area: 1246700 }
```

## Customising the output
The data files provided in the `dist` directory include all available fields, but is also possible to build a custom version of the data with certain fields excluded.

To do this, you will first need a working PHP installation, [composer](https://getcomposer.org) and a local copy of this repository. Once you have these, open a terminal in your local version of this project's root directory and run this command to install the necessary dependencies:

```sh
composer install
```

After this finishes, run the following command (here we will exclude the `tld` field from the output, but you can exclude any field you want):

```sh
php countries.php convert --exclude-field=tld
```

You can also exclude multiple fields:

```sh
php countries.php convert --exclude-field=tld --exclude-field=cca2

# Or using the shorter `-x` syntax:
php countries.php convert -x tld -x cca2
```

If you prefer to include only some fields (this can not be combined with `--exclude-field`):

```sh
php countries.php convert --include-field=name --include-field=area

# or using the shorter `-i` syntax:
php countries.php convert -i=name -i=area
```

The generated files are put into the `dist` directory, but you can change this to another existing directory:

```sh
mkdir foobar
php countries.php convert --output-dir=foobar
```

You can also choose to only generate some of the output formats:

```sh
mkdir foobar
php countries.php convert --format=json_unescaped --format=csv

# or using the shorter `-f` syntax:
php countries.php convert -f json_unescaped -f csv
```


## Showcase
Projects using this dataset:

- [REST Countries](https://restcountries.eu/)
- [International Telephone Input](https://intl-tel-input.com/)
- [Telephone JS](https://github.com/lukaswhite/telephones-js)
- [Countries of the World](http://countries.petethompson.net/)
- [Country Prefix Codes For Go](https://github.com/relops/prefixes)
- [Country Info Mapper in Go](https://github.com/pirsquare/country-mapper)
- [Visa requirements in JSON](https://github.com/StrudelInc/visas2)
- [Country picker modal for React Native](https://github.com/xcarpentier/react-native-country-picker-modal)
- [Agnostic Virtual Assistant](https://github.com/ava-ia/core)

## How to contribute?
Please refer to [CONTRIBUTING](https://github.com/mledoze/countries/blob/master/CONTRIBUTING.md).

## To do
 - add the type of the country (country, sovereign state, public body, territory, etc.)
 - add missing translations
 - pull in data automatically from CLDR at build time (idea from @Munter, see #108)

## Sources
https://www.currency-iso.org/ for currency codes.

Region and subregion are taken from https://github.com/hexorx/countries.

GeoJSON outlines come from http://thematicmapping.org/downloads/world_borders.php.

The rest comes from Wikipedia.

## Credits
Thanks to:
 - @Glazz for his help with country calling codes
 - @hexorx for his work (https://github.com/hexorx/countries)
 - @frederik-jacques for the capital cities
 - @fayer for the population, geolocation, demonym and area data
 - @ancosen for his help with the borders data
 - @herrjemand for country names and various fixes
 - all the contributors: https://github.com/mledoze/countries/graphs/contributors

## License
See [LICENSE](https://github.com/mledoze/countries/blob/master/LICENSE).
