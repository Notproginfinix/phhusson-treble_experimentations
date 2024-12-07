# STEPS TO INSTALL GSI ON A SAMSUNG GALAXY A13 *SM-A135F*
## TESTED WITH: AOSP BY TREBLEDROID, CRDROID, LINEAGEOS 21 TD BY ANDYYAN
PREREQUISITES: SAMSUNG A13 (SM-A135F) ROOTED WITH MAGISK AND UNLOCKED BOOTLOADER!!! <-- HIGHLY IMPORTANT

Disclaimer:

I am not responsible for lost data, identity theft, lost money, security vulnerabilities, bricked devices or any other hardware or software malfunctions that comes as a result of trying these GSI flashing steps.
BACKUP YOUR DATA AND OLD rom BEFORE trying these steps.

 *
 * Your warranty is now void.
 *
 * We are not responsible for bricked devices, dead SD cards,
 * thermonuclear war or you getting fired because the alarm app failed. Please
 * do some research if you have any concerns about features included in this ROM
 * before flashing it! YOU are choosing to make these modifications, and if
 * you point the finger at us for messing up your device, we will laugh at you. Hard & a lot.
 *
 *

With that out of the way, here are the steps, pretty straightforward.

1. Flash TWRP
2. Wipe -> Format Data -> yes -> format the data
3. Main menu -> Reboot -> Recovery
4. Download CRdroid GSI (10.8) (a64_bvN-unofficial) by nazim and samsung multidisabler zip.
5. Unzip, transfer to phone and flash CRdroid as image to /system in TWRP.
6. Wipe -> advanced wipe -> Data -> Repair or change FS -> Change to EXT4
7. Reboot recovery
8. Wipe -> Advanced wipe -> data -> repair or change FS -> Change to F2FS then reboot back to recovery
9. Read step 9.1 if you want gapps, otherwise, flash multidisabler, go to wipe menu -> advanced wipe -> select dalvik and cache, then wipe, reboot to system and enjoy your GSI!
# 
9.1 Do the steps from step 9, then in the system, download microG, which is a version of Gapps that doesnt put your phone in a bootloop.
10. ENJOY!!!

### NOTE: Experimental - some features like calling do not work, I am currently looking for a fix to all mobile data/calling related features. 
 Update: Inside some buildings, not much signal is received (thank you australian sim providers).  MESSAGING HAS WORKED!! Inside a building,  messaging/calling isnt really needed, and if you need it, you can use an app like whatsapp on a wifi network.
 Update 2. Leaving the house, going somewhere for a bit, a perfect opportunity to test outside calls/texts. Will post an update if it works.

Credits: All CRdroid/GSI devs, mcrazymanu for the TWRP and magisk for the root step, extra credits goes out to anyone involved in development for this phone/chipset (eg. physwizz)