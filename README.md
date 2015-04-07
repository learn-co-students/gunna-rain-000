---
tags: api, pods
languages: objc
---

# Is it raining?

Why look outside when you can just look at your phone!

## Instructions

  1. We will be using the [forecast.io](https://developer.forecast.io/) API to get the weather. It's already downloaded
  2. Read the documentation to figure out how to get an instance of a [`Forecastr`](https://github.com/iwasrobbed/Forecastr) object. The `sharedManager` method should look just like a singleton!
  3. Get an API key from [forecast.io](https://developer.forecast.io/register)
    - after registering, you'll find your API key at the bottom of the screen.
      **You don't need to enter billing information or anything. The free plan will be more than enough.**
  4. I have setup the View Controller for you with just one large label. The goal is to say Yep if it's raining and Nope if it's not. 
  5. Call the [getForecastsForLatitude:Longitude:time:exclusions:success:failure](http://cocoadocs.org/docsets/Forecastr/0.1.2/Classes/Forecastr.html#//api/name/getForecastForLatitude:longitude:time:exclusions:success:failure:) method. It will return the current weather in the `@"currently"` key with a `precipProbability` key. If that key is `1` then it is raining! **Remember any optional argument or block you can usually just put in `nil` and it will work**
  6. As you can see, this method requires a lat/lng. Sure, you could enter this manually, but that's not as fun! This is a great opportunity to try out current location in iOS 8. <a href="http://stackoverflow.com/questions/26134641/how-to-get-current-location-lat-long-in-ios-8">Here's a great StackOverflow on finding a user's current location</a>.
   **DO NOT SKIP OVER THE STUFF ABOUT InfoPlist.strings file! You need to implement this for it to work!**
  7. This method separates the success and failure case into two separate blocks. Update the label with the appropriate message when you get the weather.
  8. If it's not raining right now, find some place it is raining. I'd checkout Portland...usually it's raining there.

## Extra Credit

  * So we can get the chance of precip. Adjust the color of the UIlabel to signify the probability of precip. So full green if 0 percent. 50% chance of rain should be black and a 100% chance of rain should be full red.
