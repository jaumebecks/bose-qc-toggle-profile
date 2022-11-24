<a name="readme-top"></a>

<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]


<!-- PROJECT LOGO -->
<br />
<p align="center">
  <h3 align="center">Bose Quietcomfort profile switcher</h3>
  <h4 align="center"><i>HFP / A2DP Sink</i></h4>

  <p align="center">
    Using Bash
    <br />
    <a href="https://github.com/jaumebecks/bose-qc-toggle-profile.git/issues">Report Bug</a>
    ·
    <a href="https://github.com/jaumebecks/bose-qc-toggle-profile.git/issues">Request Feature</a>
  </p>
</p>

<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary><h2 style="display: inline-block">Table of Contents</h2></summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
        <li><a href="#usage">Usage</a></li>
      </ul>
    </li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgements">Acknowledgements</a></li>
  </ol>
</details>

<!-- ABOUT THE PROJECT -->

## About The Project

This project's purpose is to help users with BOSE Quietcomfort headphones switch
its card profile mode in a very easy way.

### Built With

- [Bash](https://www.gnu.org/software/bash/)

<!-- GETTING STARTED -->

## Getting Started

### Prerequisites

- [bash4](https://tldp.org/LDP/abs/html/bashver4.html)

And to configure some envvars

```sh
CARD_PROFILE # Currently used card profile
```

#### How to find card profile

To check how many sound cards do you have, run

```sh
pactl list cards
```

You should see a card relative to your BOSE QuietComfort headphones

```
Card #1
	Name: bluez_card.XX_ZZ_YY_JJ_KK_QQ
	Driver: module-bluez5-device.c
	Owner Module: X
	Properties:
		device.description = "Headphones name"
		device.string = "XX:ZZ:YY:JJ:KK:QQ"
		device.api = "bluez"
		device.class = "sound"
		device.bus = "bluetooth"
		device.form_factor = "headphone"
		bluez.path = "/org/bluez/hci0/dev_XX_ZZ_YY_JJ_KK_QQ"
		bluez.class = "0xXXYYZZ"
		bluez.alias = "Headphones name"
		device.icon_name = "audio-headphones-bluetooth"
		bluetooth.battery = "100%"
		bluetooth.codec = "sbc"
	Profiles:
		a2dp_sink: High Fidelity Playback (A2DP Sink) (sinks: 1, sources: 0, priority: 40, available: yes)
		handsfree_head_unit: Handsfree Head Unit (HFP) (sinks: 1, sources: 1, priority: 30, available: yes)
		off: Off (sinks: 0, sources: 0, priority: 0, available: yes)
	Active Profile: a2dp_sink
	Ports:
		headphone-output: Headphone (type: Headphones, priority: 0, latency offset: 0 usec, availability unknown)
			Part of profile(s): a2dp_sink, handsfree_head_unit
		headphone-input: Bluetooth Input (type: Bluetooth, priority: 0, latency offset: 0 usec, availability unknown)
			Part of profile(s): handsfree_head_unit
```

> Then CARD_PROFILE should be set to bluez_card.XX_ZZ_YY_JJ_KK_QQ in this example


### Installation

To get a local copy up and running follow these simple steps.

1. Clone the repo

  ```sh
  git clone https://github.com/jaumebecks/bose-qc-toggle-profile.git
  ```

2. Go into project root

  ```sh
  cd bose-qc-toggle-profile
  ```

### Usage

To run the script in local

  ```sh
  CARD_PROFILE=<YOUR-CARD-PROFILE> bash profile-toggle
  ```

> Follow the steps mentioned in [How to find card profile](#how-to-find-card-profile) for setting CARD_PROFILE

It's recommended to create a Keyboard shortcut to quickly switch between profiles.
In Ubuntu, follow these steps

1. Open `Settings > Keyboard`

2. Under `Keyboard Shorcuts > View and Customize Shorcuts`, click `Custom shortcuts`

3. Click `+` sign

    a. Add a name for it

    b. Put the following command
    ```sh
    sh -c "CARD_PROFILE=<YOUR-CARD-PROFILE> /bin/bash /<PATH-TO-PROJECT>/bose-toggle-profile/profile-toggle"
    ```
    > Remember to change <YOUR-CARD-PROFILE> env var and <PATH-TO-PROJECT> to your installation path (must be absolute)

    c. Put your preffered key binding


<!-- CONTACT -->

## Contact

Jaume Jiménez - [@jaumebecks](https://twitter.com/jaumebecks)

Project Link: [https://github.com/jaumebecks/bose-qc-toggle-profile.git](https://github.com/jaumebecks/bose-qc-toggle-profile.git)

[![LinkedIn][linkedin-shield]][linkedin-url]

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/jaumebecks/bose-qc-toggle-profile.svg?style=for-the-badge
[contributors-url]: https://github.com/jaumebecks/bose-qc-toggle-profile/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/jaumebecks/bose-qc-toggle-profile?style=for-the-badge
[forks-url]: https://github.com/jaumebecks/bose-qc-toggle-profile/network/members
[stars-shield]: https://img.shields.io/github/stars/jaumebecks/bose-qc-toggle-profile?style=for-the-badge
[stars-url]: https://github.com/jaumebecks/bose-qc-toggle-profile/stargazers
[issues-shield]: https://img.shields.io/github/issues/jaumebecks/bose-qc-toggle-profile?style=for-the-badge
[issues-url]: https://github.com/jaumebecks/bose-qc-toggle-profile/issues
[license-shield]: https://img.shields.io/github/license/jaumebecks/bose-qc-toggle-profile?style=for-the-badge
[license-url]: https://github.com/jaumebecks/bose-qc-toggle-profile/blob/master/LICENSE.txt
[product-screenshot]: images/screenshot.png
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/jaume-jimenez-forteza
