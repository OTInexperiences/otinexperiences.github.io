---
layout: page
title: GRose User Guide
date: 2011-07-27 15:35:35 +0000
author: Alan
categories: []
tags: []
permalink: "/grose-user-guide/"
original_url: http://ab48.uk/otblog/grose-user-guide/
recovery_source: wordpress_xml
recovery_status: recovered
redirect_from:
  - "/otblog/grose-user-guide/"
---
<h2>Axes</h2>
The  GRose program assumes the following axis allocations
<ul>
<li>X is the headstock horizontal offset which is the horizontal movement that results when the main spindle rosette moves against the rubber.</li>
<li>Y is the headstock vertical offset which is generally zero but which will occur when the chuck is being used.</li>
<li>Z is the pumping offset which is the movement in the spindle direction as a result of the pumping rosette moving against a rubber.</li>
<li>C is the main spindle rotation axis</li>
<li>V is the cutter depth movement axis</li>
</ul>
<p style="text-align: center;"><a href="/assets/placeholder-original-image.svg"><img alt="" class="aligncenter size-thumbnail wp-image-1340" height="150" src="/assets/placeholder-original-image.svg" title="axes" width="150"/></a></p>
<h2>Functionality</h2>
<h3>Spindles</h3>
The program supports two spindles, a main spindle and a pumping spindle. These spindles can each contain up to 20 rosettes.  The outlines of all rosettes on a spindle are combined together in order to make the shape defined by a single rotation of the spindle. This outline is defined for any angular position either as a corresponding single radius value  returned is the global variable<strong> #&lt;_result&gt;</strong> or as a two dimensional vector value returned in the global variables <strong>#&lt;resultX&gt;</strong> and<strong> #&lt;_resultY&gt;</strong>.

