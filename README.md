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
Unless anyone actually requires the complex versions, I'm looking at gutting the 
command interface and making it simpler and more consistent.

It's going to be hard to top automatic noexp in terms of feature additions, but adding new features was never the primary objective.  There has been some speculation as to the reasons why I took up Search and Destroy, it comes down to these:\

 - I want to learn, and hands-on projects like this one are what works best for me.  I've never been able to get started from
 programming "how to" books or documentation, not because there's something wrong with them per se, but because my mind sometimes has trouble filling in the gulf between an abstract concept and and the real problems it could be used to solve.  A working script lets me see applied concepts and results side by side.  Observing how changes to the code affects the results helps me understand how an arbitrary result dictates the code required.  It's like an island in between.  Then, if a solution requires things I don't know, it's a lot easier to research them specifically and fill in those gaps.  That's what works and makes sense for me, so that's how I approach it.
