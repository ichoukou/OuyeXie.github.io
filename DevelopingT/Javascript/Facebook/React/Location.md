# Introduction

Location

type Location = {
  pathname: Pathname;
  search: QueryString;
  query: Query;
  state: LocationState;
  action: Action;
  key: LocationKey;
};
A location answers two important (philosophical) questions:

Where am I?
How did I get here?
New locations are typically created each time the URL changes. You can read more about locations in the history docs.

LocationDescriptor

type LocationDescriptorObject = {
  pathname: Pathname;
  search: Search;
  query: Query;
  state: LocationState;
};

type LocationDescriptor = LocationDescriptorObject | Path;
A location descriptor is the pushable analogue of a location. Locations tell you where you are; you create location descriptors to say where to go.

You can read more about location descriptors in the history docs.

LocationKey

type LocationKey = string;
A location key is a string that is unique to a particular location. It is the one piece of data that most accurately answers the question "Where am I?".

LocationState

type LocationState = ?Object;
A location state is an arbitrary object of data associated with a particular location. This is basically a way to tie extra state to a location that is not contained in the URL.

This type gets its name from the first argument to HTML5's pushState and replaceState methods.

Path

type Path = Pathname + QueryString + Hash;
A path represents a URL path.

Pathname

type Pathname = string;
A pathname is the portion of a URL that describes a hierarchical path, including the preceding /. For example, in http://example.com/the/path?the=query, /the/path is the pathname. It is synonymous with window.location.pathname in web browsers.

QueryString

type QueryString = string;
A query string is the portion of the URL that follows the pathname, including any preceding ?. For example, in http://example.com/the/path?the=query, ?the=query is the query string. It is synonymous with window.location.search in web browsers.

Query

type Query = Object;
A query is the parsed version of a query string.

Params

type Params = Object;
The word params refers to an object of key/value pairs that were parsed out of the original URL's pathname. The values of this object are typically strings, unless there is more than one param with the same name in which case the value is an array.



# Reference

 - https://github.com/reactjs/react-router/blob/70c23b4fb9604deebe0d441e1d42379a8b82798f/docs/Glossary.md