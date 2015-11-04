This is a sketchy introduction about how ACL works in our project. The infrastructure is based on the idea from Project "ripster' (https://github.com/vslinko/ripster).

# How it works

Basically, this acl is designed to work with graphql, to achieve this purpose, wrapField is applied on every type which we want to control (I will go through all scenarios one by one in details in the following chapter). 

The structure is generally described as follows:

 - index: define specific rules to be applied
 - rules: define the logic of each rule
 - wrapConnectionField: extend wrapField to work with graphql-relay connections
 - wrapField: define the logic how to apply rules

In addition, we take advantages of Project "access-rule" (https://github.com/vslinko/access-rule), in which some basic rules are defined.

# Details

## index

The main purpose of index is to export a function which is returned by either "byType" or "complex" from rules (describe later).

You want to list all the types to be controlled here, all types not listed will be denied by default (unless you change default behaviour to allow)

## rules

### byType

you want to pass in a specific rule list which can contain two kinds of rules: simple and complex. For both of them, you have to pay attention to a few logics: 

 - how to deal with list
 - how to deal with connections
 - how to correspond json object to graphql object
 - default behaviour
 - everyrule logic

### complex

if object is a grphql object:

 - OP_CREATE is the only specific rule to be checked (because for 'rud', a json object is necessary, please fix me if I was wrong)
 - baseRule is then applied
 
if object is a json object:

 - apply specific rule
 
### admin

check roles of the object, <b>should never be used as baseRule</b>

### self

check if object's id is the same as subject's id, <b>always allow if a type is passed in as object</b>

### owner

check if object's user_id is the same as subject's id, <b>always allow if a type is passed in as object</b>

## wrapConnectionField

a connection wrapper

## wrapField

### checkAccess

check acl from index

### assertAccess

throw error if checkAccess fails

### wrappedResolve

 - check OP_READ for every type, which makes sense (if a type cannot be read, there is no point issuing any further queries), this requires that all baseRules should be passed for all types, I personal prefer 'allow'.
 - check OP_READ for every object result

### field(assertAccess)

 - check access for mutations, setup 'assertAccess' rules in each mutation if you want to control it
 
