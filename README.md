# BF4-API-Documentation
Documentation of the BF4 Battlelog JSON API

I assume if you're looking at this it's because you went through my profile and not because you actually wanted to use any of it. If that isn't the case, rethink your life choices.

### Disclaimers
This is a side project as I mess with the API. It is not guaranteed to be useful, up to date, or right. There are a lot of keys that I have no reasonable idea what they do. If I make a guess it will be marked.

### Eventual goal
Have all of the JSON endpoints sorted, the keys explained, I'd like to have it so that you can search a term and reasonably be told the various endpoints to retrieve it. The headers required for an endpoint should also be somewhere about.

### Not Happening:

I will not be putting in the effort to track every internal code and codename to an object. Some of them are incredbly odd

Actually giving myself a schedule: The endpoints are ridiculous and there is only so much looking at the same information repeated 12 times that I can deal with.

# Idiotic Design Choices

#### Capitalization
Some titles are camelCase, some are lowercase, some are PascalCase, and some they forgot about the capitalization in general. This idiosyncrasy is even present in the endpoints with identical naming formats where only one word is different. e.g. warsawWeaponsPopulate warsawvehiclesPopulate.
#### Repetition and Irrelevant Information
The same information is given multiple times in a return, with no changes in format or what it references. Some endpoints return information never even used by the webpage where they are called.
#### Blank Values
Endpoints return data with half of the keys having None or 0 in the values, even requesting on the authorized user and with information that should be present.
#### Servers Platform Path Value
The servers path is `/servers/show/[platform]/[guid]` but the platform doesn't actually affect the page you receive if you put in a valid platform. `XBOXONE` can be used to find a pc server and vice versa. This might imply that the path is not used at all but putting in an invalid platform returns `internal server error`. Except for when it doesn't, in the case of `ps2`, you get a 404 page instead.
