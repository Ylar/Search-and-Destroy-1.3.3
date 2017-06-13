# Search-and-Destroy-1.3.1

This update is mostly bug fixes, one slightly bigger than the others.

There is also a new feature, which I think a lot of you will like.

Bug fixes:
- hunt trick will now correctly terminate after trying to hunt something that doesn't exist.
- hunt trick will now abort if you try to do it while resting, sitting, or sleeping.
- the problem with 'xrunto' sometimes taking you to a random-ish room is mostly fixed.

  So what was happening is that 'xrunto' wants to run you to the 'start room' for that 
 area, which is set via 'xset mark'.  But if the area didn't have a start room (e.g. it
 was never set, or it somehow got lost), the the plugin would look to your mapper DB
 and get the lowest-numbered room uid in that area and run you there.  Apparently, 
 the assumption was that the lowest-numbered room is the likely start room since it
 is presumably the first to be created.
  Unfortunately, that only proved true for 2 or 3 areas out of 231 total. The rest
 of the time, the lowest room id could be anywhere in the zone, and actually, a lot
 of the time the destination room wasn't the lowest uid at all.  Suffice it to say
 that this was not brilliant, and got me killed more than once.
  The new approach is if no 'xset mark' start room exists, the plugin now has a
 lookup table with a 'default' start room for nearly every area, and it will
 run you to that room instead.  Most of the time it's the room linking to the
 continent or parent zone, but sometimes it's a few rooms in.  Some do have aggros
 but unless you run to something Xmas at low level, it generally won't kill you.
