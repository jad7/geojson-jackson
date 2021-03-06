GeoJson POJOs for Jackson
=========================

A small package of all GeoJson POJOs (Plain Old Java Objects) for serializing and 
deserializing of objects via JSON Jackson Parser.

Usage
-----

If you know what kind of object you expect from a GeoJson file you can directly read it like this:


```java
FeatureCollection featureCollection = 
	new ObjectMapper().readValue(inputStream, FeatureCollection.class);
```

If you what to read any GeoJson file read the value as GeoJsonObject and then test for the contents via instanceOf:

```java
GeoJsonObject object = new ObjectMapper().readValue(inputStream, GeoJsonObject.class);
if (object instanceOf Polygon) {
	...
} else if (object instanceOf Feature) {
	...
}
```

and so on.

Writing Json is even easier. You just have to create the GeoJson objects and pass them to the Jackson ObjectMapper.

```java
FeatureCollection featureCollection = new FeatureCollection();
featureCollection.add(new Feature());

String json= new ObjectMapper().writeValueAsString(featureCollection);
```

Maven Central
-------------

You can find the library in the Maven Central Repository.

```xml
<dependency>
 <groupId>de.grundid.opendatalab</groupId>
 <artifactId>geojson-jackson</artifactId>
 <version>1.1</version>
</dependency>
```
		
