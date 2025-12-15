# Liturgical Calendar

This Python module will return the name, season, week number and liturgical
colour for any day in the Gregorian calendar, according to the Anglican
tradition of the Church of England.

This module's algorithm is a direct port to Python of
[`DateTime::Calendar::Liturgical::Christian`](https://github.com/gitpan/DateTime-Calendar-Liturgical-Christian),
which was originally written in Perl and loaded with the calendar of the Episcopal
Church of the USA. It has now been fed with data from the Church of England's
[Calendar of saints](https://en.wikipedia.org/wiki/Calendar_of_saints_(Church_of_England))
and substantially modified to suit the Anglican calendar.

The output of this module is compared against the
[Church of England Lectionary](https://www.chpublishing.co.uk/features/lectionary),
which is taken to be the canonical source.

## Installation

This library is [published on PyPI](https://pypi.org/project/liturgical-calendar/).

```console
pip install liturgical-calendar
```

## Usage, as a command

Once installed, this can be run at the command line. Currently it prints
an object with various attributes. This portion of the module needs
improvement, although it is probably more useful as a library.

Specify the date in YYYY-MM-DD format, or leave blank to return info
for today.

```console
# Get info for today
$ liturgical_calendar
name : 
prec : 1
season : Lent
season_url : https://en.wikipedia.org/wiki/Lent
week : Lent 1
date : 2025-03-13
colour : purple
colourcode : #664fa6
ember : 0

# Get info for an arbitrary date
$ liturgical_calendar 2023-01-25
name : The Conversion of Paul
url : https://en.wikipedia.org/wiki/Conversion_of_Paul
prec : 7
type : Festival
type_url : https://en.wikipedia.org/wiki/Festival_(Church_of_England)
season : Epiphany
season_url : https://en.wikipedia.org/wiki/Epiphany_season
week : Epiphany 3
date : 2023-01-25
colour : white
colourcode : #fffff6
ember : 0
```

## Usage, as a library

```py
# Get info for today
dayinfo = liturgical_calendar()

# Get info for an arbitrary date
# Date can be expressed as a string in YYYY-MM-DD format, a Datetime object, or a Date object
dayinfo = liturgical_calendar('YYYY-MM-DD')

# Access the attributes individually
print(dayinfo['colour'])
```

## Development

This Python project is managed with Poetry. For local testing without installing, run

```console
poetry run liturgical_colour
```

## Issues

If you find bugs (either in the code or in the calendar data), please
[create an issue on GitHub](https://github.com/liturgical-app/liturgical-calendar/issues).

Pull requests are always welcome, either to address bugs or add new features.
