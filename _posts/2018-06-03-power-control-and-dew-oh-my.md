---
title: "Power, Control, and Dew, oh my!"
tags: [ astrophotography, gear, unboxing ]
classes: wide

header:
  teaser: /assets/images/posts/rigrunner.jpg

gallery:
  - image_path: /assets/images/unboxing/eagle2-1.jpg
    title: First assembly, sans risers
  - image_path: /assets/images/unboxing/eagle2-fw-1.jpg
    title: The other side.  As you can see, not yet done with the cable management
  - image_path: /assets/images/unboxing/eagle2-fw-2.jpg
    title: Getting there

---

The last chunk of stuff from the initial bullet list (see ["Pulled the trigger..."](/pulled-the-trigger/)) I want to talk about together.   

- I needed a way to _control_ all of this stuff
- I needed a way to _power_ all of this stuff
- And definitely needed a way to prevent dew from wreaking havoc on everything

<!--more-->

{%
  include figure image_path="/assets/images/posts/rigrunner.jpg"
  alt="Finally!"
  caption="Finally!"
%}

Two words that many astrophotographers think about only as an afterthought are "_cable management_".  In my research phase I learned that I really needed to keep the cables to a minimum.  There are a LOT of cables.

- Power & USB for the camera
- Power & USB for the guide camera
- Power & USB for the filter wheel
- Power & USB for the focuser (which, in my case, is the same as the rotator)
- Power & USB for the mount
- Power for the dew heaters (two- one for the OTA, one for the guidescope)
- Power for the GoPro (long story)

So that's _thirteen cables_, going all over the place.  Every bit the mount moves the balance might shift, or, more likely every loose cable acts like a sail causing teeny tiny vibrations.  Getting them locked down is crucial.

**warning:** plot twist at the end.
{: .notice}


## Initial Overall Plan

The plan was to control the rig with a remote-controlled micro computer, and run a separate dew heater. 

