# Pelias

An open-source Geocoder

## Basic links

[pelias/pelias](https://github.com/pelias/pelias) Github repo: a meta-repo with introductory
developer docs, a summary of the Pelias architecture, and links to other components

[Official docs](https://mapzen.com/documentation/search/) Full documentation for using the Pelias
API. These docs originate on Github [here](https://github.com/pelias/pelias-doc) and are a great
place to start contributing.

[Pelias Waffle.io board](https://waffle.io/pelias/pelias) A Github issue based kanban board that
tracks the progress of all tickets and issues for the Pelias project. Note the [help
wanted](https://waffle.io/pelias/pelias?label=help%20wanted) and [low hanging
fruit](https://waffle.io/pelias/pelias?label=low-hanging%20fruit) labels which are a great place to
look for tasks to take on.

## Notable sub-projects

[pelias/api](https://github.com/pelias/api): Our Express based API framework. Backend people go here
:)

[pelias/leaflet-geocoder](https://github.com/pelias/leaflet-geocoder) A plugin to the
[Leaflet](http://leafletjs.com/) Javascript interactive map library. Frontend people go here :)

[pelias/vagrant](https://github.com/pelias/vagrant) A Vagrant image that spins up an entire Pelias
instance in 20-30 minutes. A great way to initially familiarize yourself with the Pelias
architecture.

## Selected tasks that might be fun to work on

### Beginner

[Move execution out of index.js](https://github.com/pelias/openstreetmap/issues/37) A (hopefully)
simple refactoring of one of our importer modules.

[deal with errors better in the leaflet plugin](https://github.com/pelias/leaflet-geocoder/issues/38) Error handling is always good.

### Intermediate

[document how to set up a full development environment](https://github.com/pelias/pelias-doc/issues/55)
We have various bits of documentation for setting up a dev instance, but it's very scattered.

[fix issue with filenames in openaddresses importer](https://github.com/pelias/openaddresses/issues/23) A user recently reported having trouble
importing data via our openaddresses importer. This code is in need of a refactoring anyway, so some
cleanup here would be greatly appreciated.

(RUBY) Add pelias support to the [Ruby geocoder gem](https://github.com/alexreisner/geocoder)

[warn when unexpected parameters are found in query](https://github.com/pelias/api/issues/279) We
want to warn users when they have specified API parameters that don't exist. We already have an
infrastructure for sending warnings in our responses, the biggest challenge here will be determining
which parameters are valid and which are not, since there isn't currently a list in our codebase
(there IS one in a Google Doc that I can send you).

### Advanced

[Import multiple pbf files](https://github.com/pelias/openstreetmap/issues/55): update our Node
streams based OpenStreetMap importer to accept multiple files as input (currently it has to be run
multiple times to handle several files). The [openaddresses importer](https://github.com/pelias/openaddresses/)
already supports multiple files, so perhaps the same technique can be used.
