# OpenColorIO-Configs > Slimmed for Blender
**OpenColorIO-Configs Slimmed to the Bare Bones for Blender**
  + **Faster to d/l, and takes up less drive space:** This package is ~50Mb; **OpenColorIO-Configs** source files are several Gb.
  + **Simplifies the list of Color Settings:** From dozens down to 15, of which you'll commonly only use three.

***

This is **NOT** intended for prefessional production environments, but for hobbyists who want a more convenient way to try out ACES.

***

## Backstory

Inspired by Mario Cazares' videos (links below) on ACES in Blender, I gave it a try, but ran into two inconveniences:
  + The full set of ACES configs from **colour-science/OpenColorIO-Configs** comes in at several Gb. The v1.2 folder is several hundred Mb by itself.
  + The list of Color Spaces is so long, it gets cut off in the dropdown

I reduced the **colormanagement** folder to ~50Mb by:
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
