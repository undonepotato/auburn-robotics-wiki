# Drivetrain Design 101

The drivetrain on your robot will be the **most** important part to do absolutely correctly. Incorrectly building this part will cause durability and overheating issues as well make your auto less consistent and driving harder.

Fear-inducing first paragraph aside, building a decent drivetrain isn't impossible, even for absolutely new people who have never touched the V5 system. With this write-up, my goal is to introduce you to the basics required to make a drive base that you can use for the rest of the year and give you the skills and knowledge required to understand what's needed.

## RPM and Wheel Size (Linear Speed)
First, you need to decide your drivetrain RPM and your wheel size. The most important thing when deciding on the drive wheel size and RPM is going to be what we call **linear speed**, or the ratio of rpm and wheel size that determines the overall "speed" of a drive.

The following table provides some general advice for wheel size and RPM.

|                            | Peak speed | Pushing torque | Acceleration | Overheating risk |
| -------------------------- | ---------- | -------------- | ------------ | ---------------- |
| Bigger wheels / higher RPM | Higher     | Lower          | Lower        | Higher           |
| Smaller wheels / lower RPM | Lower      | Higher         | Higher       | Lower            |

### BIG GPT Formulas

$$
v = \frac{\text{RPM} \cdot \pi D}{60}
$$

RPM = wheel rotations per minute (after gear ratio)
D = wheel diameter

Dividing by 60 converts minutes to seconds. This gives a linear velocity in inches/sec or meters/sec depending on your units for $D$.

If you have gearing:

$$
\text{wheel RPM} = \text{motor RPM} \times \frac{\text{driving gear}}{\text{driven gear}}
$$

	
Then plug that into the speed formula, yielding:

$$
v = \frac{\text{motor RPM} \cdot (\frac{\text{driving}}{\text{driven}}) \cdot \pi D}{60}
$$

This gives the theoretical maximum linear velocity of the robot, assuming no slip.

### VEX Override Recommendations
In the 2026-2027 season Override, you will have 11w less of power on your drive. The usual standard in years past was a 6 motor (66w) drive with 2 extra motors for whatever you want. Since Override is evil, you will be limited to 55w, or 5 motor drive. Due to this limitation, I would recommend a slightly slower drive than is standard in past years. My recommended drive layout for a new person would be **2.75” at 450 rpm**.

If you want more information, I recommend reading [this](https://www.vexforum.com/t/catalogue-of-drive-gearings/109498), but I wouldn't copy the exact gearing of some of these.

![A drivetrain with 2.75 inch wheels at 450 RPM, using 600 RPM blue cartridges geared down 36:48](../assets/images/design/drivetrain-design/im1.png)

I recommend this layout due to it having a low center of gravity, being easy to build and build around, and having a good balance of speed and acceleration.

### Additional Information
!!! note "Needs expansion"
    The Additional Information section is coming soon.

## Drive Dimensions
Now that you've looked at your drive speed and calculated your linear speeds, drive dimensions are the next thing to take a look at. This will mainly be decided by what mechanisms you are making. This year, in Override, I recommend a drive length of at least 30 holes long by 27 holes wide. I have ran this since High Stakes. I recommend a very long drive this year because of the expansion limit, since longer drives tip over less. I usually recommend as small as possible width-wise as you can make, but 27 holes leaves a lot of room for odom pods and game elements. 25-30 hole crossbars are not uncommon. 

![A 35 by 27 hole purple CAD drivetrain](../assets/images/design/drivetrain-design/im2.png)
/// caption
35 hole x 27 hole drive
///

### Drive Gap
**Drive gap:** How wide the drive channels are apart on each side of the drivetrain.

You can choose between a 3 hole gap and a 4 hole gap. A 3 hole gap is always better if you make it right. It saves an inch on the drive and looks nicer, but 4 is fine and it's also easier to build.

![A top view CAD screenshot showing one side of a three-hole gap drivetrain measured by a crossbrace](../assets/images/design/drivetrain-design/im3.png)
/// caption
3 hole gap
///

## Drive Gearing
Drive gearing is going to be determined by the drive speed you choose and the length of drive you want. 

For example, for a 450 RPM drive, all of your wheels have 48-tooth gears while your motors have 36-tooth gears. The rest of the gears will be determined by the length of the drive you want. Gear types include: 

* Wheel gears: These are the gears on your wheels; these all need to be the same size.
* Drive gears: These are the gears on your motors; these also need to be the same size unless your motors aren't running at the same speed. 
* Idler gears: These gears are just on the drive chain; they aren't powered and don't have a motor on them. These are useful for making your drive longer or shorter.
!!! warning "12-tooth Idler Gears"
    Almost any reasonably sized idler gear is fine except 12-tooth. While you *can* run one, it's not recommended because it's so small it will spin at a really high RPM, significantly increasing friction.

### Gearing 5.5w Motors
You will most likely have a four-motor drive with one 5.5w motor on either side in Override. Almost every drive uses 600 RPM blue cartridges, so this raises an issue: 5.5w motors run at only 200 RPM. In order to equalize the speeds, you need to gear up the 200 RPM to 600 RPM by making a "motor stack" and then adding a 36:12 gear ratio to the half motor.

![A CAD screenshot of a gearing setup for a 5.5w motor along with 11w motors](../assets/images/design/drivetrain-design/im4.png)
/// caption
5.5w gearing
///

## Additional information
### Tile Sink
Wheels will tend to "sink" into the foam tiles due to how soft they are. To counteract this, you can add additional wheels, increasing your contact patch and sinking less. This keeps your drive running cooler and chassis slightly further above the ground. 

Now, this doesn't necessarily mean more wheels is always better, because more wheels is additional weight (meaning both overall weight and rotational mass, which is generally considered bad). Also, in *my* personal experience, it reduces your forward traction due to your wheels not digging into the ground as much.

### All Omni Wheels vs. Traction Wheels
Some teams run all omnidirectional wheels and others run omnis with traction wheels. This should honestly be left up to coder/driver preference because both are viable options.

* Omnis: More maneuverable; can cause autos to be less consistent or you to be vulnerable from pushing to the side. I personally prefer this because it drives so much better and the issues can be counteracted by skill.
* Tractions: You will be less vulnerable to pushing sideways, you will have a consistent turning circle, and you will have more consistent autos.

* Turning center: Your turning center is the center point your drive turns around. On omnis this will be determined by your center of gravity (cog) and how many wheels you have. Due to it being affected by weight, grabbing elements can change your turning center. On traction wheels, it's determined by the location of the tractions, so I recommend putting your tractions in the middle.

*By Harrison Elkins*
