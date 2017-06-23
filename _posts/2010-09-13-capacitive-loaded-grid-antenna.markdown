---

title: Capacitive loaded grid antenna
abstract: A forty five degree polarized antenna having grid layers wrapped around a vertically polarized dipole, or grids wrapped internally or externally around a vertically polarized bicone antenna, and having grid segments separated by capacitors that can attenuate, remove or minimize circumferential resonances that appear due to the presence of the grids and reduce the nulling effects from reflections from the innermost grid layer.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08395559&OS=08395559&RS=08395559
owner: The United States of America as represented by the Secretary of the Navy
number: 08395559
owner_city: Washington
owner_country: US
publication_date: 20100913
---
The invention described herein may be manufactured and used by or for the Government of the United States of America for governmental purposes without the payment of any royalties thereon or therefore.

This application is related to a patent application filed on the same day by the same inventor entitled ZERO DEGREE GRID ANTENNA.

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

Accordingly it is an object of the present invention to attenuate remove or minimize circumferential resonances due to grids wrapped around a vertically polarized dipole antenna or grids wrapped internally or externally around a bicone antenna.

Other objects and advantages of the present invention will be apparent in view of the following description drawings and claims.

The following explanation and compromised solution is presented to overcome the problem of bad patterns and gain nulls occurring at the circumferential resonances of the grids of an antenna where the circumference of the grids is an integer multiple number of wavelengths in size.

Let the low frequency response be only vertical thus at low frequencies the grids are made to disappear electrically i.e. coupling between the grids in a sheet forming a resonant medium and the electrical reflective property of the grids are eliminated at the frequencies of the resonances. Since the severity of the pattern degradation and gain null decreases with higher integer multiples of wavelength circumferences performance may be acceptable if the grids disappeared at the first two resonances or even at just the first resonance. With no polarizing grid effects present the polarization response of the antenna configuration is the response of only the antenna inside of the grids which is usually a vertically polarized dipole or bicone.

Such a configuration described above would have problems with cables passing vertically past the antenna configuration since the cables can no longer hide behind normal grids which shunt the field along their length. Without a shunted path to hide in the cables themselves will shunt the antenna to various degrees causing problems such as the cables becoming part of the antenna and resulting in asymmetrical azimuth patterns.

Let the high frequency response be both horizontal and vertical. At higher frequencies where the less severe effects of the higher order circumferential resonances are tolerable the effect of the polarizing grids is present. Thus for example the 45 degree component of an impinging horizontal or vertical field is rotated by the grids to the vertical polarization of the dipole or bicone inside of the grids.

Grids can be made to disappear electrically i.e. to not appreciably effect a passing electrical field by physically breaking each of the grids in a layer of grids into many pieces or segments as shown in so that each segment of the grid is electrically small having high impedance. shows three of the grids in a layer of grids. Each grid is broken into segments having gaps where no metallic grid is present.

A general rule is that the length of each grid segment should be of maximum size of wavelength. This is derived from the impedance of a monopole. At wavelength length a monopole is at low impedance. At wavelength length a monopole is approaching a high capacitive impedance with decreased length and decreased frequency and is thus starting to look electrically small at which point the monopole starts not effecting any field impinging on the monopole.

The transition between the appearance of broken up disappeared grids to the case of normal continuous grids can be implemented by placing suitably valued capacitors along the length of the grids at the points where breaks are to occur. is a similar configuration to with capacitors replacing the gaps . shows three of the grids in a layer of grids. Each grid is broken into segments separated by capacitors .

At low frequencies capacitors have high impedance and are thus effectively breaking up the grids into individual segments. At higher frequencies the impedance of the capacitors becomes low allowing the grids to appear electrically continuous.

A possible problem with the use of capacitors is that the series capacitive impedance added to the grid lengths will make the grids look shorter in length effecting their RF radio frequency operation. Normally grids need to be long enough at least about wavelength to be reflectors and thus the height of the cylindrical layers of grids has a minimum value.

The concept of capacitively loaded grids was investigated with NEC by placing a vertical dipole in the center of a layer of cylindrical grids as shown in . To minimize the amount of computational time the number of layers of grids and the number of grids in a layer were minimized while still maintaining the effect of circumferential resonances.

Referring to a dipole is composed of eleven segments such as segment with each segment having end points indicated by tick marks. The center segment of the dipole is the feed point of the whole antenna configuration . The length of the dipole is chosen so that it is wavelength at 1 GHz. The dipole is used to probe the fields inside the antenna configuration primarily to determine the behavior of the grids.

One layer of cylindrical polarizing grids is centered about the axis of the dipole . The grid layer is composed of a minimum of three grids . Each grid of the grid layer in this example has a pitch angle of 15 degrees with the horizon and was chosen to represent the innermost layer of grids of a typical antenna grid configuration as previously discussed with respect to . In practice multiple grid layers would be used in a gridded antenna configuration with the grids having various pitch angles .

