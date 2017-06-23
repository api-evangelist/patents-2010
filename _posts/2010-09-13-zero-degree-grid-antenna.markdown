---

title: Zero degree grid antenna
abstract: A vertically polarized dipole or bicone antenna is positioned cylindrically with in many cylindrical layers of polarizing grids that slowly rotate the incident field to cross 0 degrees, i.e., 90 degrees to the horizon, and to attenuate or minimize the effects of gain nulls from reflections off of the innermost grid layer. Such an antenna is used for detecting both horizontal and vertical polarized signals over a broad bandwidth whereby the response to both polarizations is equal.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08487824&OS=08487824&RS=08487824
owner: The United States of America as Represented by the Secretary of the Navy
number: 08487824
owner_city: Washington
owner_country: US
publication_date: 20100913
---
The invention described herein may be manufactured and used by or for the Government of the United States of America for governmental purposes without the payment of any royalties thereon or therefore.

This application is related to a patent application filed on the same day by the same inventor entitled CAPACITIVE LOADED GRID ANTENNA.

The present invention generally relates to vertically polarized RF antennas and more specifically to bicone and dipole antennas.

In the signal detection environment it is often desirable to detect both horizontal and vertical polarized signals on the horizon over a broad bandwidth. It is also desirable that the response to both polarizations is equal. Optionally an antenna may be used in a vertical stack of antennas which requires cables to pass vertically by the antenna to other antennas above the antenna.

A typical solution to detecting both horizontal and vertical polarized signals over a broad bandwidth whereby the response to both polarizations is equal is to use a vertically polarized bicone antenna positioned cylindrically in many cylindrical layers of polarizing grids that slowly rotate the incident field from cross 45 degrees to close to cross 0 degrees 90 degrees to the horizon vertically polarized as shown in . Grids pass signals that are cross or perpendicular to the grid angle or pitch angle of the grids.

The components of to be received horizontal and vertical polarized signals of equal amplitude are of equal amplitude at cross 45 degrees. Thus for equal response to either polarization the grid and bicone configuration receives this component of either of the polarizations. A bare minimum of three layers of grids of grid angles 45 30 and 15 degrees rotates the cross 45 degree component from respectively cross 45 to cross 30 and to cross 15.

The bicone inside of the 15 degree grid layer finally receives the signal at cross 0 degrees vertical polarization 90 degrees to the horizon . One layer of 45 degree grids is a possible configuration that passes a to be received signal component of cross 45 degrees to the cross 0 degrees vertical polarization of the bicone although there is a 3 decibel polarization mismatch loss.

In general the amount of rotation of polarization to be done by the grids determines the bare minimum number of grid layers that is needed to minimize to a reasonably small value the polarization mismatch loss of the grids. A reasonable rule dictates that at least one grid layer is needed per 15 degrees of rotation. Thus 45 degrees of rotation requires three grid layers with grid angles of 45 30 and 15 degrees.

The grid layers are arranged radially so that the layers of larger grid angles have corresponding larger radii. In other words a grid layer s pitch angle will increase directly with an increase in radius.

In all configurations with the length of the grid lines long enough to cause reflections the distance between adjacent grid layers must be less than wavelength and the distance between the innermost grid layer and the axis of the bicone must be less than 1 wavelength. At or 1 wavelength separations cancellation of the incident and reflected signals occurs respectively between adjacent grid layers or the innermost grid layer and the axis of the bicone causing a problematic signal gain null and degraded patterns. For the innermost grid layer and the axis of the bicone case this null also occurs at higher integer multiples of a half wavelength e.g. 1.5 2.5 . . . wavelengths although of decreasing intensity as the integer multiples of a half wavelength increases.

NEC Numeric Electromagnetic Code government models using a narrow dipole antenna instead of a bicone antenna in the configuration have shown that cancellation between the innermost grid layer and a dipole starts at 0.5 not 1.0 wavelength separation. It is not known if the difference between the two cases is dependent upon the use of a bicone or a dipole.

The distance between the innermost grid and a bicone axis can quickly approach 1 wavelength at which cancellation occurs especially if the bicone is being used at frequencies where it is electrically large i.e. larger than 1 wavelength.

Additionally the grids are parasites of finite size and thus can have resonances e.g. circumferential resonances in this configuration.

