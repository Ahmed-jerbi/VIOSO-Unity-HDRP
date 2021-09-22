# VIOSO-Unity-HDRP
Warp and Blend integeration for multi-projection calibrations into Unity's HDRP pipeline.
<p align="center">
<img src="https://northeurope1-mediap.svc.ms/transform/thumbnail?provider=spo&inputFormat=png&cs=fFNQTw&docid=https%3A%2F%2Fvioso-my.sharepoint.com%3A443%2F_api%2Fv2.0%2Fdrives%2Fb!QDylcjLXZEKJrvQmYFsy0fga1TPeY-NGuBsiQxhiwXJSsKMXCfVhQpY-RA8_M51Y%2Fitems%2F01ODCTD46UG47A7ZILHJA34QDPBMXQWMDI%3Fversion%3DPublished&access_token=eyJ0eXAiOiJKV1QiLCJhbGciOiJub25lIn0.eyJhdWQiOiIwMDAwMDAwMy0wMDAwLTBmZjEtY2UwMC0wMDAwMDAwMDAwMDAvdmlvc28tbXkuc2hhcmVwb2ludC5jb21AMTc3YjA5ZTYtOTQ3MC00OTVkLWFlMTgtNDczNGMwMDkyMzQxIiwiaXNzIjoiMDAwMDAwMDMtMDAwMC0wZmYxLWNlMDAtMDAwMDAwMDAwMDAwIiwibmJmIjoiMTYzMjMxMjAwMCIsImV4cCI6IjE2MzIzMzM2MDAiLCJlbmRwb2ludHVybCI6IlVYSmRvMU96VVg3TExsMW8vYUtYN0pJcFlMTWtUVHhnUFMvNXMwenUrY1E9IiwiZW5kcG9pbnR1cmxMZW5ndGgiOiIxMTUiLCJpc2xvb3BiYWNrIjoiVHJ1ZSIsInZlciI6Imhhc2hlZHByb29mdG9rZW4iLCJzaXRlaWQiOiJOekpoTlROak5EQXRaRGN6TWkwME1qWTBMVGc1WVdVdFpqUXlOall3TldJek1tUXgiLCJzaWduaW5fc3RhdGUiOiJbXCJrbXNpXCJdIiwibmFtZWlkIjoiMCMuZnxtZW1iZXJzaGlwfGplcmJpLmFobWVkQHZpb3NvLmNvbSIsIm5paSI6Im1pY3Jvc29mdC5zaGFyZXBvaW50IiwiaXN1c2VyIjoidHJ1ZSIsImNhY2hla2V5IjoiMGguZnxtZW1iZXJzaGlwfDEwMDMyMDAwOTkxMGZjZjRAbGl2ZS5jb20iLCJzZXNzaW9uaWQiOiIzY2EyNTA2NS01NzNkLTQxZjYtODg1OS05ZGY3YmQxZTg1MTIiLCJ0dCI6IjAiLCJ1c2VQZXJzaXN0ZW50Q29va2llIjoiMyIsImlwYWRkciI6Ijg5LjI0NS4xOTEuMTAzIn0.bEZUMFB3VU1CYS9lekhYc1NZWU1RbU5mRXc1YXFyMXN6QXpNMkVNc1ZQST0&cTag=%22c%3A%7B0F3E37D4-0BE5-413A-BE40-6F0B2F0B3068%7D%2C1%22&encodeFailures=1&width=3840&height=1766&srcWidth=&srcHeight=" alt="HDRP Vioso" style="height: 500px; width:650px;" />
<p/>

# How to use

1. Create this folder directory: Assets\plugins\VIOSO and place there the 3x files: VIOSOWarpBlend.cs, VIOSOWarpBlendPP.cs, VIOSOWarpBlend64.dll
2. The shader file VIOSOWarpBlend.shader must be placed in a "Resources" folder under Assets otherwise it will not be built outside the editor.
3. Add VIOSOHDRPcamera.cs to each of your output cameras.
4. In the VIOSO folder add your **calib file (.vwf) and VIOSOWarpBlend.ini**
5. Finally, to activate the effect: 
Go to Edit > Project Settings and select the HDRP Default Settings tab.
Scroll down until you find the Custom Post Process Orders section. Add VIOSOWarpBlendPP at the "After Post Process" injection point.

Now You should be able to see the shader in play mode, as usual keep an eye on VIOSOWarpBlend.log file to monitor errors.
- More info about VIOSO/Unity Integration: https://helpdesk.vioso.com/documentation/integrate-3d-engines/unity/
- **Note**: for better synchronisation of effects (shadows/lighting..etc) between displays, you can work in a single view warping mode by using a 2D .vwf export.

# Limitation
- Please note that Unity does not properly sync some post-processing effects between multiple displays like bloom, motion blur..etc. Therefore, make sure your application runs smoothly on all outputs first before adding warp & blend.
