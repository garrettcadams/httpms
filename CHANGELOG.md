# Change Log

## v1.2.2 - 2018-07-31

Two small bug fixes:

* A regression in config parsing where duration values (such as "20ms") could not be parsed.

* Fix a bug where the address scheme in generated QR barcode is always http.

## v1.2.1 - 2018-07-31

Added a page for generating token in a QR barcode suitable for scaning in the HTTPMS mobile app.

## v1.2.0 - 2018-07-29

Album artwork support is added into the server. Now artwork will be searched on disk or if configured - using the [Cover Art Archive](https://musicbrainz.org/doc/Cover_Art_Archive/). For this new API endpoints are created for working with the artwork.

All static files are bundled into the binary. This makes installation and uninstallation easier. On top of that because we now use `upx` the binary is much smaller than before. Apparently "more is less" contrary to what commander Pike says.

When configured with authentication HTTPMs will now have 3 new options for authentication with JWT tokens: HTTP cookie, `Authorization: Bearer` and via query parameter `token`. At the moment there is no public API for generating tokens but the interactive web login.

On the development front - dependencies are now vendored using `dep` instead of `govendor`. Also, from this version forward releases will be made from the `master` branch instead of `release/X` branches. The latter will be abandoned.

## v1.1.0 - 2017-09-01

A new API endpoint is included: `/browse/`. Using it one can browse through all artists or albums in paginated manner. See [here](README.md#browse) for its full documentation.

## v1.0.4 - 2017-03-08

### Changes

* Changed the library for scanning mp3 files meta information. This would hopefully improve the accuracy.

* The web UI now supports multiple albums with the same name. They would be individually listed in the album filter.

### New Stuff

* Now one can share search, artist and album selections, along with the currently playing track by just copying the URL.

* The UI is greatly improved on devices with small screens. This comes on the cost of exclusion of some features. On such devices one wouldn't be able to use suffle and repeat. Also, no direct download of albums or tracks. The main reason for these ommisions is that the original jPlayer theme was completely unaware of small devices. Future patches may bring the features back.

## v1.0.3 - 2017-02-11

### Bug fixes

Fixed a bug where an album by multiple artists would not be downloadable in bulk. This was because all albums were assumed to by one artist only. This means that there were actually a different album (with the same name) for every atist. Which in turn means that by downloading such an album, you would get only the songs for the particular artist.

## v1.0.2 - 2016-10-12

### Bug fixes

* Fixed a bug where track attributes were jumbled while scanning a library. The effect of this bug were tracks with wrong data for album, track number, title or artist.

## v1.0.1 - 2015-12-05

### What's new?

* This version have its dependencies vendored. All the code required for building it can be found in the release.

## v1.0.0 - 2014-10-19

The first tagged version.
