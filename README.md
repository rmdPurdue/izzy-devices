# izzy-devices
The `izzy-devices` package provides the `Client` and `Server` classes that are part of the IZZY (Intelligent 
Scenery Simulation Project) as well as enumerations for statuses for both client and server devices.

## Installation
Use the package manager [pip](https://pip.pypa.io/en/stable/) to install `izzy-devices`.
```bash
pip install izzy-devices
```

## Background
"IZZY," or the Intelligent Scenery Simulation Platform, is an ongoing research project in applied robotics and 
control systems for moving scenery in live entertainment. Computerized control of scenery is not new; technologies 
for controlling both simple and complex movement of scenery in multiple axes have been around for decades. Many 
traditional approaches borrow heavily from industrial automation systems, employing programmable logic controllers 
(sometimes with more-user-friendly PC-style front-end interfaces), roller switches, high-powered motors, and cable 
winches. However, because of the very real safety concerns related to hauling scenic units weighing as much as a 
couple of tons across the stage at relatively high velocities, typical automation systems rely heavily on 
highly-choreographed movements and attentive operators to ensure safety. Additionally, traditional approaches often 
require the construction of expensive subfloors and decking systems to provide pathways for winched cables and 
tracks for scenic units to follow.

## IZZY and Mother
The IZZY (Intelligent Scenery Simulation Platform) project software is built around two software objects: a client
and a server. An implementation of IZZY is a ``client``; the offstage control and programming interface ``server`` has
been affectionately dubbed "Mother" (a not-so-subtle nod to *Alien*). A ``client`` stores information about an IZZY
device, including physical dimensions, network information installed sensor packages, and position and movement
information. A ``server`` stores network information and a collection of ``client`` instances--one instance for each
physical IZZY device on the network.

```{note}
When instantiated in software on an IZZY device, a ``server`` instance should not be used to hold a list of
``client`` devices as remote devices should not communicate to each other. A ``server`` instance on an IZZY device
should only be used to store network information about the Mother device.
```

The ``izzy-devices`` package provides the ``Client`` and ``Server`` classes as well as enumerations for statuses for
both ``client`` and ``server`` devices.
