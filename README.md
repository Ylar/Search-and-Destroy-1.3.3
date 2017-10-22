# Search and Destroy 1.3.3 - 22 October 2017
Good morning ninjas, we have a new update today.  As usual, if there are any problems, let me know and I'll do
what I can.  Here we go:

- The campaign type detect should correctly identify the cp type when a room and the area 
  it's in have the same name.

- The display glitch where targets don't show up should be fixed.  Let me know if not.

- The current 'xcp' target is now highlighted in the GUI window.

- Room cp targets are now sorted by area.  Special thanks to Fiendish for helping me with this.

- The font size and line spacing can now be changed in the GUI window.  The commands are 'xgui fontsize \<number>'
  and 'xgui linespace \<number>'.  Defaults are 8 and 15, respectively.

- The cp list font will change between Lucida Sans Unicode and Segoe depending on cp type.  Segoe is a bit
  narrower than Lucida and it might allow more room cp text to fit in the window.  Xgui fontsize works on
  both.  

- "nx" and "nx-" now do 'quick scan' after the run.

- Removed all but the "?" button from the window title bar.  I never used them, did anyone else?

- Added "send to front/back" to the window title bar as a right-click menu.  The title bar buttons (including
  'bring to front') usually got covered up when sending the window to back, making them un-clickable.  Not helpful.
  As long as you can right click the title bar, it's easy to bring the window to front again.

- Finally removed the 'reset gui' commands and related code.  Their only purpose was to bring the window back after it glitched out and left the screen, but since that bug no longer exists there is nothing to reset anymore.

- Removed much of the spam that happens on Mapper Extender install, and when you take a new cp.  Also removed some
  old debugging output as well as "cp ch" and other echoes when the plugin sends commands to the mud.  The output
  looks and feels a lot cleaner now.

- Continued the trend of more code clean-up, regexp simplification, neater output appearance, and all that.

That's all for now.  Happy searching and destroying, and thanks for all your support!


# Search and Destroy 1.3.2 - 22 September 2017
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

# Search and Destroy 1.3.1 - 14 June 2017
Bug fixes:
- hunt trick will now correctly terminate after trying to hunt something that doesn't exist.
- hunt trick will now correctly terminate if you try to do it while resting, sitting, or sleeping.
- hunt trick and quick-where will no longer use 1.mob for its first
try.  It will just do 'hunt mob' or 'where mob'.  I don't think it matters which is used,
it seems to target the same thing either way, I just didn't like 1.mob.  If problems with
it let me know and I can change it back.
- campaign target window will now populate when taking a CP from a questor.  Before, it would
only populate when requesting from Commander Barcett.
- the problem with 'xrunto' sometimes taking you to a random-ish room is mostly fixed. If 
xrunto takes you to the wrong area, e.g. Fantasy Fields instead of 'fields' (Killing Fields)
go to (in this case) Killing Fields and 'xset mark' the start room again and that should fix it.

New feature:
- Auto-noexp!  When you're at low TNL and you can take a campaign at your current level, 
 it will turn on noexp and prevent you from over-levelling and missing a campaign.

   When plugin is installed, it defaults to off.  To turn it on, do 'xset noexp (amount)'.
 If you're on a CP but can take a new one at your current level, noexp will kick on 
 when your TNL drops below the given amount.  Noexp will kick back off after you finish
 your current CP and then go and take another one.  You can also toggle noexp off 
 manually via 'noexp' as usual.  For low levels I suggest setting it at 1000 TNL or so,
 and around 500 when you get higher and mobs award less XP.  You may need to go higher
 if there's a lot of double stacking with your daily blessing bonus.
 
# Search and Destroy 1.3.0 - 31 May 2017
- Search and Destroy is once again being actively worked on, and this time I'm in charge!
Good times are ahead!
- The bug causing the GUI window to 'jump' and leave the screen when you try to move it has
been fixed.  It is no longer possible for the window to get lost, stuck, or otherwise go
beyond the edges of the screen.
