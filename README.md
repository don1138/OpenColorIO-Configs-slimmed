# Add a Minimal Set of ACES Settings to Blender

***

This is **NOT** intended for professional use; it's just me playing around to figure out ACES.

If you want a good practical, slimmed version of ACES to work with in Blender, check out [**Filmic Blender**](https://github.com/sobotka/filmic-blender).

***

## Installation

  + Navigate to the **colormanagement** folder inside the Blender app bundle.
    + on Mac: /Applications/Blender.app/Contents/Resources/2.91/datafiles/colormanagement/
  + Add the **aces** folder alongside **filmic** and **luts**.
  + Replace **config.ocio** *(first save a backup copy of the Blender default!)* with the one provided.
  
  For usage instructions, watch **[Using ACES in Blender](https://www.youtube.com/watch?v=PkWT7HSEfJY)**.

## Alternate Option – The Full Set

Shortly after I created this repo, the folks at **Color Science** posted a release that comes to 124mb. If you want to use the full set of configs, you can follow the installation instructions shown above, with these changes:
  + Download **[OpenColorIO Config ACES 1.2](https://github.com/colour-science/OpenColorIO-Configs/releases/download/v1.2/OpenColorIO-Config-ACES-1.2.zip)**.
  + Rename the **luts** folder *(OpenColorIO-Config-ACES-1.2 2/aces_1.2/luts)* to **aces**, and copy to the **colormanagement** folder.
  + Download **aces_1.2_config.ocio** from this repo, rename it to **config.ocio**, and relace the existing file in the **colormanagement** folder.

## Known Conflicts

  + **KIT OPS** - After inserting a decal, you will need to go into the Material and set the color space manually.
  + The Color Picker uses the sRGB model, even in ACES, so your sRGB color values may shift *(for example, purples may shift to blue)*.
    + To switch to the ACES Color Picker, change line 14 in **config.ocio** to `color_picking: Output - sRGB`.

## So, Why Make A Minimized Set?

  + **Simplified list of Color Settings:** From dozens down to 15, of which you'll commonly use only three.
  + **Faster to D/L:** The full **OpenColorIO-Configs** source files are several Gb.
  + **Takes up less drive space:** About ~50Mb.
  
Inspired by Mario Cazares' videos (links below) on ACES in Blender, I gave it a try, but ran into two inconveniences:
  + The full repo of ACES configs from **colour-science/OpenColorIO-Configs** is several Gb. The v1.2 folder by itself is several hundred Mb.
  + The list of Color Spaces is so long, it gets cut off in the dropdown.

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
  + [Filmic Blender](https://github.com/sobotka/filmic-blender)

Mario Cazares' videos on adding ACES to Blender
  + [Setup ACES in Blender](https://www.youtube.com/watch?v=B7FWNNDXBl0)
  + [Using ACES in Blender | Short Tutorial](https://www.youtube.com/watch?v=PkWT7HSEfJY)