Circumferential resonances occur when the circumference of the grid layer is an integer multiple of a wavelength. Such resonances usually severely degrade the required azimuthal omni patterns of the bicone at the frequencies of the resonances due to re radiation or reflection off of the grids. The resonances appear as negative spikes or nulls when illustrated in gain versus frequency plots.

Resonances can be expected to be made less severe by making the grids more broadband by making them larger. For example the heights of the grids can be increased. However measurements have indicated that increasing grid height has little effect on decreasing pattern degradation at resonance frequencies.

Additionally the circumference of grid layers can be made larger so that higher order resonances appear in the frequency band of interest. The worse case resonance is when the circumference is 1 wavelength. Usually resonances when the circumference is 3 or more wavelengths can be ignored since pattern degradation is small.

Typical measurements such as for a configuration of a bicone inside 15 and 30 degree layers of grids have shown the following severity of gain nulls see TABLE 1 .

Vertical and horizontal polarization gain decibel versus frequency wavelength plots for all azimuths are shown in respective . First and second nulls are noted for each grid layer N N Nand N respectively. The frequencies in and corresponding to the respective 1 and 2 wavelength circumferences of the 15 degree grid layer are noted at 1 and 2 whereas the frequencies corresponding to the respective 1 and 2 wavelength circumferences of the 30 degree grid layer are noted at 1 and 2 . Notice that nulls are located at or close to the circumferential wavelength points.

Note that a small space separates the 15 degree and 30 degree grids with the 30 degree grids being a little larger in radius and circumference. This results in the resonances of both grids not being exactly at the same frequency. The 30 degree grid resonances are a little lower in frequency than those of the 15 degree grids. The 1 and 2 resonance frequencies for both grids are shown on . The double resonances are seen with the first null being actually composed of two closely spaced nulls Nand N and the second null composed of two closely spaced nulls Nand N.

The nulls are at or close to the circumferential wavelength points. Gains for horizontal polarization and below the first null are spread out since the antenna configuration was below its cut in frequency resulting in the feed cable of the bicone starting to become part of the antenna and radiating asymmetrically in the azimuth plane. Measurement problems also spread out the gains above the second null.

Optionally cables are allowed to vertically pass the antenna configuration. To allow one or more cables to pass vertically by the antenna the cables are run parallel to the outermost layer of grids and outside of and insulated from the grids as shown in .

Running the cables parallel to the outermost layer of grids minimizes shunting of the antenna by the cables and upsetting the azimuth patterns since the cables are at the polarization shunted by the grids. To minimize further shunting by the cables in the area past the grids the cables should be kept away from the top and bottom of the bicone and thus should maintain at least the same radial distance from the bicone axis as in the area where the cables pass the outermost grid layer.

Describing the components of the antenna configuration in in more detail a bicone antenna is made up of two cones a top cone and a bottom cone arranged as shown. A coaxial cable feeds the bicone at the feed point of the antenna where the outer conductor of the cable is connected to the bottom cone and the center conductor of the cable is connected to the top cone . The feed angle is the angle between the two cones at a feed point and is usually picked so that the characteristic impedance Zof the bicone is that of the coaxial cable 50 ohms to ensure optimal match.

The bicone is wrapped in three layers of grids of grid angles of 15 30 and 45 degrees see also C D respectively where the separation between adjacent grids or the innermost grid and the extreme edge of the bicone is a constant value. The grid layers are arranged radially so the layers of larger grid angles are of larger radius from the antenna axis .

The grid layers are kept separated by placing foam spacers between adjacent layers or between the innermost layer and the bicone or by placing the whole configuration in a cylindrical dielectric box not shown whose top and bottom are mounted to the top and bottom of the bicone and whose top and bottom have slits on their insides in which the top and bottom edges of the grid layers are placed and held in place.

The height of the grid layers are at least that of the height of the bicone . Any cables running vertically past the antenna are run parallel to the grids of the outermost layer of grids and outside of and insulated from the grids. In the same area past the grids the cables preferably maintain at least the same radial distance from the bicone axis as in the area where the cables pass the outermost grid layer. If there is more than one cable the cables are placed symmetrically about the circumference of the outermost grid layer.

A grid is a metal line that extends from the bottom to the top of the sheet having a height . The angle the grid makes with the horizontal is the grid angle . In C D the grid angle is 45 30 and 15 degrees respectively. The width of the grid compared to the width of the non gridded area of the sheet is somewhat arbitrary. The width is non critical as long as the extremes of the line width are not used. In the metal width divided by the total width available for a grid is 0.5.

