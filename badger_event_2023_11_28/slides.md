---
marp: true
title: "Mapping the Future of Sustainable Digital Products"
author: Stuart Harris, Red Badger
class: invert
style: |
  :root {
    --color-canvas-default: #303030
  }
  a {
    font-size: 0.6em;
  }
  em {
    font-style: normal;
    font-weight: bold;
    color: #F24A01;
  }
  img[alt~="center"] {
    display: block;
    margin: 0 auto;
  }
  img[alt="1"] { view-transition-name: one; contain: layout; /* required */ }
  img[alt="2"] { view-transition-name: two; contain: layout; /* required */ }
  img[alt="3"] { view-transition-name: three; contain: layout; /* required */ }
  img[alt="4"] { view-transition-name: four; contain: layout; /* required */ }
  img[alt="5"] { view-transition-name: five; contain: layout; /* required */ }
  img[alt="6"] { view-transition-name: six; contain: layout; /* required */ }
  img:is([alt="1"], [alt="2"], [alt="3"], [alt="4"], [alt="5"], [alt="6"]) {
    height: 64px;
    position: relative;
    top: -0.1em;
    vertical-align: middle;
    width: 64px;
  }
  .morph {
    display: inline-block;
    view-transition-name: var(--morph-name);
    contain: layout;
    vertical-align: middle;
  }
transition: fade 300ms
---

[1]: https://icongr.am/material/numeric-1-circle.svg?color=666666
[2]: https://icongr.am/material/numeric-2-circle.svg?color=666666
[3]: https://icongr.am/material/numeric-3-circle.svg?color=666666
[4]: https://icongr.am/material/numeric-4-circle.svg?color=666666
[5]: https://icongr.am/material/numeric-5-circle.svg?color=666666
[6]: https://icongr.am/material/numeric-6-circle.svg?color=666666
[1a]: https://icongr.am/material/numeric-1-circle.svg?color=ff9900
[2a]: https://icongr.am/material/numeric-2-circle.svg?color=ff9900
[3a]: https://icongr.am/material/numeric-3-circle.svg?color=ff9900
[4a]: https://icongr.am/material/numeric-4-circle.svg?color=ff9900
[5a]: https://icongr.am/material/numeric-5-circle.svg?color=ff9900
[6a]: https://icongr.am/material/numeric-6-circle.svg?color=ff9900

![bg right vertical ](./banner.png)
![h:100](../assets/RB_Screen_Logos_Artwork-02.svg)

# Mapping the Future of Sustainable Digital Products

2023-11-28

Stuart Harris

Founder & Chief Scientist

Red Badger

---

<!--
paginate: true
footer: "Mapping the Future of Sustainable Digital Products"
-->

![1][1] Rust

![2][2] WebAssembly

![3][3] Next-gen platforms

---

![bg right grayscale](../assets/stu.jpg)

# Stu

- Software engineer
- Founder of Red Badger

