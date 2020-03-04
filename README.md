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

## Development is happening somewhere else
This repository serves only as a landing page for other repositorys, where the actual development will take place.

 * **[dystonse-website](https://github.com/dystonse/dystonse-website)** The website of Dystonse, which features both a GUI to perform searches and a lot of background information about the project _(working)_
 * **[dystonse-search-node](https://github.com/dystonse/dystonse-search-node)** The first implementation of the Dystonse search algorithm. It actually works and serves as backend for the _website_. Development will be discontinued in favor of a clean implementation in (most likely) Rust. _(working)_
 * **[dystonse-search-rust](https://github.com/dystonse/dystonse-search-rust)** This will be the home of the reimplementation  of the Dystonse search algorithm. _(no content yet)_
 * **[dystonse-tools](https://github.com/dystonse/dystonse-tools)** Some Java-based tools from 2017. Development paused / discontinued.
   * **Import tool** This tool makes a request to the VBB real time HAFAS API (See explanations here) to get the current position and delay of vehicles and writes them into a MySQL table. _(working)_
   * **Geocode tool** This tool is in very early development and does not do what it's supposed to do. It can currently be used to view small subset of the collected data on a map. _(partly working)_
   * **Prediction tool** This tool will use statistic algorithms to form a model that can predict the future delay of vehicles based on the current delay and other relevant predictive variables. _(no code, just development notes)_

## News and Contact

You can follow [@dystonse](https://twitter.com/dystonse) on Twitter to stay up to date or get in touch.
