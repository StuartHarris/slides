---
marp: true
title: "AI: Better code for better digital experiences"
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
  img[alt="1"] { view-transition-name: one; contain: layout; /* required */ }
  img[alt="2"] { view-transition-name: two; contain: layout; /* required */ }
  img[alt="3"] { view-transition-name: three; contain: layout; /* required */ }
  img:is([alt="1"], [alt="2"], [alt="3"]) {
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
    vertical-align: top;
  }
backgroundColor: #303030
transition: fade 300ms
---

![bg right vertical ](./banner.png)
![h:100](../assets/RB_Screen_Logos_Artwork-02.svg)

# AI: Better code for better digital experiences

2023-09-20

Stuart Harris

Founder & Chief Scientist

Red Badger

---

<!--
paginate: true
footer: "AI: Better code for better digital experiences"
-->

![1](https://icongr.am/material/numeric-1-circle.svg?color=666666) _low_-code,
_no_-code, _ai-gen_-code

![2](https://icongr.am/material/numeric-2-circle.svg?color=666666) _Rust_ and
_WebAssembly_

![3](https://icongr.am/material/numeric-3-circle.svg?color=666666) _Crux_ —
experimental, open source tooling for building _headless_ apps

---

![bg right grayscale](../assets/stu.jpg)

# Stu

- Software engineer
- Founder of Red Badger

[@stuartharris](https://twitter.com/stuartharris)

## ![h:80px](../assets/RB_Screen_Logos_Artwork-02.svg)

---

![1](https://icongr.am/material/numeric-1-circle.svg?color=ff9900)
<span class="morph" style="--morph-name:title;">_low_-code, _no_-code,
_ai-gen_-code</span>

![2](https://icongr.am/material/numeric-2-circle.svg?color=666666) _Rust_ and
_WebAssembly_

![3](https://icongr.am/material/numeric-3-circle.svg?color=666666) _Crux_ —
experimental, open source tooling for building _headless_ apps

---

![1 w:256 h:256](https://icongr.am/material/numeric-1-circle.svg?color=ff9900)

# <span class="morph" style="--morph-name:title;">_Code_ — <br/>_low_-code, _no_-code, _ai-gen_-code</span>

<style scoped>section figure { margin-right: 100px !important; }</style>

![bg right:30% fit](https://cdn.jsdelivr.net/gh/twitter/twemoji@14.0.2/assets/svg/1f469-200d-1f527.svg)

---

# ![1](https://icongr.am/material/numeric-1-circle.svg?color=ff9900) Can you express it in words?

> If you _can't describe it_, unambiguously, to a stranger, then low-code will
> not help you.

> If you _can write it down_ in words, then it's easy to write it in code.

> AI can help you write it in words. And in code.

---

# ![1](https://icongr.am/material/numeric-1-circle.svg?color=ff9900) Demo

![bg right](./demo.png)

---

![1](https://icongr.am/material/numeric-1-circle.svg?color=666666) _low_-code,
_no_-code, _ai-gen_-code

![2](https://icongr.am/material/numeric-2-circle.svg?color=ff9900)
<span class="morph" style="--morph-name:title;">_Rust_ and _WebAssembly_</span>

![3](https://icongr.am/material/numeric-3-circle.svg?color=666666) _Crux_ —
experimental, open source tooling for building _headless_ apps

---

![2 w:256 h:256](https://icongr.am/material/numeric-2-circle.svg?color=ff9900)

# <span class="morph" style="--morph-name:title;">_Rust_ and _WebAssembly_</span>

![bg right:40% 80%](https://upload.wikimedia.org/wikipedia/commons/0/0f/Original_Ferris.svg)

---

# ![2](https://icongr.am/material/numeric-2-circle.svg?color=ff9900) Better Tools and Better Architecture

- <span class="morph" style="--morph-name:rust;">**Rust** is a
  _revolution_</span>

  everyone can now build reliable, high quality software in almost any space
  — perfect for multi-platform app development

- **WebAssembly** is a _revolution_

  fast and portable — great for building apps in the languages we love

---

# ![2](https://icongr.am/material/numeric-2-circle.svg?color=ff9900) <span class="morph" style="--morph-name:rust;">**Rust** is a _revolution_</span>

<style scoped>section figure { margin-right: 100px !important; }</style>

![bg right:20% fit](../rust_nation_2023/rustacean-orig-noshadow.png)

- _Quality_ — build software that works
- _Portability_ — from embedded to cloud
- _Sustainability_ — build software that lasts, and be greener
- _Security_ — be secure
- _Cost, Speed_ — be faster overall, and cheaper to run
- _Control, Risk, Compliance_ — be in control, reduce risk, and operate safely
- _Innovation, Talent, Culture_ — innovate, attract and retain talent, and build
  a culture of engineering excellence

---

# ![2](https://icongr.am/material/numeric-2-circle.svg?color=ff9900) Better Tools and Better Architecture

- <span class="morph" style="--morph-name:rust;">**Rust** is a
  _revolution_</span>

  everyone can now build reliable, high quality software in almost any space
  — perfect for multi-platform app development

- <span class="morph" style="--morph-name:wasm;">**WebAssembly** is a
  _revolution_</span>

  fast and portable — great for building apps in the languages we love

---

# ![2](https://icongr.am/material/numeric-2-circle.svg?color=ff9900) <span class="morph" style="--morph-name:wasm;">**WebAssembly** is a _revolution_</span>

![bg right contain](https://d33wubrfki0l68.cloudfront.net/dbe8acea017ac1ca11dbd8f5bc7034bd67847b1a/8f9ac/assets/images/wasifills_fig4-14e087daebfce1bef3b7b2982cbfb9b2.png)

WebAssembly Component Model

WIT

https://cosmonic.com/blog/engineering/gap-bridging-with-wasifills

---

<iframe height="705" src="https://www.youtube.com/embed/tAACYA1Mwv4" title="Keynote: What is a Component (and Why)? - Luke Wagner, Distinguished Engineer, Fastly" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

---

![bg fit](https://d33wubrfki0l68.cloudfront.net/afd53443a08b14482ebcf3969b67ffe525a58719/d05ee/assets/images/epochs-b2c613034d9c952b60b0f9b0a5ca7405.png)

---

![bg fit](https://d33wubrfki0l68.cloudfront.net/f1b9afb55f69c1eb9beb778a81acb32a63fd03ca/12c89/assets/images/writetherightcode-d6efe8598b376df4a8298cdd91b54156.png)

---

# ![3 w:256 h:256](https://icongr.am/material/numeric-3-circle.svg?color=ff9900) Crux

![bg right 50%](../rust_nation_2023/sticker.svg)

- Shared _behaviour_

- in _Rust_ ![h:30](../rust_nation_2023/rustacean-orig-noshadow.png)

- Platform _native_ UX

---

# ![3](https://icongr.am/material/numeric-3-circle.svg?color=ff9900) Building a multi-platform app (don’t @ me!)

<style scoped>
table th {
    width: 14%;
}
</style>

|             | Platform Native | Kotlin MM | React Native | Capacitor Ionic | Flutter | Crux |
| ----------- | :-------------: | :-------: | :----------: | :-------------: | :-----: | :--: |
| Native UX   |       ✅        |    ✅     |     😐️      |       ❌        |   ❌    |  ✅  |
| Web?        |       ❌        |    😐️    |     😐️      |       ✅        |   ✅    |  ✅  |
| Development |       😐️       |    ✅     |     😐️      |       ✅        |   ✅    |  ✅  |
| Testing     |       😐️       |    😐️    |      🤯      |       🤯        |   😐️   |  🤩  |
| Maintenance |       😐️       |    ✅     |      😡      |       😡        |   ✅    |  ✅  |
| Effort      |       3x        |    2x     |      2x      |      1.5x       |  1.4x   | 1.4x |

---

![bg](https://raw.githubusercontent.com/redbadger/crux/master/examples/counter/counter.webp)

---

# ![3](https://icongr.am/material/numeric-3-circle.svg?color=ff9900) What does testing look like?

![bg left](../rust_in_the_enterprise//jenkins-fire.webp)

---

# ![3](https://icongr.am/material/numeric-3-circle.svg?color=ff9900) What does a test look like?

```rust
#[cfg(test)]
mod test {
    use super::*;
    use crux_core::testing::AppTester;

    #[test]
    fn increments_count() {
        let app = AppTester::<App, _>::default();
        let mut model = Model::default();

        let update = app.update(Event::Increment, &mut model);

        // Check the app asked us to `Render`
        assert_effect!(update, Effect::Render(_));

        // Check view model is correct
        let actual_view = app.view(&model).count;
        let expected_view = "Count is: 1";
        assert_eq!(actual_view, expected_view);
    }
}
```

---

# ![3](https://icongr.am/material/numeric-3-circle.svg?color=ff9900) 17ms

## ![bg right:60% fit](../rust_in_the_enterprise//notes_tests.webp)

---

![bg left:40% cover](../rust_nation_2023/crux-bg.svg)

# ![3](https://icongr.am/material/numeric-3-circle.svg?color=ff9900) The crux of Crux

github.com/redbadger/_crux_

- _headless_, multi-platform, composable apps with shared _behaviour_
- better _testability_
- higher _quality_ apps
- more _joy_ from better tools

---

# Thank you! ![h:40](https://cdn.jsdelivr.net/gh/twitter/twemoji@14.0.2/assets/svg/1f64f.svg)

<style scoped>section figure { margin-right: 100px !important; }</style>

![slides bg fit right:30%](qr_code.png)

[@stuartharris](https://twitter.com/stuartharris)

<br/>

[Slides](https://github.com/StuartHarris/slides/blob/main/badger_event_2023_09_20/slides.pdf)

[Crux Book](https://redbadger.github.io/crux/),
[Crux Github](https://github.com/redbadger/crux),
[Crux Docs](https://docs.rs/crux_core/latest/crux_core/),
[Crux Website](https://red-badger.com/crux)

[Rust Nation 2023 Talk](https://www.youtube.com/watch?v=cWCZms92-1g&t=5s)
