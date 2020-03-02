# sfomuseum-data-flight-2020-03

Flight data for arrivals and departures at SFO (March, 2020)

## Important

This is highly experiental work right now. If you are planning to try using it, for anything at all, understand that everything is in flux and subject to change and may still break along the way.

## Background

Details to follow but for background we recommend reading these blog posts:

* [Who's On First at SFO Museum](https://millsfield.sfomuseum.org/blog/2018/08/28/whosonfirst/) (August 2018)
* [SFO Museum, Who's On First and Airports](https://millsfield.sfomuseum.org/blog/2018/10/30/airports/) (October 2018)
* [Capturing flight data at SFO and SFO Museum](https://millsfield.sfomuseum.org/blog/2019/01/18/flights/) (January 2019)
* [Harvey Milk Plane Has a Permalink – Updated flight data at SFO Museum](https://millsfield.sfomuseum.org/blog/2019/05/17/flights/) (May 2019)

## Notes

Some (but still not all) flights have "alternate" geometries representing the planned route for the flight as well as the actual flight path in and out of SFO. Respectively they identified using the following naming convention:

* `{WHOSONFIRST_ID}-alt-swim-route.geojson`
* `{WHOSONFIRST_ID}-alt-swim-path.geojson`

There are a few things to keep in mind when using this data:

* These alternate geometries are currently not availble for "code share" flights.
* Routes and paths are clipped at the exterior boundaries of airports as well as the United States. We hope to have more detailed data soon, but today this is what we have to work with.
* Elevation, speeds and point-in-time data for flight paths (not routes) are stored in the `swim:altitudes` and `swim:speeds` and `swim:timestamps` properties respectively. Each is an array and each index maps to a corresponding entry in the feature's `coordinates` array.
* Elevation data are currently encoded as raw [SWIM](https://www.faa.gov/air_traffic/technology/swim/products/) `simpleAltitude Type` values. The documentation describes these values as:

> "Simple type used to place constraints on a flight's altitude. The altitude can represent a number of values as reported by NAS. Please refer to NAS MD-314 section 3.1 for details. The message from HADDS to TFMS is constrained to include an assigned altitude, nnn, or a beacon reported altitude, nnn + 'C', or an interim altitude, nnn + 'T'. Allowed format: [0-9]{0,3}[C,T]{0,1}. Where C = Beacon reported altitude is within Altitude Conformance Limits (ALCT) feet and T = Interim altitude is currently being displayed in the assigned altitude field."

## License

This data is published under the [Community Data License Agreement – Permissive – Version 1.0](LICENSE) license, but we'd love a [shout-out](https://twitter.com/flysfo) and generally to hear what you're doing if you use the data.

## See also

* https://millsfield.sfomuseum.org/flights/
