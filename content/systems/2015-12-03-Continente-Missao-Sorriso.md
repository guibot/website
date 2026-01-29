+++
title = "Continente Missao Sorriso"
date = 2015-12-03
status = "archived"
tags = ["artica", "interactive", "physicalcomputing", "work"]
featured = true
cover = "./2015-12-03-Continente-Missao-Sorriso-images/missao_sorriso-1.jpg"
showCover = false
+++

{{< youtube gKpxnx61JYE >}}

We had to create an interactive installation for a road-show campaign that would be travelling through several schools across Portugal to promote [Missão Sorriso](https://missao.continente.pt/). The project involved developing a **_Band Hero_** clone that could play 3 licensed tracks from [Orelha Negra](https://soundcloud.com/orelha-negra). To bring more impact to the experience we used real instruments as input devices instead of the usual plastic controllers.

# **Hardware**

The hardware had to be procured and modified to allow for non-musicians to still be able to play the game. We had 4 different instruments.

**Drum Set**

We purchased a real drum set and stripped it down to a few minimum elements: bass drum, snare drum, tom and hi-hat. This was required for the portability of the drum set during the roadshow.

Next, we coupled to it an Arduino with several piezo sensors. The piezos were placed inside each drum element which was muffled with a plastic material to prevent sound noise and physical damage to the piezos.

The Arduino would register the values and send a WebSocket message to a Node server.

**Bass Guitar**

The bass guitar was purchased as one of those build at home kits, that saved some work of breaking a new guitar apart.

We actually had 2 bass guitar prototypes, one using frequency analysis of the picks, and the other using actual sensors. The second prototype proved to be both more robust and easy to learn to use, and that’s the one that was used in the end.

The pick was taken apart from a plastic controller of guitar hero. The bass guitar carved up for more space to place it inside along with an Arduino and connections to the triggers placed on the handle bar.

Similar to the drum set, the Arduino would register the values and send a websockets message by ethernet network to a node.js server.

**Keyboard**

The keyboard was a standard midi keyboard, sending midi values that are converted into websockets messages by our node.js server working as a proxy.

**Sampler**

The sampler was a standard MPC. We opened it up to replace the lights with matching colors to the game and remove any buttons without usage. Similar to the keyboard, the MPC sent midi messages that were converted into websockets messages by our node.js server working as a proxy.

# **Software**

In the software department the whole application is actually a webpage with a localhost server.

- The design is hardcoded to FullHD resolution.
    
- Web Audio API is used to trigger sounds.
    
- WebGL (via [pixi.js](http://www.pixijs.com/)) is used to give 3d acceleration to the interactive elements.
    

To sync the tracks we developed an internal editor to add/move/edit/delete track nodes. It was made to easy scroll back and forth with the mousewheel to check for music synchronism. And it included functionality to import and export as json.

An additional requirement was made to input high-scores from each session and export them to a local file, for the client to analyse after the roadshow was done.

As previously mentioned the [sourcecode is open source](https://bitbucket.org/artica/continente-music-experience) available under MIT license. Feel free to fork it to add support for frets on fire assets, other controllers, play music directly from youtube / soundcloud, etc.

# **Installation**

We delivered the project as a turn key solution. Fully pre-tested and ready to operate by the roadshow crew alone. They were touring several schools during 2 months, we wouldn’t be able to be present during all of the sessions but were available to provide support when required.

All the hardware was ready to plug and play. We provided a technical ryder for the cables, labelled all inputs and ducttapped the unused ports. We also provided an operations and troubleshooting manual and provided replacement parts for the more sensitive components that might not resist the hard life on the road.

We were present on the initial setup sessions to make sure all things worked smoothly. We caught some early malfunctions and had to repair them but overall we were impressed on how well the system held up on the road.  
  
**Customer:** Continente Missão Sorriso  
  
**Agency:** GCI  
  
**Software:** Filipe Cruz, André Almeida  
  
**Instruments Hacking & Electronics:** Guilherme Martins