The radius of the grid layer is chosen to be 1 wavelength at 1 GHz so that the behavior of the grids as a function of size in wavelengths can be directly determined from the frequency. The height of the grid layer is 2 wavelengths at 1 GHz a size more than adequate to surround the space around the dipole .

A grid in this example is made up of sixty segments with nine capacitors inserted into and distributed evenly along the length of each grid. For exemplary purposes only three capacitors are shown in in grid although in practice capacitors are used to bridge grid segments in all grids in every grid layer.

The capacitors can be made by extending the ends of the segments beyond the gap so that the ends of the two segments on opposite sides of a gap overlap to form a capacitor. There are two ways to do this as shown in .

Reference numeral shows the original location of the gap. Adjacent segments such as segments and are placed on opposite sides of a common axial line so that the overlapping areas of both segments forms coplanar capacitor . This would be used for smaller values of capacitance.

Adjacent segments such as segments and are placed on opposite sides of the dielectric sheet to which they are mounted so that the overlapping areas of both segments are separated by the sheet and form a planar capacitor . This would be used for larger capacitance values.

For a given antenna configuration the values of the capacitors are the same. Over a range of tested antenna configurations the values of the capacitors were varied from 20000 to 0.2 picofarads pF by a multiplier of 10. Of course other capacitive values outside of this range can also be used. The following capacitors of TABLE 3 were used during testing. The configuration they were in is identified both in the table and in the drawings by similar reference numerals e.g. ref .

Results of the above testing are summarized where 1 is a graph of true horizontal response curves without offsets of gain db versus frequency MHz of the dipole of 2 is a graph of offset horizontal response curves of gain db versus frequency MHz of the dipole of and is a graph of offset vertical response curves of gain db versus frequency MHz of the dipole of .

As the capacitive loading increases from TRACE to TRACE see TABLE 3 and the two gain nulls shift to higher frequencies and reduce in magnitude until the two resonances are gone with the maximum capacitive loading of the curve as shown in .

Also a cut in frequency exists for the horizontal response and it shifts to higher frequencies with increased loading. All shifting to higher frequencies is an expected and an intended result of loading and opening up the grids by the high capacitor impedances at lower frequencies. The capacitors are effectively shortening the circumference of the grids. The cut in frequency is present because at zero frequency the grids of zero size are invisible and thus no rotation of horizontal polarization to the vertical polarization of the antenna for reception is possible. When the cut in frequency is approximately near or past the frequency where the circumference is 2 wavelengths the gain nulls of 1 and 2 wavelength circumferences disappear and the horizontal polarization response equates to the response of a high pass filter below and near cut in.

According to the above configuration the 1 and 2 wavelength circumferential resonances of the grids and their associated gain nulls are gone. This requires at least some loss of the horizontal response at the resonance frequencies. Below cut in near the second resonance horizontal response cuts out like a high pass filter and thus antenna response is vertical. Above cut in there is little change in horizontal response ignoring other effects such as the null at 610 MHz and thus antenna response is approximately minus 15 db horizontal and approximately 2 db vertical.

The horizontal gain at all frequencies is appreciably less than the vertical gain due to the use of only a layer of 15 degree grids which rotate an incident wave only a small amount in the horizontal direction. There is significant shunting in the horizontal direction by the 15 degree grid layer.

The gain null at 610 MHz is the first wavelength reflection null discussed earlier herein. For the horizontal polarization significant reduction of this null can be seen with the maximum capacitive loading of curve and thus capacitive loading also helps reduce nulls formed from reflections off of the innermost grid layer. This is due again to the capacitors making the grids disappear to some degree even at frequencies above cut in. The gain nulls in the vertical plots are small since the 15 degree grid layer does little shunting in the vertical direction.

The antenna allows removal of grid circumferential resonances by opening up the grids at the resonance frequencies. The tradeoff is reduced horizontal response in the area of these frequencies. The antenna also allows reduction of nulls formed by reflection off of the innermost grid layer.

The above preferred embodiment is an example using only one 15 degree grid layer for demonstrative purposes. In practice all grid layers in an antenna grid configuration such as shown in for example which has equal horizontal and vertical polarization response would require capacitive loading since a normal configuration has multiple layers of grids.

The same principles and procedures of the example above directed to a dipole antenna are applicable to a bicone antenna or other vertically polarized antenna in external or internal grid configurations.

It will be understood that many additional changes in the details materials steps and arrangement of parts which have been herein described and illustrated in order to explain the nature of the invention may be made by those skilled in the art within the principle and scope of the invention as expressed in the appended claims.

The foregoing description of the preferred embodiments of the invention has been presented for purposes of illustration and description only. It is not intended to be exhaustive or to limit the invention to the precise form disclosed and obviously many modifications and variations are possible in light of the above teaching. Such modifications and variations that may be apparent to a person skilled in the art are intended to be included within the scope of this invention as defined by the accompanying claims.

