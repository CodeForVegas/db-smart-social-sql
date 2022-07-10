# Smart Social Backend Database Project

The goal of the Smart Social Project is to enable a Smart City to communicate with itself.

The Backend Database will hold organizer, event calender, event entry, venue/location, and other data in a relational database initially, intended to make maximal use of various views, geolocation data, and other means to provide data in maximally useful ways.

This will enable supporting a Smart Calendar, Smart Contacts, Smart News, etc etc etc.

This repository was formerly named db-smart-calendar-sql but will now contain schema for all Smart Social project data.

## Project Policies

Unless otherwise and specifically indicated with replacement files in this repository, this project will adhere to the default Code for Vegas Foundation policies for Code of Conduct and Contributing, found at

* [Code of Conduct - Code for Vegas Foundation](https://github.com/CodeForVegas/.github/blob/main/CODE_OF_CONDUCT.md)
* [Contributing to this Project - Code for Vegas Foundation](https://github.com/CodeForVegas/.github/blob/main/CONTRIBUTING.md)

## Tools Selection

Schema have been borrowed from a mobile vendor event platform in development by @DanHugoDanHugo (Dan Hugo) and adapted to use for a generalized calendar/event scheme. Permission has been granted to take the snapshot and adapt as needed for the project here by Dan Hugo.

### Database Selection

Thanks to a variety of useful features, PostgreSQL is a useful store across the Smart Social platform. Database schema is defined in sql rather than via an ORM, and migration can be accomplished in a client-language agnostic fashion using tools such as [tusker](https://github.com/bikeshedder/tusker)

A cache layer, implemented using Redis for example, might be useful under load, this is TBD.

### Caching and Alternates

It is possible that a particular Smart Social deployment may include only parts of the overall Smart Social platform, or it may be deployed on a central host and deployed as a cloud service, in which case these alternate schemes may only require a caching store. This is TBD but could be managed with a pubsub scheme, or demand pull expiry info, or other. The main store here would be a source of truth for such updates (ie a local cache or downstream should behave as any peer and forward updates in a timely fashion).

### Event Streams

An event steam mechanism (something as heavy as Kavka or as light as a very basic LISTEN/NOTIFY scheme) may be useful to synchronize services around the database. This may be a part of the database, or a part of the design of the database services around the database.
## References

[PostgreSQL Home](https://www.postgresql.org/)

[tusker](https://github.com/bikeshedder/tusker)