There are two ways of combining the rosettes together.
<ol>
<li>The default method whereby at each anglular position around the spindle the radius value returned is the largest value taken over all the individual rosettes on the spindle. Thus for three rosettes R1, R2 and R3 the overall radial value is max(r1,r2,r3)  where ri is the radius of rosette Ri at the given angle.</li>
<li>The blending method. Here each rosette can be given a weighting value called its blend.  The blend value can be either positive or negative and may be any decimal.  Then at each angular position the radius of each rosette is multiplied by its blending value and then all are summed together. This total value is then normalised by dividing it by the sum of all the individual blending coefficients. So if a spindle has three rosettes R1, R2 and R3 with blend values b1, b2 and b3 the overal radial value at any angle is given by  r1 * b1 + r2 *b2 + r3 * b3 / (b1 + b2 + b3)  where ri is the radius of rosette Ri at the given angle.</li>
</ol>
<h2>Spindle data layout</h2>
The group of variables that make up the data for a spindle are those starting at #200 for the main spindle,  #400 for the pump spindle and #600 for the chuck (not yet implemented). The first value in each case is a count of the number of items on the spindle, or stages on the chuck.
<pre>#&lt;_Main_Count&gt;       = #200 ( Number of Rosettes on Main        )
#&lt;_MainSpindle&gt;      = 200  ( start of Rosettes on Main Spindle    )
                            ( data starts at #&lt;_MainSpindle + 1&gt;    )
#&lt;_Pump_Count&gt;       = #400 ( Number of stages on Pump        )
#&lt;_PumpSpindle&gt;      = 401  ( start of rosettes on pump spindle )

#&lt;_Chuck_Count&gt;      = #600 ( Number of stages on Chuck        )
#&lt;_Chuck&gt;            = 601  ( start of stages on chuck        )</pre>
The data block for each item on the spindle comprises of a single value which is the address of the rosette itself. All other data is stored in a rosettes data block.
<h2>Rosettes</h2>
All rosettes have several pieces of data in common. These are
<ol>
<li>An integer defining the type of rosette</li>
<li>A flag value indicating if the rosette is to be included (to be removed)</li>
<li>A  major radius.</li>
<li>A minor radius.</li>
<li>A phase value.</li>
<li>A blending coefficient.</li>
</ol>
These are held at the following offsets from the start of the data block representing the rosette.
<pre>(Common Offsets                                            )
(  R_Type        = 0;    // type of rosette                )
(  R_Include     = 1;    // flag to include rosette        )
(  R_R           = 2;    // Major radius of rosette        )
(  R_r           = 3;    // Minor radius of rosette        )
(  R_Phase       = 4;    // phase of rosette               )
(  R_Blend       = 5;    // blend coefficient              )</pre>
The following rosettes are defined
<ol>
<li>An elliptical rosette, R_Type = 0 requires just the values defined above. R_R is the major radius of the ellipse and R_r its minor radius. If these are equal we have a circle.</li>
<li>A polygon rosette R_Type = 1 R_R is the circumradius of the polygon. It also requires two further values R_Numsides which defines the number of sides and R_IsStar which defines if the polygon is a star. If this is the case then R_r is the inner radius of the star.  <em>At present there is a slight problem with stars. The algorithm I used in OTWorkbench seems to create errors so I have used a simpler interpolation algortithm. However this makes the stars come out a petal type shapes. This problem needs to be addressed.</em></li>
<li>A sinusoidal waveform rosette. R_Type=2 where here R_R is the mean radius of the rosette. Three further values are required these are the frequency and amplitude of the wave called R_Frequency and R_Amplitude together with a flag value R_abs which if set to 0 returns the standard wave but if set to 1 reflects the negative parts in order to produce a rectified wave.</li>
<li>Epicycloid rosette R_Type = 3 uses both R_R and R_r in the generation of the outline.</li>
<li>Hypocycloid rosette R_Type = 4 which like the epicycloid above uses both R_R and R_r.</li>
<li>Spiral Rosette R_Type=5  which implements r = a + b * angle</li>
<li>A petal Rosette R_Type=6 whoose outline is a N sided petal. R_R is the outer radius and R_r is the inner radius of the petal.</li>
</ol>
<pre>(  Polygon Rosette                            )
(  R_Numsides    = 6;    // number of sides in polygon            )
(  R_IsStar      = 7;    // flag true if star shape            )

(  Wave Rosette                                )
(  R_Frequency   = 6;    // frequency of wave                )
(  R_Amplitude   = 7;    // Amplitude of wave                )
(  R_Absolute    = 8;    // flag set true if absolute values used    )

(  Helix Rosette                            )
(  R_Pitch       = 6;    // pitch of spiral                )
(  R_Gradient    = 7;    // gradient of spiral                )
(  R_Exponent    = 8;    // Exponent of spiral                )
(  R_Logrithmic  = 9;    // flag set true if spiral is logarithmic    )</pre>
<h2>Rosette data layout</h2>
Rosettes are represented by a block of 10 variable values stored in a common area starting at user variable #800 which is a count of the number of rosettes defined in the area.

#&lt;_Rosette_Count&gt;    = #800    ( first item is count of rosettes    )
#&lt;_Rosettes&gt;               = 801    ( start of rosette data            )
#&lt;_RosettesOffset&gt;    = 10    ( record size for Rosette        )

The data for each rosette is stored in a block of 10 user varaibles although currently only 9 are used.  The second common value R_Include is carry over from my original code and was used there to determine is a rosette was being used and displayed in the UI. This value is redundant in this application because the same effect can be achieved by setting a rosettes blend value to zero. I just havent had the inclination yet to remove it from the code.
<h2>Chuck</h2>
This has not been implemented yet.
<h2>General Variables</h2>
The program uses some general variables  which are listed below
<pre>( Main Program locations                                       )

#&lt;_UseRotary&gt;        = #49    (flag is 1 if a rotary machine   )
#&lt;_UseMainSpindle&gt;   = #50    (flag is 1 if using main spindle )
#&lt;_UsePumpSpindle&gt;   = #51    (flag is 1 if using pump spindle )
#&lt;_UseChuck&gt;         = #52    (flag is 1 if using chuck        )
#&lt;_UseSurface&gt;       = #53    (flag is 1 if using surface      )
#&lt;_ToolOffset&gt;       = #54    (tool offset position            )
#&lt;_UseBlending&gt;      = #55    ( flag is 1 if using blending    )
#&lt;_InvFeedrate&gt;      = #56    ( inverse feed rate              )
#&lt;_Feedrate&gt;         = #57    (Linear feed rate                )
#&lt;_Safeheight&gt;       = #58    (safe height                     )</pre>
The <strong>UseRotary</strong> flag is set to 1 if like me you are using a rotation of some type. It may be a rotating spindle or alternatively a rotary table. When set positional moves will include an angular axis.

You set the values of <strong>UseMainSpindle, UsePumpSpindle, UseChuck</strong> and <strong>UseSurface</strong> to a value of 1 if you wish that component to be included in the program. <strong><em>Note that surfaces are not yet implemented.</em></strong>

The <strong>ToolOffset</strong> is an important value as it represents the position of the cutting tool relative to the centre of the main spindle. Its value is added to the radius of the spindle outline at each angular value. Thus by adjusting this value different sizes of shapes may be generated.

<strong>UseBlending</strong> is a global variable that determines how rosettes are combined together on a spindle. Note that both spindles use this flag so you cannot have only one spindle where blending is used. It is either both or neither.

<strong>InvFeedrate</strong> is the value used in Inverse time mode for the value of F, which is used when the UseRotary flag is set true. In that case a G93 code is output. The emc manual describes the inverse time mode as  " In inverse time feed rate mode, an F word means the move should be completed in [one divided by the F number] minutes. For example, if the F number is 2.0, the move should be completed in half a minute."

<strong>Feedrate</strong> is the value given to F in the standard G94 units per minute mode.

Finally <strong>Safeheight</strong> is the cutter depth value that should be set to clear the work and all obstacles.
<h2>General Comments</h2>
<ol>
<li>The program is designed to generate absolute positions.</li>
</ol>
 

 