The length of a grid line should be at least wavelength so it can reflect away the field parallel to the grids.

The number of grids on a sheet is determined by the required spacing between the grids. This spacing should be appreciably less than 1 wavelength for appreciable attenuation of the field parallel to the grids as further discussed in the case of a bicone in internal grids below. Note that the actual number of grid lines is much larger than shown in .

Another possibility to reduce the effects of possible resonances and to reduce pattern degradation when the separation between the bicone and grids is one wavelength is to place the grids within the bicone as shown in .

The internal grid bicone antenna of includes a bicone having a height two circumferential edges and a radius measured from the bicone or antenna axis . The antenna includes a top cone a bottom cone a feed angle a feed point 15 degree grid layer 30 degree grid layer and 45 degree grid layer .

An internal grid bicone antenna reduces resonance effects since the grids are more highly coupled to the bicone and are thus less a parasite. If the layers are small enough in circumference operation below the first resonance where the circumference is one wavelength is possible. Also the null frequency where the separation between the bicone axis and innermost grid is one wavelength is pushed to higher frequencies since the separation is reduced. Thus the antenna configuration can be used at higher frequencies. However several problems arise from this configuration.

Placing the grids within the bicone starts to defeat the purpose of the grids which is to rotate the field for an antenna behind the grids. In the internal grid configuration part of the bicone is behind the grids in the rotated field and part of the bicone is ahead of the grids in the field that has not yet been rotated.

The part of the bicone ahead of the grids is the two horizontal edges of the bicone which act as a pair of horizontal grids. Long grids start to allow the field they are supposed to block i.e. the field parallel to the grids to pass at roughly when the spacing between the parallel grids is 1 wavelength. Thus below 1 wavelength the two horizontal edges of the bicone can block horizontal polarization from being received by the grids and bicone. Thus the height of a wide internal grid bicone must be at least 1 wavelength for horizontal response to equal vertical response.

For an idea of the approximate amount of blockage that a layer of grids can achieve to polarization parallel to the grids below is a representative TABLE 2 of the amount of field blockage of grids versus grid separation obtained from NEC from a dipole probe in front of a 2 wavelength by 2 wavelength sheet of grids.

The cases with a small number of grids in Table 2 above may be suspect since only a 2 wavelength by 2 wavelength sheet of grids was used.

Placing the grids within the bicone increases the cut in frequency of the bicone more than what occurs with bicones with external grids. The cut in frequency is defined as the frequency where the VSWR Voltage Standing Wave Ratio about the characteristic impedance Zof the antenna becomes a low flat level. This is because the grids are shunting the bicone at a point closer to the bicone feed point .

Vertical passage of cables past a bicone in either external or internal grids is done by having the cable follow the path of the grids of the outermost grid layer outside of the outermost grid layer. Since grids shunt any field along their direction the antenna impedance wise will usually not see the cable at the frequencies where it is of low impedance being those frequencies above cut in. Below cut in the bicone and similarly sized grids have high impedance and thus coupling to lower impedance longer cables going past the bicone is possible resulting in the cables becoming part of the antenna and radiating usually undesirable patterns. Obviously this is an undesirable property if operation below cut in is important.

Accordingly it is an object of the present invention to provide a vertically polarized dipole or bicone antenna positioned cylindrically within many cylindrical layers of polarizing grids that slowly rotate the incident field to cross 0 degrees i.e. 90 degrees to the horizon to attenuate or minimize the effects of gain nulls from reflections off of the innermost grid layer. Such an antenna is used for detecting both horizontal and vertical polarized signals over a broad bandwidth whereby the response to both polarizations is equal.

Other objects and advantages of the present invention will be apparent in view of the following description drawings and claims.

A possible mechanism for the creation of the cancellation nulls between the innermost layer of grids and the bicone is shown in B. In a bicone with an axis is shown radially wrapped within the innermost layer of grids. An incident wave impinges on what is considered the front of the grid layer which typically is composed of a multitude of grids at a low pitch angle of 15 degrees.

The portion of the wave which is passed by the grid continues to the bicone for reception. The wave continues past the bicone to the opposite side of the grids considered to be the backside of the innermost layer of grids. At the backside a significant part of the wave is reflected back reflected wave with the addition of 180 degrees of phase since the backside direction of the grids is opposite to that of the front of the grids.

