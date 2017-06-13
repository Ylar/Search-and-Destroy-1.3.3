# Search-and-Destroy-1.3.1

This update is mostly bug fixes, one slightly bigger than the others.

There is also a new feature, which I think a lot of you will like.

Bug fixes:
- hunt trick will now correctly terminate after trying to hunt something that doesn't exist.
- hunt trick will now abort if you try to do it while resting, sitting, or sleeping.
- not a bug per se, but hunt trick and quick-where will no longer use 1.mob for its first
try.  It will just do 'hunt mob' or 'where mob'.  I don't think it matters which is used,
it seems to target the same thing either way, I just didn't like 1.mob.  If problems with
it let me know and I can change it back.
- the problem with 'xrunto' sometimes taking you to a random-ish room is mostly fixed. If 
xrunto takes you to the wrong area, e.g. Fantasy Fields instead of 'fields' (Killing Fields)
go to (in this case) Killing Fields and 'xset mark' the start room again and that should fix it.

So what was happening is that 'xrunto' wants to run you to the 'start room' for that 
area, which is set via 'xset mark'.  But if the area didn't have a start room (e.g. it
was never set, or it somehow got lost), the the plugin would look to your mapper DB
and get the lowest-numbered room uid in the zone and run you there.  Apparently, 
the assumption was that the lowest-numbered room is the likely start room since it
is presumably the first to be created.

Unfortunately, that only proved true for 2 or 3 areas out of 231 total. The rest
of the time, the lowest room id could be anywhere in the zone, and actually, a lot
of the time the destination room wasn't the lowest uid at all.  Suffice it to say
that this was not brilliant, especially if it ran you into a room of aggros and
got you killed.  Yeah, no thanks.

The new approach is if no 'xset mark' start room exists, the plugin now has a
lookup table with a 'default' start room for nearly every area, and it will
run you to that room instead.  Most of the time it's the room linking to the
continent or parent zone, but sometimes it's a few rooms in.  Some do have aggros
but unless you run to something Xmas at low level, it generally won't kill you.  As
a bonus, Upper and Lower Planes can now have a set 'xrunto' point, which I set to
the Amulet of the Planes landing room.

Some SH areas got left out due to risk of me dying a lot.  For those, it's 'runto roulette'
until I add them in, but it's a handful of areas, maybe 5 or 6.
 
 
Lastly, new feature:
 - Auto-noexp!  When you're at low TNL and you can take a campaign at your current level, 
 it will turn on noexp and prevent you from over-levelling and missing a campaign.

   When plugin is installed, it defaults to off.  To turn it on, do 'xset noexp <amount>'.
 If you're on a CP but can take a new one at your current level, noexp will kick on 
 when your TNL drops below the given amount.  Noexp will kick back off after you finish
 your current CP and then go and take another one.  You can also toggle turn noexp off 
 manually via 'noexp' as usual.
 
   To turn the feature back off, just do 'xset noexp off'. 
