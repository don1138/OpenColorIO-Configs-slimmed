# Add a Minimal Set of OpenColorIO (ACES) Configs to Blender's Color Management Settings

***

This is **NOT** intended for professional use, but for hobbyists who want a convenient way to try out ACES.

***

## Installation

  + Download these files, and navigate to the **colormanagement** folder inside the Blender app bundle.
    + on Mac: /Applications/Blender.app/Contents/Resources/2.91/datafiles/colormanagement/
  + Add the **aces** folder alongside **filmic** and **luts**
  + Replace **config.ocio*** *(forst save a backup copy of the Blender default!)* with the one provided.
  
  For usage instructions, watch the **Using ACES in Blender | Short Tutorial** video linked below.

## Known Conflicts

  + **KIT OPS** - After inserting a decal, you need to go into the Material and set the color space manually.
  + The Color Picker uses the sRGB model, even in ACES, so your sRGB color values may shift (for example, purples may shift to blue).
    + To switch to the ACES Color Picker, change line 14 in **config.ocio** to ***color_picking: Output - sRGB***

## Why A Minimized Set?

  + **Simplifies the list of Color Settings:** From dozens down to 15, of which you'll commonly use only three.
  + **It's faster to d/l, and takes up less drive space:** This package is ~50Mb; The full **OpenColorIO-Configs** source files are several Gb.
  
  + Note: Since I created this repo, the folks at Color Science have put out a release that comes to 124mb. If you prefer to use this full set of configs, you can follow the installation instructions shown above, with these changes:
    + Download [OpenColorIO Config ACES 1.2](https://github.com/colour-science/OpenColorIO-Configs/releases/download/v1.2/OpenColorIO-Config-ACES-1.2.zip)
    + Rename the **luts** folder (OpenColorIO-Config-ACES-1.2 2/aces_1.2/luts) to **aces**, and copy to **colormanagement**
    + Download **aces_1.2_config.ocio** from this repo, rename it to **config.ocio**, and relace the existing file in **colormanagement**

## Backstory

Inspired by Mario Cazares' videos (links below) on ACES in Blender, I gave it a try, but ran into two inconveniences:
  + The full set of ACES configs from **colour-science/OpenColorIO-Configs** comes in at several Gb. The v1.2 folder is several hundred Mb by itself.
  + The list of Color Spaces is so long, it gets cut off in the dropdown

So, to make the package smaller and friendler, I reduced the **colormanagement** folder to ~50Mb by:
  + Deleting all Directories except for v1.2
  + Deleting SPI3Ds that are no longer referenced in **config.ocio**
  + Stripping all Colorspaces from **config.ocio** except for:
    + The three Cazares recommends using
      + **Utility - Linear - sRGB** (for HDRIs and EXRs)
      + **Utility - sRGB - Texture** (for Color Textures, JPG and PNG)
      + **Utility - Raw** (for Non-Color Textures)
    + A few others kept for either technical or arbitrary reasons
      + **ACES - ACES2065-1**
      + **ACES - ACEScc**
      + **ACES - ACEScct**
      + **ACES - ACESproxy**
      + **ACES - ACEScg**
      + **Input - ADX - ADX10**
      + **Output - Rec.2020**
      + **Output - Rec.709**
      + **Output - sRGB**
      + **Utility - LMT Shaper**
      + **Utility - Linear - Adobe RGB**
      + **Utility - Linear - Adobe Wide Gamut RGB**
  
***

## Links
  + [OpenColorIO-Configs](https://github.com/colour-science/OpenColorIO-Configs)

Mario Cazares' videos on adding ACES to Blender
  + [Setup ACES in Blender](https://www.youtube.com/watch?v=B7FWNNDXBl0)
  + [Using ACES in Blender | Short Tutorial](https://www.youtube.com/watch?v=PkWT7HSEfJY)
