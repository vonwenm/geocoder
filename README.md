Mapquest geocoder and directions for Go (golang)
================================================

## What does it do

* Returns a Longitude and Latitude for a given string query
* Returns an address for a Longitude and Longitude
* Returns directions between two or more points. (JSON or XML)

## API Key
Get a free API Key at [http://mapquestapi.com](http://mapquestapi.com)

## Why MapQuest API?
Google Maps Geocoding API has a limitation that prohibits querying their geocoding API unless you will be displaying the results on a Google Map. Google directions is limited to 2 requests per second.

## Install

* go get "github.com/jasonwinn/geocoder"
* import "github.com/jasonwinn/geocoder"
 

## Examples

### Geocode
```
  query := "Seattle WA"
  lat, lng := geocoder.Geocode(query)
  
  // 47.6064, -122.330803
 
```

### Reverse Geocode
```
  address := geocoder.ReverseGeocode(47.6064, -122.330803)

  address.Street 	        // 542 Marion St   
  address.City 		        // Seattle
  address.State 	        // WA
  address.PostalCode 	    // 98104 
  address.County 	        // King
  address.CountryCode       // US 

```

### Directions
```
  directions := NewDirections("Amsterdam,Netherlands", []string{"Antwerp,Belgium"})
  results, err := directions.Get()
  route := results.Route
  time:= route.Time
  legs:= route.Legs
  distance:= route.Distance
  // or get distance with this shortcut
  distance, err := directions.Distance("k")
```

## Documentation

[https://godoc.org/github.com/jasonwinn/geocoder](https://godoc.org/github.com/jasonwinn/geocoder)

