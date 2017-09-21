# Search-and-Destroy-1.3.2

This update improves upon the last with new bug fixes and by addressing some of
the things that give Search and Destroy a bit of a clunky feel.  I'm a little bit
nervous because of the potential for glitches, but (fingers crossed) it's working
for me so hopefully it will work for you too!  Take a look:

- Fixed issue with auto-noexp sometimes not kicking in when double is active and
TNL drops below the set point.  Note, in order for it to work, you must have timers
enabled and the timer interval set to zero.

- Auto-noexp will work with exprate and non-exprate experience messages.

- Mob keywords will always be sent to the MUD lower case.

- Added filter to fix "Miss Area" mob keywords in Siren's Resort.

- Added (some) missing areas to the list of default area start rooms.  I haven't
had anyone raise issues with the revamped xrunto approach, which is a good sign.
I do plan on re-visiting this as there are still improvements that could be made.

- Added 'xcp' as an alias for 'xcp 1'.

- 'xcp' will retry if it fails because of "no object or data busy".  

- If you hit 'nx' too many times, you can go back using 'nx-' or right clicking
  the 'nx' button.

- S&D now detects which type of CP is active.

- Target list is now filtered according to cp type.  This removes most of the extra 
list items displayed (mostly in area cp's) when a target location is both a valid 
area and room name.  Room cp's can still generate multiple links per target (as they
should) if the same room name exists in different areas.

- Simplified 'xcp' and 'cp check' syntax in Mapper Extender.  I get what WinkleWinkle
was doing with these crazy regexp's, but most wind up being complexity for their 
own sake.  Fiendish certainly doesn't use them in his scripts, and I can see why.  
Unless people actually require the complex versions, I'm looking at gutting the 
command interface and making it a lot simpler.
