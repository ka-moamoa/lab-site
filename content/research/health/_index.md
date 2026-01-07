---
title: "Health: Wearable, Implantable, Accessible"
summary: "We design, develop, and deploy wearable and implantable computational devices that reduce the effect of structural, access, societal, monetary, or mental barriers to receiving healthcare treatment, across cancer, nutrition and diabetes, and respiratory care."
cardView: false
layout: "simple"

cascade:
  showDate: false
  showAuthor: false
  invertPagination: true
  groupByYear: false
---

## Mobile Health

Our lab has been active in the mobile health research community since 2012 with the [Amulet Project](https://amulet-project.org/about/) (of which a [post-mortem summary can be found here](https://www.cs.dartmouth.edu/~kotz/research/project/amulet/index.html)  written by [Prof. David Kotz at Dartmouth](https://www.cs.dartmouth.edu/~dfk/)). This has since turned into collaboration with Prof. [Nabil Alshurafa](https://www.feinberg.northwestern.edu/faculty-profiles/az/profile.html?xid=33330) in the Department of Preventive Medicine at Northwestern, and Prof Hester's courtesy appointment in that department. Our goal is to reduce the effect of structural, societal, monetary, or mental barriers to receiving healthcare treatment. This has come in the form of lowering the burden of long term monitoring and interventions through novel wearable design, building tools for clinical researchers to conduct better clinical trials with strong groundtruth and high adherence, and bootstrapping clinical processes. 

Early work in this space was in the design and development of the Amulet platform and software toolchain, published in SenSys’16, USENIX ATC’18, and [MobiCom’19](https://josiahhester.com/cv/files/mobicom19amulet.pdf) as full papers. Amulet was the first multi-tenant and ultra low power smart watch for mobile health, allowing for a nine month battery lifetime. 


### Eating Detection with Wearables

![necksense](../../img/eating.jpeg)
Recently with Nabil Alshurafa and the [HABITS Lab](http://www.nalshurafa.com/) we have been exploring eating behaviors.
This was published in UbiComp'20 as ["NeckSense: A Multi-Sensor Necklace for Detecting Eating Activities in Free-Living Conditions."](https://www.thehabitslab.com/assets/papers/67.pdf).
NeckSense is a novel neck-worn device with multiple embedded sensors inferring eating behavior from contactless sensors, targeting the obesity problem and tested with people with obesity, validated in real-world setting using wearable camera for 270 hrs in-the-wild, with data and code provided to the community. [More information can be found here.](http://necksense.info/)
Currently we are designing new wearable devices that can non-invasively monitor eating, sleeping, smoking and mental health indicators via egocentric and low power thermal imaging and other sensing modalities.  

### Wearable Visual Systems

{{< youtubeLite id="SdmGOnwIP0I" label="Blowfish-tools demo" >}}

Extending from this we have explored how wearable visual systems can be used to understand behavior, establish ground truth, or serve as interactive devices. Our first foray into this space was investigating how privacy norms prevent the gathering of strong ground truth (for example with video), reducing adherence in medical trials that use wearables, as described in our [IMWUT/UbiComp’19 paper, "To Mask or Not to Mask? Balancing Privacy with Visual Confirmation Utility in Activity-Oriented Wearable Cameras"](https://www.rawanalharbi.com/publication/alharbi-2019-mask/alharbi-2019-mask.pdf). 

We have continued this work with an IEEE Percom 2022 paper titled "ActiSight: Wearer Foreground Extraction using a Practical RGB-Thermal Wearable" which explores how low resolution thermal imaging can be used as an attentino mechanism in wearable, egocentric video collection, to greatly reduce the amount of processing power and time required to gather useful inferences from video streams. We also explored how thermal alone is a powerful mechanism to infer gestures and human behaviors, in an ISWC'21 paper titled ["HeatSight: Wearable Low-power Omni Thermal Sensing."](https://dl.acm.org/doi/fullHtml/10.1145/3460421.3478811)

### Battery-free Body Area Intelligence

With support from the NSF [(CNS-2107400)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=2107400), together with collaborators at UMass Amherst, we have been exploring body area networks for health monitoring. An exciting new paradigm for wearable health sensors is one where sensors and batteries need not be integrated within the same device. This project seeks to realize this vision by utilizing human tissue as a medium for transferring power and data between different device pairs. The project objective is to develop hardware and software mechanisms that allow heterogeneous networks of sensors that are largely battery-free. The key working principle is the design of a system where energy transmitters that include batteries, provide power to relatively many battery-free sensors while simultaneously serving as an endpoint for data collection from the sensors. The project has three thrusts: 1) quantifying the performance and safety issues of the use of human tissue as a propagation medium for power and communications; 2) the design of hardware and software primitives needed to facilitate energy sharing between networks of battery-free devices; 3) the operating system, run-time support, and tools needed to coordinate devices that in turn enable higher level health applications.


##  Low-cost, Batteryless Smart Personal Protective Equipment (PPE) Tackling the COVID-19 Pandemic

![Smart PPE](../../img/smartppe-overview.jpg)

We have been funded by the NSF (via the RAPID mechanism [CNS-2032408](https://www.nsf.gov/awardsearch/showAward?AWD_ID=2032408)) to embed personal protective equipment (PPE) like masks, and face shields, with ultra low cost and maintenance free sensing devices to help battle the COVID-19 pandemic. These smart PPE devices will enable healthcare workers, caregivers, and the general population to stay safe and  informed.

# Implantables

{{< article link="/research/health/cancer/" showSummary=true >}}
<br>
{{< article link="/research/health/circadian/" showSummary=true >}}
