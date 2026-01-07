---
# Date this page was created.
date: 2020-12-22T00:00:00

# Project title.
title: "Intermittent Computing"

# Project summary to display on homepage.
summary: "Exploring how computing systems can be designed to function reliably when power is scarce, intermittent, or harvested from the environment. By treating power loss as a normal operating condition rather than a failure, intermittent computing enables long-lived, battery-free devices that support real-world applications in sensing, interaction, health, and sustainability."

showHero: false
layout: simple
---



<iframe width="100%" height="400" src="https://www.youtube.com/embed/Egte_jpQPsk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Battery-free embedded systems offer a transformative and ecologically sustainable approach for building the next trillion computing devices. Yet, sophisticated applications still seem out of reach. System designers lack the hardware platforms, efficient runtime systems, and focused tools to build capable, data-intensive, reactive, and reliable applications on these devices. 

**This project, generously funded from the [National Science Foundationʻs Faculty Early Career Development Program (CAREER)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=2145584),** seeks to address these shortcomings, to fill the gap in hardware platforms, runtime systems, and tools for practical, dynamic, and capable applications on intermittently powered embedded systems.

## Project Updates, News, and Media Coverage

* **(11/2022)** [_**Protean**_](http://protean.systems/) is presented and published at [ACM SenSys 2022](https://sensys.acm.org/2022/)! _This paper/project is our current progress on the modular, adaptive, accelerated hardware platform proposed in the CAREER project. This represents the first inference capable, modular, heterogeneous platform for intermittent computing and batteryless sensing!_ **See video below...**
<video autoplay loop muted playsinline>
  <source src="../../video/ProteanAnimation v20_1.webm" type="video/webm">
  <source src="my-../../video/ProteanAnimation v20_1.mp4" type="video/mp4">
</video>

* **(07/2021)** _Communications of the ACM article on our work around enabling a batteryless Internet-of-Things via energy harvesting and intermittent computing techniques. ["A Battery-Free Internet of Things"](https://cacm.acm.org/magazines/2021/7/253454-a-battery-free-internet-of-things/abstract)_

* **(10/2020)** _The Wall Street Journal covered our Battery-free Game Boy, a demonstration of intermittent computing._ [_"Battery-Free, Energy-Harvesting Perpetual Machines: The Weird Future of Computing"_](https://www.wsj.com/articles/battery-free-energy-harvesting-perpetual-machines-the-weird-future-of-computing-11601697600?st=xyjz99iomamhwr6&reflink=article_copyURL_share)

## CAREER Project Overview

This project advocates for a future Internet-of-Things where the predicted trillion devices are battery-free, interact seamlessly with a user, sense, and infer large amounts of data in real-time, all to inform countless applications across societally essential domains.
**In this future,** battery-free devices will be easy to program, straightforward to test and deploy, with scalable and capable hardware platforms and systems. Programmers will have the tools to manage the volatility of energy harvesting and power failures and build resilient code for complex and practical applications that combine sensing, machine learning, and communication.  Developers will finally have confidence in a deployed battery-free embedded system.
The project has three guiding insights:

1. **Leverage hardware heterogeneity and weave its benefits across the system stack.** We can overcome the energy-per-computation barrier keeping us from capable applications by using low-power accelerators and FPGAs. However, the intermittent systems support for this is nascent at best.
2. **Embrace energy-aware adaptation, dynamism, and approximation.** Energy harvesting is inherently dynamic; the applications that run off this energy should be scaling operations based on energy available instead of just giving up. We must create scalable and efficient runtime systems that work no matter the energy situation.
3. **Equip developers with a new generation of sophisticated tools.** Building applications that can scale computation across intermittent power failures, heterogeneous hardware, and dynamic energy are challenging. We must develop tools that give insights into energy generation and usage and show the many paths an application can take caused by dynamic energy availability.

![career project tasks overview](../../img/career-overview.jpg)
**Task 1: Hardware and Systems-Support for Heterogeneity.** Accelerators are ubiquitous in high-performance mobile computing. Intermittent computing has not yet integrated specialized and general purpose hardware in a single platform due to the challenges stemming from heterogeneity and mixed memory volatility. This thrust builds a reconfigurable, modular, and deployment-ready hardware platform that embraces multiple computing forms—microcontroller (MCU), convolutional neural network accelerator (CNNA), FPGA, etc. _Recent progress includes devellpment of the [Protean modular hardware platform](http://protean.systems/)_

**Task 2: Language and Runtime Support: Sketchpoints and High-Level Programming.** Checkpoint costs for memory-intensive applications often exceed the energy budget. This makes it challenging to build data and memory-intensive or inference-focused applications with a high level of sophistication (i.e., millions of weights in a CNN versus thousands). The task explores alternative checkpointing methods. This task builds on these approaches to create efficient inference applications and transpilers for high-level programming languages for battery-free devices so that novices can program in scripting languages like Python, JavaScript, and Blocks. _See the  [Battery-free Makecode project](https://ka-moamoa.github.io/makecode-website/) upon which much of this task will be developed._

**Task 3: Developer Tools and Energy Insights.** Heterogeneity causes headaches in understanding where energy is being used and which computing elements are responsible for program tasks. This task builds tools for the simulation and emulation of scalable intermittent computing applications. 


**Integration–Deployment in the Real World.** The research tasks, education, and outreach activities are all integrated via real-world deployment and testing with the SAGE project at Argonne National Lab to deploy smart cities and remote conservation applications, and with with clinicians in various  Medical Schools to deploy mobile health devices (smart face masks, fitness trackers).

![career bpc efforts tasks overview](../../img/career-bpc.jpg)
**Education and Outreach.** The project supports an outreach program that integrates battery-free and energy harvesting devices into a summer programming camp for K-8 Native Hawaiian students at Ke Kula Kaiapuni ʻo Pūʻōhala School, a Hawaiian immersion bi-lingual public school. Prof. Hester is a Native Hawaiian, which along with other Indigenous people are grossly underrepresented in computing. The goal is to help prepare Native Hawaiian/Indigenous students (who are often forgotten) as next-generation computing professionals through interrelated activities designed to develop critical computer science skills, and gain exposure to research. The past two summers the summer camp has happened, with over 100 students participating, and working to help safeguard an ancient fishpond maintained by Native Hawaiians the past millennia. 


## What is Intermittent Computing?

<iframe width="100%" height="400" src="https://www.youtube.com/embed/ErapUArQahM" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

_For a summary and broad perspective of our work that is less technical, please read our feature in the ACM XRDS Student Magazine titled ["Batteries Not Included"](https://dl.acm.org/citation.cfm?id=3351474)_


The future of computing will involve millions, billions, or trillions of tiny devices computing, sensing, and learning all around us.This is a future where devices are small, cheap, and are useful for the entire lifetime of the things they monitor.
This means these devices have to leave their batteries in the lab because batteries wear out, are expensive, they are bulky, and replacing or recycling the number of  batteries needed to power the next billions sensors is not feasible, and is environmentally irresponsible.

Batteryless devices enable applications that have always seemed impractical.
When the batteries are left behind, infrastructure monitoring on a large scale finally becomes feasible.
Sensors can harvest vibrations off buried water pipes to listen for leaks.
River beds can be coated with sensors that watch for bridge deterioration.
Sensors embedded in pavement on roads and highways can communicate with vehicles, and maintenance workers. Small animal tracking, invisible long-lived wearables, and deployment in extreme environments–even space, become possible.
All of these applications represent long term sensing deployments in hard to reach places, some require thousands or tens of thousands of sensors, they all would have trouble working with batteries, and they are all impractical, and maybe even impossible, with our current techniques.

**Intermittent computing**: These tiny devices have energy storage that is eight orders of magnitude smaller than the energy in your phone: the difference in mass between an african elephant and an ant. These are devices with so little energy storage that *energy harvesting* becomes essential, supply voltages — which are normally stable and clean — become intermittent, now without batteries, power failures become common events. This complicates everything from design to testing to deployment.

<!--**This research project focuses on the exploration of languages, architectures, hardware, and tools to enable reliable, sophisticated intermittent computing.** Some of the past work done for this project is listed below.


## Ekho Emulator [ACM SenSys'14]
Ekho is an emulator capable of recording energy harvesting conditions and accurately recreating those conditions in the lab. This makes it possible to conduct realistic and repeatable experiments involving energy harvesting, intermittently powered devices. Ekho is a general-purpose, mobile tool that supports a wide range of harvesting technologies.

## Federated Energy Storage [ACM SenSys'15]
Untethered sensing devices have, for decades, powered all system components (processors, sensors, actuators, etc) from a single shared energy store (battery or capacitor). When designing batteryless sensors that are powered by harvested energy, this traditional approach results in devices that charge slowly and that are more error prone, inflexible, and inefficient than they could be. Federated Energy partitions and prioritizes harvested energy automatically into multiple isolated smaller energy stores (capacitors), which simplifies task scheduling, enables efficient use of components with differing voltage requirements, and produces devices that charge more quickly under identical harvesting conditions than a traditional centralized approach.

## Mayfly Programming Language [ACM SenSys'17]
Mayfly is a language and runtime for timely execution of sensing tasks on tiny, intermittently-powered, energy harvesting sensing devices. Mayfly is a coordination language and runtime built on top of Embedded-C that combines intermittent execution fragments to form coherent sensing schedules: maintaining forward progress, data consistency, data freshness, and data utility across multiple power failures. Mayfly makes the passing of time explicit, binding data to the time it was gathered, and keeping track of data and time through power failures.

## Flicker Prototyping Platform [ACM SenSys'17]
Flicker is a a platform for quickly prototyping batteryless embedded, energy harvesting sensors. Flicker is an extensible, modular, “plug and play” architecture that supports RFID, solar, and kinetic energy harvesting; passive and active wireless communication; and a wide range of sensors through common peripheral and harvester interconnects.

## Intermittent Kernel [ACM SenSys'18]
InK is the first multi-threaded task based language for intermittent computing. With InK prioritized threads can be scheduled and dynamically executed including with timing constraints as in Mayfly.

## Timekeeping Circuit and System [ACM ASPLOS 2020]
We explored dynamic reconfiguration of remanence based timekeepers to facilitate more accurate timing of off periods. This system, BOTOKS, enables new applications like TDMA communication, from the enhanced timekeeping architecture and hardware platform. 

## Automatic Checkpointing with Timekeeping [ACM ASPLOS 2020]
We built an automated checkpoints system called TICS that instruments arbitrary C programs (including those with pointer usage and recursion) for intermittent operation, preserving state and execution progress through power failures. The key observation in TICS is that checkpointing, if done poorly, will results in inconsistency in memory and time. We identified three timing consistency violations that could happen through arbitrary automated checkpointing approaches and design TICS to be aware of those. We also allowed for lightweight annotations (compiler pragmas) to be added to any C program if a programmer want4ed to preserve a notionoftimeorexpirationofavalueinC;forexampleifglobalvariable holdsasensorreadingthatisonlyuseful for a set time, this could be designated and TICS would roll back to the last instantiation point of the variable to get new data and proceed.

-->