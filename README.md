# Search-and-Destroy-1.3.1

This update is mostly bug fixes, one slightly bigger than the others.

There is also a new feature, which I think a lot of you will like.

Bug fixes:
- hunt trick will now correctly terminate after trying to hunt something that doesn't exist.
- hunt trick will now abort if you try to do it while resting, sitting, or sleeping.
- the problem with 'xrunto' sometimes taking you to a random-ish room has been fixed, or
maybe "worked around" is a better way to put it.  The problem happened when trying to
'xrunto' an area for which no start room had been set via 'xset mark'.  In this case,
the plugin would look at the room uid's for that area, and run you to the room with
the lowest-valued uid, apparently on the basis that the start room is the first one
to be created (which would give it the lowest-numbered uid).  