A significant component of the backside grids is parallel to the wave that is perpendicular to and passed by the front of the grids which allows reflection of a significant part of the wave. The reflected wave is reflected to the bicone axis . If the path length from the bicone axis to the grids is n 2 wavelengths where n is an integer the total path length from the axis to the grids and back to the axis is 2 times n times 180 degrees or effectively 0 degrees. Thus the reflected wave arrives 180 degrees out of phase at the antenna axis bicone axis with the incident wave which causes cancellation.

As opposed to a dipole measurements have shown that cancellation actually starts at 1 instead of wavelength path lengths for the bicone. This may be explained by the fact that a bicone occupies a large part of the path from the antenna axis to the grids. This occupation of space may effect the electrical path length at wavelength distances.

A solution to the cancellation causing reflections is to disallow reflections. When the incident wave is at the backside of the grids no component of the grids at this location can be parallel to the incident wave. This is only possible if the grids on the front and back line up in the same direction. The only two possibilities for this solution are either the grids are vertical 90 degree grids or the grids are horizontal 0 degree grids.

Zero degree grids is an acceptable solution since they only pass vertical polarization which is the final polarization of the receiving bicone used when a bicone grid configuration is implemented to rotate the 45 degree polarized incident wave to the vertical polarization of the bicone.

The solution is to add a layer of 0 degree grids between the innermost grid layer and the bicone. This layer has the following two properties. First it is compatible with the original configuration since it not the bicone will be the final component to rotate the field to vertical. Second its presence as the innermost grid layer will ensure that no reflections occur inside the layer that may place a cancellation point on the bicone axis.

The above concept was initially investigated with NEC by placing a vertical dipole in the center of a layer of three cylindrical 15 degree grids as shown in .

Referring to a dipole is composed of eleven segments each having end points marked with a tick mark. The center segment of the dipole is the feed point of the whole antenna configuration . The length of the dipole is chosen so that it is wavelength at a frequency of 1 Gigahertz. The dipole is used to probe the fields inside the antenna configuration primarily to determine the behavior of the grids.

A layer of cylindrical polarizing grids is centered about the axis of the dipole . The layer in this example is composed of three grids and . In this example each grid within the layer has a 15 degree pitch angle with the horizon. The grid layer was chosen to represent the innermost layer of grids of an antenna grid configuration. The radius of the 15 degree grid layer is chosen to be 1 wavelength at 1 GHz so that the behavior of the grids as a function of radial size in wavelengths can be directly determined from the frequency.

The height of the grid layer is two wavelengths at 1 GHz a size more than adequate to surround the space around the dipole . A second layer of 0 degree grids is inserted between the 15 degree layer and the dipole. At 1 GHz the vertical separation between grids is wavelength and the horizontal separation between the layers is wavelength.

Additional charts similar to not shown could be presented to represent any grid layers such as 30 45 or any other degree angles. If only two grid layers were used the preferred layers would be 0 degree and 45 degree layers.

The analysis and results of the dipole antenna configuration of are shown in . displays a vertical response curve of gain in decibels versus frequency in Megahertz of a dipole with 15 degree grids. The frequency axis also identifies radius values and circumference values of the 15 degree grids in wavelengths . The response curve includes the effects of the addition of a layer of 0 degree grids between the innermost 15 degree layer and the dipole.

The vertical plots of show little perturbation likely due to the small number of grids in the 15 degree layer and due to the 15 degree grids having only a small vertical component.

A configuration of a preferred embodiment of a bicone antenna according to the principles of the invention is shown in . The antenna configuration is similar to that of except for the addition of a 0 degree grid layer between the innermost 15 degree grid layer and the radius of the bicone antenna .

The bicone has a radius and a height . The bicone similar to the bicone shown in the prior art of is wrapped with an innermost layer of 15 degree grids a layer of 30 degree grids and a layer of 45 degree grids. What is new is that the bicone antenna includes a 0 degree grid layer wrapped between the bicone and the innermost 15 degree grid layer .

The separation between adjacent grid layers and the separation between the innermost grid layer and the extreme edge of the bicone are constant values. The grid layers are arranged radially so that the layers of larger grid angles have corresponding larger radii. In other word a grid layer s pitch angle will increase directly with an increase in radius.

The grid layers are kept separated by placing foam spacers see the cross section of one spacer between adjacent layers or the 0 degree layer and the bicone .