These micro computers, such as the [Intel NUC](https://www.amazon.com/Intel-mini-NUC7i5BNK-Core-version/dp/B01N4EP1N0), tend to come "bare bones".  They don't have drives, RAM, or an operating system.  You can buy bundles but I planned to cobble it together myself (parts list below).  The NUC only has four USB ports, which isn't enough, so I would also need a [quality USB hub](https://www.amazon.com/gp/product/B06ZZ7NDTG).  I was opting for the windows 10 "pro" variety, which has [Remote Desktop](https://www.microsoft.com/en-us/p/microsoft-remote-desktop/9wzdncrfj3ps) built in.  You can get away with other remote software, such as [TightVNC](https://tightvnc.com) or [TeamViewer](https://www.teamviewer.us).  If you use the alternatives mentioned you can get away with the "home" flavor.

<figure style="width: 200px" class="align-left">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/images/posts/rigrunner.jpg" alt="">
  <figcaption>RIGrunner</figcaption>
</figure> 
For power, the plan was to run a RIGrunner 4008 setup with Anderson powerpoles connectors.  In general, you can usually just snip the power side of your cords, replace them with powerpole connectors, and plug them in.  You can also buy various 2.5 pigtails and connectors.  Another great resource for powerpole things is [Powerwerx](https://powerwerx.com).  They have top-notch stuff but their shipping is pretty high.  The RIGrunner has some pretty high amp fuses, so I planned to replace them with much lower amp versions to match the corresponding equipment.  The RIGrunner/powerpole stuff gets pretty pricey.  Don't forget the crimp, extra cord (silicone wire is a good choice), and a 

<figure style="width: 200px" class="align-right">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/images/posts/dew-heater.jpg" alt="">
  <figcaption>DigiFire</figcaption>
</figure> 
I didn't know anything about dew heaters.  I poked around and found that the [Kendrick](http://www.kendrickastro.com) brand was pretty respected.  You need a controller and the actual heaters.  For the controller, I chose the DigiFire 8.  This was overkill because I didn't need four dew heaters, but it works with just two.  I also had to grab a couple dew _straps_.  These just plug into the controller, then wrap around the OTA and guidescope.  The whole purpose here is to keep the optics above the dew point.

Another essential item in cable management is a [label maker](https://www.amazon.com/gp/product/B005J7Y6GS).  I love the Epson one, simply because of the labels themselves- they have a split back which makes them very easy to peel.  I had an older Brother one, I think.  The paper was a real pain to peel.

### NUC Parts List

This list is definitely flexible - you can opt for less RAM, less storage, an i3 rather than i5 chip, or even a different vendor.  As I said, you can also buy a bundle.

- [The NUC itself](https://www.amazon.com/dp/B01N4EP1N0) ($350)
  - (You can get a slim or tall version - the difference is that the slim uses different storage)
- [16GB RAM](https://www.amazon.com/Crucial-PC4-19200-SODIMM-260-Pin-Memory/dp/B01BIWMWVS) ($150)
  - The price of RAM fluctuates quite a bit
- [Disk Storage](https://www.amazon.com/Samsung-960-EVO-Internal-MZ-V6E250BW/dp/B01M20VBU7) ($155)
- [Windows 10 pro usb](https://www.amazon.com/Microsoft-Windows-English-Flash-Drive/dp/B075PZ12B2)($190)
- [USB Hub](https://www.amazon.com/gp/product/B06ZZ7NDTG) ($75)
  
Which comes to $920.  You can hunt around for a deal.

### Powerpole/RIGrunner List

This is not an exaustive list - just enough to get you started

- [Crimp](https://www.amazon.com/TC-1-Ratcheting-Crimper-Powerpole-Connectors/dp/B00F1OUD5W)
- [Power Supply](https://powerwerx.com/ss30dv-desktop-dc-power-supply-powerpole) ($120)
  - There are some similar to this on Amazon, but most of the ones that I found there don't put out the full 30A to each output
- [RIGrunner 4008](https://www.amazon.com/RR-4008-C-RIGRUNNER-Power-Panel-Complete/dp/B00S8JN0MA)($145)
- Various [meters](https://powerwerx.com/digital-meters)
- [Connectors](https://www.amazon.com/Powerpole-Connectors-Assortment-Disconnect-Unassembled/dp/B07CB121LL)

Whatever wiring solution you choose, you can't go wrong with some [braided cord sleeve](https://www.amazon.com/gp/product/B004UHQMYW) -- buy two :wink:, and grab some small black zip ties.

## Stop the presses.  Change Course.  New Plan

No plan survives contact with the enemy.  I actually _bought_ all of this stuff.  I even started prepping to install it (still no mount, yet).  Then, I stumbled upon the [Primaluce Labs Eagle2pro](https://telescopes.net/store/primalucelab-eagle2-pro-wifi-control-unit-for-telescopes-astrophotography.html).  This is an entire system.  And. It. Is. Red.  Yay, more red.  I still needed rings for the Tak OTA, and a couple dovetail bars.  

The Eagle2pro is a NUC inside, with extra stuff.  It has eight USB ports (a mix of USB 2.0 & 3.0), three dew heater jacks, WiFi (which operates in both client and server mode at the same time), AND has 12-volt power distribution _built right in_.  This unit replaces the NUC, RIGrunner, USB hub, and the dew heater.  It even comes with a license for Windows 10 Enterprise.  


{%
  include figure image_path="/assets/images/unboxing/eagle2-fw-2.jpg"
  alt="Imaging Rig Dry Run"
  caption="Imaging Rig Dry Run"
%}

The Eagle2pro case is machined aluminum, and is meant to be _part_ of your imaging train.  In the above picture you see the first assembly of the imaging train.  I had just put together the cable wraps, but hadn't bothered to secure them.  That bunch of cables is power and USB, zip-tied then wrapped with that braided sleeve.  Once my mount came I had to swap things around - balance with this scope was wayyy camera heavy.  I flipped the Eagle2 around, so the power cords were on the back, and slide the whole assembly up.  When I tear down the rig, I slide that all back so it fits in its ginormous pelican case.

{% include gallery id="gallery" caption="Couple more rig pics" %}



