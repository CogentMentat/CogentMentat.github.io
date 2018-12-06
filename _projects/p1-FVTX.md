---
layout: project
projectnum: 1
title: "FVTX: the Forward Vertex Detector for the PHENIX Experiment at BNL"
excerpt: "Hardware and software work on the FVTX detector, currently seeing
action at the Relatavistic Heavy Ion Collider at Brookhaven National
Laboratory."
thumbnail: /assets/img/p1-FVTX/fvtx_thumb.jpg
comments: false
---

The FVTX detector is part of a silicon detector upgrade to the [PHENIX
experiment](http://www.bnl.gov/rhic/PHENIX.asp) at Brookhaven National
Laboratory.

The [PHENIX collaboration](http://www.phenix.bnl.gov/) performs basic research
with high energy collisions of heavy ions and protons.  PHENIX seeks to
understand the quark gluon plasma, a state of matter thought to exist shortly
after the big bang.  PHENIX also explores quantum chromodynamics and the
quantum spin properties of the proton.  The experiment is housed in the
Relativistic Heavy Ion Collider, the only spin-polarized proton-proton
collider in the world.

My contributions to FVTX spanned elementary particle physics analysis,
FPGA-based electronics, modeling detector geometry in code, and testing
silicon detectors. Below are highlights of my work.

## Software

* Collaborator: Aaron Key, Graduate Student, UNM

The basic hardware unit of FVTX is called a wedge.  Each wedge is comprised of
a silicon strip detector and a "high-density interconnect," a multi-layered
flex circuit board providing power and readout capabilities. Connecting the
analog output of the silicon to the readout on the HDI are 26 custom readout
chips, each of which have multiple, adjustable parameters controlling their
operation.  The GUI we designed communicates with the readout chips from an
individual basis up to a detector-wide basis, allowing detailed adjustment of
data acquisition. The GUI was written in Python using the Tkinter module.

{% capture images %}
    /assets/img/p1-FVTX/top-level_ex_fullsize.jpg
    /assets/img/p1-FVTX/wedge-level_ex_fullsize.jpg
    /assets/img/p1-FVTX/chip-level_ex_fullsize.jpg
{% endcapture %}
{% include gallery images=images caption="Three elements of a GUI visual
hierarchy: top-level, wedge-level, and chip-level control panels (click
thumbnail to enlarge)." cols=3 %}

* Features:
  - Integration with FPGA-based electronics.
  - Live propagation of visual cues to all levels of the GUI indicating
    changes not written to the FVTX hardware.

## Hardware

* Supervisor: Sergey Butsyk, Postdoctoral Fellow, UNM
* Collaborator: Aaron Key, Graduate Student, UNM

The final FVTX detector will utilize a complex chain of electronics,
processing data and providing two-way communication and control.  Building an
electronics test stand, we created and debugged the firmware necessary for
interfacing with the GUI discussed above.  We also finalized the
communication chain of the built-in calibration capabilities of the FVTX
detector.

<figure>
	<img src="/assets/img/p1-FVTX/oldroc.jpg">
    <figcaption><center>Testing one piece of data acquisition electronics that
    surrounds the beam line.</center></figcaption>
</figure>

## Silicon Detector Testing

Using LabVIEW and a probe station, we verified quality metrics provided by
Hamamatsu Photonics for each silicon detector ordered.

<figure>
	<img src="/assets/img/p1-FVTX/silicon_testing.jpg">
    <figcaption><center>.</center></figcaption>
</figure>

## Detector Geometry Modeling

* Collaborator: Hubert van Hecke, Staff Physicist, Los Alamos National Laboratory

Part of the FVTX development process necessitated simple geometric computer
modeling of each piece of the final detector.  Using GEANT 3, a toolkit for
FORTRAN, we created a simplified detector model in code.  GEANT models
integrate with particle collision modeling software, allowing studies of
detector materials' effects the collection of particle physics data.  The
model mirrors the final, surveyed geometry of FVTX, accounting for minute
positioning changes not present in engineering specifications.

<figure>
	<img src="/assets/img/p1-FVTX/GEANT_cages_spacial.jpg">
    <figcaption><center>Wireframe representation of parts of the FVTX detector
    simulation.</center></figcaption>
</figure>
