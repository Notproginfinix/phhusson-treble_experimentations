# STEPS TO INSTALL GSI ON A SAMSUNG GALAXY A13 *SM-A135F*
## TESTED WITH: AOSP BY TREBLEDROID, CRDROID, LINEAGEOS 21 TD BY ANDYYAN, AND PIXELOS!!
PREREQUISITES: SAMSUNG A13 (SM-A135F) ROOTED WITH MAGISK AND UNLOCKED BOOTLOADER!!! <-- HIGHLY IMPORTANT



[Link to TWRP](https://xdaforums.com/t/recovery-twrp-3-6-11-unofficial-for-samsung-a135f-a13.4485961/)

[Link to CRDROID Rom](https://github.com/naz664/crDroid_gsi/releases)

[Link to LineageOS (Vanilla) By Andy Yan](https://sourceforge.net/projects/andyyan-gsi/files/lineage-21-td/lineage-21.0-20241118-UNOFFICIAL-a64_bvS.img.gz/download)

[Link to LineageOS (GAPPS) By Andy Yan](https://sourceforge.net/projects/andyyan-gsi/files/lineage-21-td/lineage-21.0-20241118-UNOFFICIAL-a64_bgN-signed.img.gz/download)

[Link to AOSP (Only get arm32_binder64-ab-vanilla.img.xz)](https://github.com/TrebleDroid/treble_experimentations/releases)

[Link to PixelOS Download](https://master.dl.sourceforge.net/project/thegsis/PixelOS/02032023/PixelOS-13-a64_bgN-UNOFFICIAL.img.xz?viasf=1)

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
Update: Calling/VOLTE is broken?? with flossims. Use whatsapp or data to call/text. Messaging works though.

Credits: All CRdroid/GSI devs, mcrazymanu for the TWRP and magisk for the root step, extra credits goes out to anyone involved in development for this phone/chipset (eg. physwizz)