# dystonse
<p align="center">
  <img src="https://github.com/lenaschimmel/dystonse/blob/master/header_white.png?raw=true" alt="Header image with dystonse logo"/>
</p>

I'm preparing my master thesis on _dystonse_, a routing algorithm for public transit with the following key characterstics (as they are commonly defined in the respective research field):

 * __Dynamic__: the cost function ( = travel time) varies over time, which is the case for scheduled public transit
 * __Stochastic__: the cost function ( = travel time) is not a deterministic prediction of the actual travel time, but a probability distribution
 * __Online__: The algorithm does not return a final output upfront, instead it iterates _en route_, while the user is actually traveling, incorporating updated real time information to yield the best routing that is currently archievable
 
The software will be implemented in C++ and operate on _GTFS static_ and _GTFS realtime_ data. To enable a field test in Berlin, Germany, I'm currently developing [dystonse-tools](https://github.com/lenaschimmel/dystonse-tools) to bring Berlins realtime data into the appropriate format.
