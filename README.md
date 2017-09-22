# Search-and-Destroy-1.3.2

Update 1.3.2 improves upon the last with new bug fixes and by addressing some of
the things that give Search and Destroy a bit of a clunky feel.  I'm a little bit
nervous because of the potential for glitches, but (fingers crossed) it's working
for me so hopefully it will work for you too!  Take a look:

- Fixed the issue with auto-noexp sometimes not kicking in when double is active and
TNL drops below the set point.  Note, in order for it to work, you must have timers
enabled and the timer interval set to zero.

- Auto-noexp will work with exprate and non-exprate experience messages.

- Added filter to fix "Miss Area" mob keywords in Siren's Resort.

- Added (some) missing areas to the list of default area start rooms.  I haven't
had anyone raise issues with the revamped xrunto approach, which is a good sign.
I do plan on re-visiting this as there are still improvements that could be made.

- Added 'xcp' as an alias for 'xcp 1'.

- 'xcp' will retry if it fails because of "no object or data busy".  

- If you hit 'nx' too many times, you can go back by using 'nx-' or right-clicking
  the 'nx' button.

- Enlarged GUI buttons to make them easier to click.

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

- Removed a lot of spammy text output (old debugging messages, etc.) plus other 
general cleaning-up.

# Update 21 Sep 2017 @ 20:00 MUD time  

On short notice, I'm implementing a change to correct a major omission that was brought
to my attention.  A few other things I was working on also made it in.  Hopefully they
aren't horribly broken:

- Hunt trick should now work for Navigators hunting through portals.  Previously, 
it would break because the portal hunt message didn't match the regexp.  It looks
functional to me now, but I'm not a navigator so please let me know if and when this
breaks.  If it works, it should remove the need to patch it yourself.

- Navigator auto-hunt will be trickier.  For now, when you try to hunt through a portal, you
will be prompted to enter the portal and then autohunt again.

- The autohunt command interface has been redone, in line with the general simplification
plan mentioned above.  If anything goes wrong with it, let me know.  This wasn't rushed,
exactly, it just hasn't had as long to be tested as other things, but I fixed all of the
issues that I was able to identify.

Please let me know if anything breaks or there are other issues.  Everything is working for me; it's been several dozen campaigns without any errors or having to stop and fix any problems.  When I upload these files, they're identical to what I'm running and have been testing.  Ideally that means good times for everyone, but if not, come talk to me.  Please be advised, my work schedule is exhausting, it fucking sucks and will only get worse as the god-forsaken holiday hell season approaches.  But if you contact me I'll do my best to get back to you whenever I manage to be awake and/or around.

It'll be pretty hard to top automatic noexp as far as adding new features goes.  But adding new features was never the primary objective:  Bug and problem fixing was, and there's still plenty to be done on that front.  For now, I hope you enjoy this update as I believe it to be a noticeable improvement even over 1.3.1.

Happy searching and destroying, ninjas.
- 
