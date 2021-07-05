# Session Name: LSON-LD 
**Full Form: JavaScript Object Notation for Linked Data**  
**Date: 3th July, 2021**  
----

## Brief About JSON-LD

- JSON-LD is a method of encoding linked data using JSON by meaning itself into the document.
- In JSON_LD, every key in a JSON document had its own unique identity which you could look up (because web!).
- JSON-LD allows data to be serialized in a way that is similar to traditional JSON.
- It is a lightweight and modern standard of Linked Data format through in HTML Document or other section.
- By implementing, we can develop our REST API Services services and non-structural Database like MongoDB & Apache CloudDB.
- JSON-LD follows the [World Wide Web Consortium](https://en.wikipedia.org/wiki/World_Wide_Web_Consortium) rules and regulation that is the organization of main international standards organization for the World Wide Web. Founded in 1994 and currently led by Tim Berners-Lee. 


## There are 4 Fundamentals in JSON-LD:

1. "@context"  
It's also called Document Context that hold whole of JSON information. Process it by algorithm and generate a link.  

2. "@id"  
it is an unique identifier of any value or information.  

3. "@type"  
it defines what kind of value we would given.  
There are mainly 2 kind of 'type' in JSON-LD  
    - Object Type (person, place, event, company)
    - Data Type (Integer, Float, Date-Time, Temperature)

4. "key": "value"  
Describes our data.

## Example: 

```
{
  "@context": {
    "@vocab": "http://schema.org/",
    "first_name": "givenName",
    "last_name": "familyName",
    "alias": "alternateName",
    "email": "email"
  },
  "first_name": "Benjamin",
  "last_name": "Young",
  "alias": "BigBlueHat",
  "email": "byoung@bigbluehat.com"
}
```
- **"@context"** object, that maps with our variables to JSON-LD 'keywords' for terms of customization. 
- **"@vocab"** maps The key/value pairs directly to meaningful URLs at [Schema.org](Schema.org). For reason, every key have an identity & a unique definition.

```
{
  "@context": "http://schema.org/",
  "givenName": "Benjamin",
  "familyName": "Young",
  "alternateName": "BigBlueHat",
  "email": "byoung@bigbluehat.com"
}
```
- JSON-LD with **No Customization** 


## There are 2 Algorithm in JSON-LD

- Expansion
- Compaction

### Expansion

- It takes **"@context"** URL and gives us JSON-LD code.
```
[
  {
    "http://schema.org/alternateName": [
      {
        "@value": "BigBlueHat"
      }
    ]
  }
]
```
**Output:**  
```
{
  "@context": "http://schema.org/",
  "alternateName": "BigBlueHat"
}
```


### Compaction
- It takes JSON_LD code and provides us context URL
```
{
    "@context": "http://schema.org/",
    "alternateName": "BigBlueHat"
}
```

**Output:**  
```
[
  {
    "http://schema.org/alternateName": [
      {
        "@value": "BigBlueHat"
      }
    ]
  }
]
```

## Expression Examples: 

**Integer Expression**  
```
{
    "@context": "URL",
    "MarkSheet": {
      "@id": "unique URL",
      "@type": "xsd:int"
    }
}
```

**Float Expression**  
```
{
    "@context": "URL",
    "Cgpa": {
      "@id": "unique URL",
      "@type": "xsd:float"
    }
}
```

**Date Expression**  
```
{
    "@context": "URL",
    "birthday": {
        "@type": "xsd:dateTime",
        "@value": "1st July, 2002"
    }
}
```

**Language Expression**  
```
{
    "@context": "URL",
    "name": {
        "@language": "JP",
        "@value": "Sheizei"
    }
} 
```

### About More Information, Visit [cloudbees.com](https://www.cloudbees.com/blog/json-ld-building-meaningful-data-apis), [Official JSON-LD Page](https://json-ld.org/)