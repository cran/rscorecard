# rscorecard 0.11.0
- update dictionary for 30 October 2018 release of data

# rscorecard 0.10.0
- update dictionary for 28 September 2018 release of data

# rscorecard 0.9.0

## Potentially breaking changes
- default value for `sc_year()` is now `'latest'` rather
  than 2013. With continued data updates, this makes more sense than
  keeping an old year. Existing scripts that relied on the default for
  data from 2013 will need to be updated.  
- also note that the `year` column will be a character column with
  `latest` as the value when the most recent data are choosen. The
  College Scorecard doesn't clearly note which data are the latest, so
  I have left the string. When building a panel dataset across
  multiple years, it will be best to use numeric year values for all
  years so that the resulting tibbles can be bound together cleanly.

## Other changes
- add support for using some tidyselect helper functions when
  selecting variables with `sc_select()`: `starts_with()`,
  `ends_with()`, `contains()`, and `matches()` should now be
  available.
- update dictionary for 6 September 2018 release of data

# rscorecard 0.8.0

## Changes
- improved error handling when submitting bad request 
- added `sc_select_()` and `sc_filter_()`, which allow users to select
  and filter variables using strings stored in environment variable

# rscorecard 0.7.1

## Changes
- update dictionary for March 2018 release of scorecard data

# rscorecard 0.7.0

## Changes
- update dictionary for 19 December 2017 release of scorecard data

# rscorecard 0.6.0

## Changes
- allow `sc_zip()` to take zip codes that start with zero (h/t
  @nateaff), either with string value or by returning leading zeros to
  numeric values that R drops

# rscorecard 0.5.0

## Changes
- changed way API call is made (now using [`httr`](https://CRAN.R-project.org/package=httr) to make call rather than `jsonlite` directly) in order to improve parsing on bad lines
- added `debug` option to `sc_get()` so that the API URL string could be returned when debugging call
- removed old namespace import/exports no longer being used

# rscorecard 0.4.0

- update dictionary for 28 September 2017 release of scorecard data
- update link in introduction vignette
- change contact information
- read data dictionary sheet by name instead of sheet number when
  making `sysdata.rda` in `./data-raw/make_dict_hash.R`
- correct `sc_get()` to use `floor()` instead of `ceiling()` so that
  it doesn't make unnecessary API request/pull (h/t @jjchern)

# rscorecard 0.3.3

## Bug fix
- allow `sc_filter()` to use subset object vectors

# rscorecard 0.3.2

- allow `sc_filter()` to use vectors stored in objects
- allow `sc_filter()` to use `%in%` operator

# rscorecard 0.3.1

- update dictionary for 13 January 2017 release of scorecard data
- update `sc_dict()` to search all columns by default
- update internal hash lookup environment to have less generic name

# rscorecard 0.2.5

- fixed `sc_dict()` bug that wouldn't allow for search by developer friendly names

# rscorecard 0.2.4

- initial release