Alternatively the whole antenna configuration could be placed into a cylindrical dielectric box not shown whose top and bottom are mounted respectively to the top and bottom of the bicone and whose top and bottom have slits on their insides in which the top and bottom edges of the grid layers are placed and held in place.

The height of the grid layers is at least that of the bicone. Any cables running vertically past the antenna are run parallel to the grids of the outermost layer of grids and outside of and insulated from the grids. In the area past the grids the cables preferably maintain at least the same radial distance from the bicone axis as in the area where the cables pass the outer most grid layer . If there is more than one cable the cables are placed symmetrically about the circumference of the outer most grid layer .

In a grid layer is made by etching or cutting metal off of a plastic sheet . A typical way to un join the grid layer from its cylinder about the bicone is to cut the layer along a line parallel to and halfway between two of the grids making up the layer. It can be rejoined later with tape. The exception is the 0 degree grid layer where the sheet is cut see line across the grids and rejoined with tape for the sheet and with solder for the grids.

A grid is a metal line that extends from the bottom to the top of the sheet or around the sheet for the 0 degree layer. The angle the grid makes with the horizontal is the grid angle . In and the grid angle is respectively 45 30 15 and 0 .

The metal width of each grid compared to the width of the non gridded area of the sheet is somewhat arbitrary. The width is non critical as long as the extremes of the line width are not used i.e. the metal width divided by total width available for a grid line is greater than 0 and less than 1. In the metal width divided by the total width available for a grid line is 0.5.

The length of a grid line should be at least wavelength so it can reflect away the field parallel to the grids.

The number of grids on a sheet is determined by the required spacing between the grids. This spacing should be appreciably less than 1 wavelength for appreciable attenuation of the field parallel to the grids.

Measurements of actual antenna configurations were made and the results of the VSWR of a bicone of characteristic impedance Zof approximately 50 ohms were made as summarized in . shows the VSWR versus frequency as well as the radius and circumference of the innermost grid layer of a bicone without any grid layers. shows the VSWR versus frequency as well as the radius and circumference of the innermost grid layer of a bicone wrapped inside 15 30 and 45 degree grid layers. shows the VSWR of a bicone wrapped inside 0 15 and 45 degree grid layers. The cut in frequencies Xare shown in each of the drawings.

The VSWR of the bicone itself is low and approximately flat above the cut in frequency X. When a common configuration of added 15 30 and 45 degree grid layers is made spikes in the VSWR are seen near frequencies where the radius of the innermost 15 degree grid layer is approximately 1 1.5 and 2 wavelengths and where the circumference of this layer is one wavelength. When a 0 degree grid layer is added between the bicone and the 15 degree grid layer the spikes only associated with the radius disappear.

Likewise gain versus frequency plots during testing showed that gain dips near 1 1.5 and 2 wavelengths associated with the radius only disappear with the addition of the 0 degree grid layer. Gain dips near the circumferential integer multiples of wave length did not disappear. Thus it may be concluded that the 0 degree grid layer prevents reflections within the inner most layer of grids and possible resultant gain nulls from cancellations caused by reflections. The VSWR and gain spikes or dips associated with the one wavelength circumference of the 15 degree grid layer did not disappear with the addition of the zero degree grids and thus it may be concluded that the zero degree grid layer does not prevent grid circumferential resonances from degrading patterns.

Since the 0 degree grid layers prevent reflections the distance between the innermost layer and the antenna axis is not critical. Increasing this distance will reduce the shunting effect of the grids on the bicone which raises the cut in frequency of the bicone evident by comparing the cut in frequencies Xof and . If this distance is made large enough there is no rise in cut in frequency. This is desirable since it allows a given sized bicone to work at the lowest possible frequency.

Although the preferred embodiments shown herein have been directed to a bicone antenna the same principles are applicable to a dipole antenna. It will be understood that many additional changes in the details materials steps and arrangement of parts which have been herein described and illustrated in order to explain the nature of the invention may be made by those skilled in the art within the principle and scope of the invention as expressed in the appended claims.

The foregoing description of the preferred embodiments of the invention has been presented for purposes of illustration and description only. It is not intended to be exhaustive or to limit the invention to the precise form disclosed obviously many modifications and variations are possible in light of the above teaching. Such modifications and variations that may be apparent to a person skilled in the art are intended to be included within the scope of this invention as defined by the accompanying claims.

