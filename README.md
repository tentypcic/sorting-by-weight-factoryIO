<h2 align="center">
Sorting by weight
</h2>

<p align="center">
  <img src="/Documentation/images/work-line.gif">
</p>
<p align="center">
	Project code in TIA Portal and model in FacotryIO.
	<br />
	<a href="https://plc-programme-viewer.000webhostapp.com/sbw">View demo</a>
	·
	<a href="https://github.com/tentypcic/sorting-by-weight-factoryIO/issues">Report Bug</a>
</p>

## Table of Contents
- [Built With](#built-with)
- [About The Project](#about-the-project)
  - [Features](#features)
  - [Sorting line](#sorting-line)
  - [Project Tree](#project-tree)
  - [Algorithm](#algorithm)
  - [HMI panel](#hmi-panel)
  - [Test Suite](#test-suite)
  - [Filter Weight](#filter-weight)
- [How To Use](#how-to-use)
  - [Factory IO](#factory-io)
  - [TIA Portal](#tia-portal)
  - [Version Controle Interface](#version-controle-interface)
  - [SIMATIC Automation Compare Tool](#simatic-automation-compare-tool)
- [License](#license)

## Built With
This project was bult using these technologies:
- [Factory I/O](https://factoryio.com/)
 - [ Siemens TIA Portal V17](https://support.industry.siemens.com/cs/document/109784440/simatic-step-7-incl-safety-s7-plcsim-and-wincc-v17-trial-download?dti=0&lc=en-PL) 
 - [SIMATIC S7-PLCSIM](https://support.industry.siemens.com/cs/document/109795016/simatic-s7-plcsim-advanced-v4-0-trial-download?dti=0&lc=en-PL)
 - [Test Suite Advance](https://support.industry.siemens.com/cs/document/109793099/tia-portal-test-suite-advanced-v17-trial-download?dti=0&lc=en-AT)
 - [SIMATIC Automation Compare Tool](https://support.industry.siemens.com/cs/document/109797235/simatic-automation-compare-tool-?dti=0&lc=en-DO) 
 - [GIT](https://git-scm.com/)
 - [Grafcet-Studio](https://www.mhj-tools.com/?page=grafcet-studio)

## About The Project

This is a PLC programme for sorting by weight.

Code in TIA Portal V17. The sorting line has been modelled in Factory IO 3D simulation software.

### Features

 - [x] Two operating modes - automatic and manual
 - [x] Three error scenarios
 - [x] Filter Weight - moving average
 - [x] HMI panel
 - [x] Sound and light signalling
 - [x] Statistics
 - [x] Unit tests

### Sorting line

<p align="center">
  <img src="/Documentation/images/line.png">
</p>

The line consists of:
 - :four: belt conveyors (C1, C2, C3, C4),
 - a sorting conveyor (S),
 - a weighing conveyor (W),
 - an emitter (E) - wchich delevers the parcels to the line,
 - :three: receivers (R1, R2, R3) - used to receive parcels from the line,
 - :nine: optical sensors including:
	 - :four: retro-reflective sensors (D1, D7, D8, D9),
	 - :five: diffuse-reflectiv (D2, D3, D4, D5, D6),
 - a control panel ("P").

### Project Tree
<p align="center">
  <img src="/Documentation/images/tree.png">
</p>

The programme is structured in six layers. The structure of the programme is similat to the concepts of oop. Each layer is responsible for one main task.

### Algorithm

Some functions use a sequential algorithm. Such algorithms have been graphically represented in Grafcet-Studio and translated into LAD and SLC languages.

### HMI panel

<p align="center">
  <img src="/Documentation/images/hmi-panel.gif">
</p>

The HMI displays basic information about the sorting line. The status of the sensors, the status of the conveyors, informs about the operating modes and erros.

### Test Suite

<p align="center">
  <img src="/Documentation/images/test.gif">
</p>

The programme has been tested using the Test Suite add-on, which allows unit test to be written.

### Filter Weight

<p align="center">
  <img src="/Documentation/images/trace.gif">
</p>

The programme uses a moving average weighting filter. After many trials, the correct parameters such as cyclic interruption time and sampling rate were selected experimentally. By using the Trace function in the TIA it was possible to compare the signals.

## How To Use

To clone and run this application, you'll need FactoryIO and TIA Portal (v16 and later) installed in your computer. 

### Factory IO

Download the scene for factory io and move it to the default folder in the `C:\Users\username\Documents\Factory IO\My Scenes`

### TIA Portal

On TIA v17 and later: 
Download an archaised version of the programme and open in TIA

### Version Controle Interface

On TIA v16 and later:
 Download template of the programme and open in TIA
 
    # Clone this repository into your worksapce
    
    $ git clone https://github.com/tentypcic/sorting-by-weight-factoryIO
    
    # Use the Version Control Interface (VCI) in TIA to synchronise programme

<p align="center">
  <img src="https://www.dmcinfo.com/Portals/0/Siemens-VCI-image-2.png">
</p>

### SIMATIC Automation Compare Tool

You can view the functions and blocks in the .xml extension directly using the SIMATIC Automation Compare Tool software.

<p align="center">
  <img src="/Documentation/images/act.png">
</p>

## License

Distributed under the MIT License. See `LICENSE` for more information.