> [@stuartharris](https://twitter.com/stuartharris)

## ![h:80px](../assets/RB_Screen_Logos_Artwork-02.svg)

---

# 6 principles of sustainable software engineering

1. _Carbon efficiency_ — minimize the amount of carbon emitted per unit of work
2. _Energy efficiency_ — the more you utilize a computer, the more efficient it
   becomes at converting electricity to useful computing operations
3. _Carbon awareness_ — Shifting demand to times when carbon intensity is low
4. _Hardware efficiency_ — reduce embodied carbon by extending the life of
   hardware
5. _Measurement_ — measure the carbon footprint of your software
6. _Climate commitments_ — net zero (abate/eliminate) vs. carbon neutral
   (offset)

> [25 minute overview](https://learn.microsoft.com/en-us/training/modules/sustainable-software-engineering-overview/)

---

![h:540 center](https://learn.microsoft.com/en-us/training/modules/sustainable-software-engineering-overview/media/7-measurement-sci-image.jpg)

> [Green Software Foundation](https://greensoftware.foundation/)

---

# Sustainable Software Engineering

> Find as many "Carbon Proxies" as you can

- Time-to-interactive and Page weight
- Average server response time
- Cost of your services
- The utilisation of your servers

> [Sustainable Software Engineering overview](https://learn.microsoft.com/en-gb/training/modules/sustainable-software-engineering-overview),
> [How to measure and reduce the carbon footprint of your application](https://www.microsoft.com/en-gb/industry/blog/technetuk/2021/10/12/how-to-measure-and-reduce-the-carbon-footprint-of-your-application/)

---

## Three revolutions

![1][1a] <span class="morph" style="--morph-name:rust;">**Rust** is a
_revolution_ in sustainable software engineering</span>

![2][2] WebAssembly

![3][3] Next-gen platforms

---

# ![1 h:150 w:150][1a] <span class="morph" style="--morph-name:rust;">**Rust** is a _revolution_ in sustainable software engineering</span>

![bg right:40% 80%](https://upload.wikimedia.org/wikipedia/commons/0/0f/Original_Ferris.svg)

---

<style scoped>section { --color-canvas-default: #808080 }</style>

![h:540 center](https://corrode.dev/why-rust/energy-consumption.svg)

> [Why Rust in production?](https://corrode.dev/why-rust/),
> [Sustainability with Rust](https://aws.amazon.com/blogs/opensource/sustainability-with-rust/)

---

<style scoped>section { --color-canvas-default: #808080 }</style>

![h:540 center](https://corrode.dev/why-rust/robustness.svg)

> [Why Rust in production?](https://corrode.dev/why-rust/)

---

<style scoped>section { --color-canvas-default: #808080 }</style>

![h:540 center](https://corrode.dev/why-rust/bug-costs.svg)

> [Why Rust in production?](https://corrode.dev/why-rust/)

---

## Three revolutions

![1][1] Rust

![2][2a] <span class="morph" style="--morph-name:wasm;">WebAssembly</span>

![3][3] Next-gen platforms

---

# ![2 h:150 w:150][2a] <span class="morph" style="--morph-name:wasm;">**WebAssembly** is a _revolution_</span>

![bg 50% right](https://upload.wikimedia.org/wikipedia/commons/thumb/1/1f/WebAssembly_Logo.svg/1200px-WebAssembly_Logo.svg.png)

---

# ![2 h:150 w:150][2a] <span class="morph" style="--morph-name:wasm;">The **WebAssembly** _Component Model_</span>

![fit center](https://www.fermyon.com/static/image/spin-twcm-wasi.png)

---

<iframe height="705" src="https://www.youtube.com/embed/tAACYA1Mwv4" title="Keynote: What is a Component (and Why)? - Luke Wagner, Distinguished Engineer, Fastly" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

---

## Three revolutions

![1][1] Rust

![2][2] WebAssembly

![3][3a] <span class="morph" style="--morph-name:platform;">Next-gen
platforms</span>

---

# ![3 h:150 w:150][3a] <span class="morph" style="--morph-name:platform;">**Next-gen platforms** are a _revolution_</span>

![bg right h:400](./raise-platform.png)

---

![h:400 center](https://cosmonic.com/assets/images/smallEpoch-e514189dc062ebf5ff99f937478ea336.jpeg)

---

# **Cosmonic** and _wasmCloud_

> "The next-gen Kubernetes"

> [https://cosmonic.com/](https://cosmonic.com/),
> [https://wasmcloud.com/](https://wasmcloud.com/)

# **Fermyon** and _Spin_

> "The next-gen AWS Lambda"

> [https://www.fermyon.com/](https://www.fermyon.com/),
> [https://www.fermyon.com/spin](https://www.fermyon.com/spin),
> [https://www.fermyon.com/cloud](https://www.fermyon.com/cloud)

---

## Three revolutions

![1][1a] Rust

![2][2a] WebAssembly

![3][3a] Next-gen platforms

---

# Thank you!

<style scoped>section figure { margin-right: 100px !important; }</style>

![fit h:100](https://cdn.jsdelivr.net/gh/twitter/twemoji@14.0.2/assets/svg/1f64f.svg)

[@stuartharris](https://twitter.com/stuartharris)

![bg right:40% fit QR code](./qr.webp)
