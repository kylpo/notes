# Floating Points
Or, the reason ___ = ____ in javascript

This is just the notes I’ve taken from [Bartek Szopka: Everything you never wanted to know about JavaScript numbers -- JSConf EU 2013](https://www.youtube.com/watch?v=MqHDDtVYJRI)’s excellent talk.

Javascript isn’t the only offender. Also Java, …

Position of Signifiand depends on the exponent

Sign      Exponent         .         Significand
[1] bit    [1-8?] bits                  [rest of bits]

The more bits for integer, the less we have for fraction part.

Floating Point has 2 zeros: 0, -0
