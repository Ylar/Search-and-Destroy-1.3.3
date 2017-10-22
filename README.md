# Search and Destroy-1.3.3

# Search and Destroy 1.3.2 - 22 Sept 2017
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

Lastly, on short notice, I'm implementing a change to correct a glaring omission that was brought
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
issues that I was able to identify.  Type "search help" to see the new command syntax.
