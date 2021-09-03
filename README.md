# VIOSO-Unity-HDRP
Warp and Blend integeration for multi-projection calibrations into Unity's HDRP pipeline.

# How to use

1. Create this folder directory: Assets\plugins\VIOSO and place there the 3x files: VIOSOWarpBlend.cs, VIOSOWarpBlendPP.cs, VIOSOWarpBlend64.dll
2. The shader file VIOSOWarpBlend.shader must be placed in a "Resources" folder under Assets otherwise it will not be built outside the editor.
3. Add VIOSOHDRPcamera.cs to each of your output cameras.
4. In the VIOSO folder add your calibfile (.vwf) and VIOSOWarpBlend.ini
5. Finally, to activate the effect: 
Go to Edit > Project Settings and select the HDRP Default Settings tab.
Scroll down until you find the Custom Post Process Orders section. Add VIOSOWarpBlendPP at the "After Post Process" injection point.

Now You should be able to see the shader in play mode, as usual keep an eye on VIOSOWarpBlend.log file to monitor errors.
- More info about VIOSO/Unity Integration: https://helpdesk.vioso.com/documentation/integrate-3d-engines/unity/
- Note: for better synchronisation of effects (shadows/lighting..etc) between displays, you can work in a single view warping mode by using a 2D .vwf export.
- 
# Limitation
- Please note that some of Unity's post processing effects like bloom, motion blur..etc are not properply synced in multi-display mode.
