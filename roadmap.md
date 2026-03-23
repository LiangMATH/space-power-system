# Space Power System Learning Roadmap

This document outlines a proposed learning journey from basic electrical concepts
to a full understanding of space‑qualified power systems.  The goal of this
curriculum is to build a strong foundation in the relevant disciplines while
gradually introducing the unique challenges of operating in orbit.  Each
module includes theory, modelling and simulation tasks.

## Overview

The electrical power system (EPS) of a spacecraft comprises power generation,
storage and distribution【76182107308584†L158-L171】.  Learning about these
subsystems in isolation before integrating them together mirrors how actual
spacecraft are designed and tested.  Your progress will span several
months; adapt the pacing to fit your schedule and academic commitments.  The
modules can be studied sequentially or overlapped if you prefer a more
integrated approach.

| Phase | Duration (weeks) | Focus |
|------|-----------------|------|
| **Foundation** | 1–2 | Review of basic circuit analysis, power calculations, three‑phase systems, control theory, and an introduction to MATLAB/Simulink. |
| **Solar Module** | 2–3 | In‑depth study of photovoltaic physics (I–V curves, diode models), comparison of terrestrial vs. space solar cells, maximum power point tracking (MPPT) algorithms and modelling of solar arrays.  This module also introduces semiconductor physics and lays the theoretical groundwork for later modules. |
| **Power Electronics** | 2–3 | Study DC‑DC conversion (buck, boost and buck‑boost), PWM control and switching losses.  Build and simulate converters using SPICE or Simulink, and explore gallium‑nitride (GaN) devices as emerging technologies【76182107308584†L2060-L2074】. |
| **Battery/Storage** | 2–3 | Explore Li‑ion and Li‑Po cell chemistry, energy density, charge/discharge behaviour, and thermal considerations.  Note that Li‑ion cells deliver ~3.6 V per cell with specific energies often >150 Wh kg⁻¹【76182107308584†L1612-L1624】.  Perform simple cycle‑life simulations. |
| **PMAD (Power Management and Distribution)** | 2–3 | Learn how spacecraft distribute and regulate power.  Topics include bus architectures, load sharing, protection, redundant design and efficiency trade‑offs.  Review commercial vs. custom PMAD designs and GaN advantages【76182107308584†L2016-L2081】. |
| **Load Modelling** | 1–2 | Model constant‑power loads (CPLs) and dynamic loads such as avionics or onboard computing.  Investigate how load characteristics influence bus stability and converter design. |
| **System Integration** | 2–3 | Assemble a simplified EPS by connecting your solar array, converter, battery and loads.  Perform power‑flow and stability analysis.  Iterate designs based on space‑specific constraints like mass, volume and radiation. |

## Detailed Steps

### 1. Foundation

* Refresh basic circuit theory: Ohm’s law, Kirchhoff’s laws and Thevenin/Norton
  equivalents.  Ensure you can compute real and reactive power in AC and DC
  systems.
* Review basic control concepts (open/closed loop, PID controllers) and their
  implementation in power electronics.
* Set up MATLAB/Simulink (or a comparable tool) and practise building simple
  circuits.  Many later simulations will rely on this platform.

### 2. Solar Module

* Study semiconductor physics and the PN junction to understand how light
  generates a current in a solar cell.  Build the single‑diode and
  double‑diode models to reproduce the I–V characteristic.
* Compare terrestrial silicon cells (~20 % efficient) with space‑grade
  multi‑junction cells based on III–V semiconductors such as GaAs.  The
  state‑of‑the‑art for space includes 3‑5 junction cells delivering >32 %
  efficiency【76182107308584†L356-L363】.  Despite higher cost, these cells are
  chosen for their power‑to‑mass advantage【76182107308584†L360-L367】.
* Examine degradation mechanisms: radiation damage, cover‑glass darkening,
  contamination and mechanical failures【76182107308584†L372-L375】.
* Review maximum power point tracking (MPPT) techniques such as perturb‑and‑
  observe and incremental conductance.  Simulate a PV module with an MPPT
  controller feeding a DC‑DC converter.
* Understand how continuous sunlight in many orbital regimes reduces the need
  for oversized arrays, yet eclipse periods still require energy storage.
