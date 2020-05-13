# dystonse - _DYnamic STochastic ONline SEarch in public transport networks_
<p align="center">
  <img src="https://github.com/lenaschimmel/dystonse/blob/master/header_white.png?raw=true" alt="Header image with dystonse logo"/>
</p>

We are preparing a routing algorithm for public transit with the following key characterstics (as they are commonly defined in the respective research field):

 * __Dynamic__: the cost function ( = travel time) varies over time, which is the case for scheduled public transit
 * __Stochastic__: the cost function ( = travel time) is not a deterministic prediction of the actual travel time, but a probability distribution
 * __Online__: The algorithm does not return a final output upfront, instead it iterates _en route_, while the user is actually traveling, incorporating updated real time information to yield the best routing that is currently archievable

## Website
**The prototype of the Dystonse website is available at [dystonse.org](https://dystonse.org) - there you can test the algorithm and read about the background of this project.**

## Blog
We just started out development blog at [blog.dystonse.org](https://blog.dystonse.org).

## Development status
This repository does not contain code, but we track our development and share some notes in the [project-status](./project-status) folder.

## Data colletions
We have started to collect real time data. Current colletion status: 

Provider                             | Status
-------------------------------------|----------------------------------------------------------------------
Verkehrsverbund Bremen/Niedersachsen | ![badge](https://healthchecks.io/badge/5441c6f8-5c30-4c41-826d-02327f/s_7xl3wR/record-vbn-realtime.svg)
Verkehrsverbund Rhein-Neckar         | ![badge](https://healthchecks.io/badge/5441c6f8-5c30-4c41-826d-02327f/gKm3Jn9I/record-vrn-realtime.svg)

## Development is happening somewhere else
This repository serves only as a landing page for other repositorys, where the actual development takes place.

 * **[dystonse-gtfs-data](https://github.com/dystonse/dystonse-gtfs-data)** A collection of tools to work with the **gtfs** schedule data and **gtfs-realtime** data that we're collecting from the public transport providers listed above. Used for importing data into a database, and creating statistical analyses. This is where most of our work happens at the moment (May 2020). _(partly working, more features currently being developed)_
 * **[dystonse-docker](https://github.com/dystonse/dystonse-docker)** A docker-compose setup for our whole stack (so far: data collection, automated import into database, config and admin tools for the database), containing the public parts of the config we actually use for our ongoing data collection, and slightly redacted examples of the non-public parts to show how the whole setup would be used by anyone. _(working, currently maintained to fit whenever we make any changes to our deployment)_
 * **[dystonse-website](https://github.com/dystonse/dystonse-website)** The website of Dystonse, which features both a GUI to perform searches and a lot of background information about the project _(working, but currently not maintained while we're working on the backend)_
 * **[dystonse-search-node](https://github.com/dystonse/dystonse-search-node)** The first implementation of the Dystonse search algorithm. It actually works and serves as backend for the _website_. Development will be discontinued in favor of a clean implementation in Rust. _(working)_
 * **[dystonse-search-rust](https://github.com/dystonse/dystonse-search-rust)** This will be the home of the reimplementation  of the Dystonse search algorithm. _(no content yet)_
 * **[dystonse-tools](https://github.com/dystonse/dystonse-tools)** Various tools that are somehow useful for our project, but not the main focus of our development.
   * **[Agencies tool](https://github.com/dystonse/dystonse-tools/tree/master/agencies)** A tool for gathering and organizing information about German transit agencies. _(working)_
   * Some Java-based tools from 2017. Development paused / discontinued.

## News and Contact

You can follow [@dystonse](https://twitter.com/dystonse) on Twitter to stay up to date or get in touch.
