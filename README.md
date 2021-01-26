<h1 align="center"> Macchina </h1>

<p align="center">
  <img src="preview.png"/>
</p>

## Table of Contents:
- [About](#about)
- [Benchmarks](#bench)
- [Features](#features)
- [Installation](#install)
- [Platform Support](#platform-support)

---

## About Macchina <a name="about"></a>
Macchina lets you flex... I mean view system information.
It's an alternative to slower BASH fetchers but isn't as featureful,
so if you're willing to sacrifice features for speed, then Macchina is the right tool for you.

## Benchmarks <a name="bench"></a>
Macchina is pretty fast, see for yourself:

- Execution time is measured using [hyperfine](https://github.com/sharkdp/hyperfine)

| Command | Mean [ms] | Min [ms] | Max [ms] | Relative |
|:---|---:|---:|---:|---:|
| `macchina` | 28.8 ± 0.8 | 27.7 | 30.3 | 1.00 |
| `neofetch` | 247.0 ± 1.8 | 244.5 | 249.8 | 8.57 ± 0.24 |

__Summary__: 'macchina --palette' ran __8.57 ± 0.24__ times __faster__ than 'neofetch'

- Note that hiding elements using Macchina's __--hide__ argument significantly improves speed

---

## Features <a name="features"></a>
Macchina displays basic system information such as:
- Hostname
- Operating system
- Kernel version
- Package count (Arch Linux Only)
- Default shell
- Default terminal
- Processor _model name_, _frequency_ and _thread count_
- Memory usage
- Uptime
- Battery _percentage_ and _status_

Macchina supports the following arguments:
- --no-color: disable colors
- --palette: display palette
- --hide: for hiding elements such as host, os, kern, et cetera.
- --short-cpu: shorten processor output
- --short-sh: shorten shell output
- --help

---

## Installation <a name="install"></a>

Macchina is not yet ready to be deployed on [crates.io](https://crates.io/), but you can compile it from source and play around with it.

Here's how _you_ can do that:

1. Clone the repo: `git clone https://github.com/grtcdr/macchina`
2. Navigate to the folder and compile from source: `cd macchina && cargo build`
3. __target/__ has been generated by cargo and Macchina's binary file can now be run: `./target/debug/macchina`

__Bonus__: To run macchina from anywhere on your system, you have two options:

1. Place `macchina/target/debug/macchina` somewhere in your __$PATH__, like _~/.local/bin_ or _/usr/bin_.

:heavy_exclamation_mark: Any changes you make to the source code will apply to the macchina binary file but you'll need to place the newly built binary file on your __$PATH__ __again__ to run it from _anywhere on your system_ with your new changes.

2. Create a new symlink for Macchina:

:heavy_exclamation_mark: This symlink will point to the binary file, so everytime you modify the source code and rebuild, running `$ macchina` from _anywhere on your system_ will run the newly built binary file.

---

## Will Macchina Work on Your Macchina? <a name="platform-support"></a>

|  Platform     |      Support       |
| :-:           |        :-:         |
| Linux         | :heavy_check_mark: |
| BSD           |     :question:     |
| MacOS         |                    |
| Windows       |                    |

> Cells containing :question: have not yet been tested.