* **Theoretical foundation**: Include explanations of DC‑DC converters and
  battery basics here.  For example, a DC‑to‑DC converter is an electronic
  circuit that converts a source of direct current from one voltage level to
  another【28655642480916†L178-L181】.  Li‑ion cells deliver about 3.6 V with
  specific energies above 150 Wh kg⁻¹ and are relatively tolerant of
  radiation【76182107308584†L1612-L1619】.

### 3. Power Electronics

* Explore step‑down (buck), step‑up (boost) and buck‑boost topologies.  Derive
  their voltage transfer functions and analyse inductor, capacitor and switch
  selection.
* Implement pulse‑width modulation (PWM) control and closed‑loop voltage
  regulation.  Investigate how switching frequency affects efficiency and
  component size.  Consider GaN devices for higher switching speeds and
  improved power density【76182107308584†L2060-L2074】.
* Simulate converters under varying input (solar) and output (load) conditions.

### 4. Battery/Storage

* Understand electrochemistry of Li‑ion and Li‑Po cells, including the
  cathode/anode materials and electrolyte.  Note typical nominal voltage
  (~3.6 V) and specific energy values【76182107308584†L1612-L1624】.
* Study how radiation minimally affects capacity, but high doses can still
  produce measurable degradation【76182107308584†L1616-L1621】.
* Learn about charge/discharge cycles, depth of discharge and temperature
  effects on ageing【76182107308584†L1621-L1631】.  Implement a simple battery
  model and simulate cycles.
* Examine current spacecraft battery form factors (18650, 21700, 4680) and
  their specific energies【76182107308584†L1642-L1687】.

### 5. PMAD

* Investigate bus architectures (regulated vs. unregulated) and how to manage
  multiple voltage domains.
* Study the selection of PMAD units.  Consider conversion efficiency,
  input/output range, output power and Size–Weight–Power (SWaP) metrics【76182107308584†L2025-L2030】.
* Weigh the pros and cons of commercial off‑the‑shelf (COTS) PMAD systems
  versus custom designs.  COTS devices may include unnecessary features that
  increase mass or omit critical functions like MPPT and redundancy【76182107308584†L2031-L2053】.
* Examine emerging GaN‑based PMAD technologies for higher switching frequency
  and improved efficiency, while acknowledging their control complexity and
  limited flight heritage【76182107308584†L2060-L2081】.

### 6. Load Modelling

* Define different types of loads: resistive, constant‑current and
  constant‑power loads.  Understand that constant‑power behaviour can
  destabilise DC buses due to the negative impedance effect.  Explore
  stabilisation methods such as virtual impedance or bus regulation.
* Model an AI compute payload or communication subsystem as a dynamic load.
  Vary its power demand to observe how the EPS responds.

### 7. System Integration

* Combine your solar array, DC‑DC converter, battery and load models into a
  complete EPS.  Implement bus regulation and MPPT control.
* Perform power‑flow analysis during sunlit and eclipse periods.  Examine how
  the battery charges and discharges, and assess system stability under
  varying loads.
* Iterate on your design to improve specific power and reduce mass, drawing on
  insights from the earlier modules.  Consider space constraints such as
  radiation hardness and thermal management.

## Usage of the Repository

* **01_solar/** – Notes on photovoltaic theory, models and simulations.  Include
  fundamentals of semiconductors and summaries of key papers.  Store
  Simulink models of PV modules and MPPT controllers.
* **02_power_electronics/** – Theory and models for DC‑DC conversion.  Save
  derivations, circuit schematics and simulation files.
* **03_battery/** – Notes and models on Li‑ion and alternative storage
  technologies, including testing data and ageing curves.
* **04_pmad/** – Articles, datasheets and design notes on bus architectures and
  power management units.
* **05_load/** – Descriptions and models of typical satellite loads (computers,
  radios, instruments).  Include studies on constant‑power load stability.
* **06_system/** – Integration experiments and full system models.  Document
  your assumptions and results.
* **papers/** – Downloaded references and research papers.  Keep track of
  citations here.
* **references/** – Store external links, bibliographies and any external
  spreadsheets.

Following this roadmap and populating the repository with your notes,
simulations and references will give you a solid foundation in space power
systems and prepare you for more advanced research or practical projects.
