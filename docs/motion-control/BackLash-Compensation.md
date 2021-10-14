# Backlash Compensation

According to Jason we get a 0.2-0.25mm backlash in the X and y directions

From what I can gather you can try to compensate for backlash in one of two ways
Ether at the firmware level or at the post-processor level (the thing that turns the 3d model into g-code)

It doesn't look like backlash compensation was ever implemented in the duet firmware
but someone did implement a post-processor for fusion 360 which has it

  * https://github.com/BruceRoyce/UltimateRepRapPost
  * https://forum.duet3d.com/topic/21778/the-ultimate-reprap-post-processor-for-fusion-360/2?_=1634213191322
  * https://forum.duet3d.com/topic/4665/backlash-compensation/31
