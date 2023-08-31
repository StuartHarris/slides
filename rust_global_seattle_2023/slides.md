---
marp: true
title: Building iOS, Android and Web Apps that share a single Rust Core
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

![bg right vertical fit](https://events.linuxfoundation.org/wp-content/uploads/2023/06/Rust-Global-white.svg)
![bg 70%](https://events.linuxfoundation.org/wp-content/uploads/2023/07/WasmCon-Logo-TaglineMashup_white_v2.svg)
![bg 50%](../assets/RB_Screen_Logos_Artwork-02.svg)

# Building iOS, Android and Web Apps that share a single Rust Core

2023-09-06

Stuart Harris

Founder & Chief Scientist

Red Badger

---

<!--
paginate: true
footer: "Rust Global @ WasmCon, Seattle 2023"
-->

![1](https://icongr.am/material/numeric-1-circle.svg?color=666666) _What_ is the
problem with multi-platform app development today?

![2](https://icongr.am/material/numeric-2-circle.svg?color=666666) _Rust_,
_WebAssembly_, and _Ports and Adapters_

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

![1](https://icongr.am/material/numeric-1-circle.svg?color=ff9900) _What_ is the
problem with multi-platform app development today?

![2](https://icongr.am/material/numeric-2-circle.svg?color=666666) _Rust_,
_WebAssembly_, and _Ports and Adapters_

![3](https://icongr.am/material/numeric-3-circle.svg?color=666666) _Crux_ —
experimental, open source tooling for building _headless_ apps

---

![1 w:256 h:256](https://icongr.am/material/numeric-1-circle.svg?color=ff9900)

# The problem

<style scoped>section figure { margin-right: 100px !important; }</style>

![bg right:30% fit](https://cdn.jsdelivr.net/gh/twitter/twemoji@14.0.2/assets/svg/1f469-200d-1f527.svg)

---

# ![1](https://icongr.am/material/numeric-1-circle.svg?color=ff9900) Tooling and Architecture

## It's too hard to "build quality in"

- Historically, a lack of good _tooling_ has lead to a poor developer experience
  for multi-platform app development

- Bad _architectures_ make applications _hard to test_ and maintain

---

# ![1](https://icongr.am/material/numeric-1-circle.svg?color=ff9900) Building a multi-platform app (don’t @ me!)

<style scoped>
table th {
    width: 16%;
}
</style>

|             | Platform Native | Kotlin MM | React Native | Capacitor Ionic | Flutter |
| ----------- | :-------------: | :-------: | :----------: | :-------------: | :-----: |
| Native UX   |       ✅        |    ✅     |     😐️      |       ❌        |   ❌    |
| Web?        |       ❌        |    😐️    |     😐️      |       ✅        |   ✅    |
| Development |       😐️       |    ✅     |     😐️      |       ✅        |   ✅    |
| Testing     |       😐️       |    😐️    |      🤯      |       🤯        |   😐️   |
| Maintenance |       😐️       |    ✅     |      😡      |       😡        |   ✅    |
| Effort      |       3x        |    2x     |      2x      |      1.5x       |  1.4x   |

---

# ![1](https://icongr.am/material/numeric-1-circle.svg?color=ff9900) UI-centric architecture

- UI layout is the _primary_ organising principle
- Behaviour and interaction with the outside world are _secondary_

<br/>

---

# ![1](https://icongr.am/material/numeric-1-circle.svg?color=ff9900) UI-centric architecture

- UI layout is the _primary_ organising principle
- Behaviour and interaction with the outside world are _secondary_

> “It looks like this… and does that”

---

![1](https://icongr.am/material/numeric-1-circle.svg?color=666666) _What_ is the
problem with multi-platform app development today?

![2](https://icongr.am/material/numeric-2-circle.svg?color=ff9900) _Rust_,
_WebAssembly_, and _Ports and Adapters_

![3](https://icongr.am/material/numeric-3-circle.svg?color=666666) _Crux_ —
experimental, open source tooling for building _headless_ apps

---

![2 w:256 h:256](https://icongr.am/material/numeric-2-circle.svg?color=ff9900)

# The solution

![bg right:40% 80%](https://upload.wikimedia.org/wikipedia/commons/0/0f/Original_Ferris.svg)

---

# ![2](https://icongr.am/material/numeric-2-circle.svg?color=ff9900) Better Tools and Better Architecture

- **Rust** is a _revolution_

  - everyone can now build reliable, high quality software in almost any space
    — perfect for multi-platform app development

- **WebAssembly** is a _revolution_

  - fast and portable — great for building apps in the languages we love

- **Ports and Adapters** is a _revolution_

  - portable and easy to test — easy to build high quality apps

---

# ![2](https://icongr.am/material/numeric-2-circle.svg?color=ff9900) What if we start with behaviour?

We build a _core_ that encapsulates our app’s behaviour:

- updates a _model_ in response to _events_
- emits _effects_ — intent to perform side-effects
- is _pure_ (can be easily tested)

---

<!--transition: fade 600ms-->

<div class="morph" style="--morph-name:title;">

# ![2](https://icongr.am/material/numeric-2-circle.svg?color=ff9900) Behaviour

</div>
<div class="morph" style="--morph-name:update;">
A pure update function (cf. Elm, Redux, etc.)

```rust
fn update(event: Event, state: Model) -> (Model, Vec<Effect>)
```

</div>

---

<div class="morph" style="--morph-name:title;">

# ![2](https://icongr.am/material/numeric-2-circle.svg?color=ff9900) Behaviour with side-effects

</div>
<div class="morph" style="--morph-name:update;">
A pure update function (cf. Elm, Redux, etc.)

```rust
fn update(event: Event, state: Model) -> (Model, Vec<Effect>)
```

</div>
<div class="morph" style="--morph-name:http;">
A dirty function with side-effects

```rust
fn http(effect: Effect) {/*perform HTTP request*/}
```

</div>

---

<div class="morph" style="--morph-name:title;">

# ![2](https://icongr.am/material/numeric-2-circle.svg?color=ff9900) UI

</div>
<div class="morph" style="--morph-name:view;">
Imagine the UI as a projection of state (cf. early React)

```rust
fn view(state: Model) {/*update UI*/}
```

</div>

---

<div class="morph" style="--morph-name:title;">

# ![2](https://icongr.am/material/numeric-2-circle.svg?color=ff9900) UI with platform independence

</div>
<div class="morph" style="--morph-name:view;">
Imagine the UI as a projection of state (cf. early React)

```rust
fn view(state: Model) -> ViewModel
```

</div>
<div class="morph" style="--morph-name:render;">
Introduce a view model

```rust
fn render(view: ViewModel) {/*update UI*/}
```

</div>

---

# ![2](https://icongr.am/material/numeric-2-circle.svg?color=ff9900) Before

_Behavior_

<div class="morph" style="--morph-name:update;">

```rust
fn update(event: Event, state: Model) -> (Model, Vec<Effect>)
```

</div>
<div class="morph" style="--morph-name:http;">

```rust
fn http(effect: Effect) {/*perform HTTP request*/}
```

</div>

_UI_

<div class="morph" style="--morph-name:view;">

```rust
fn view(state: Model) -> ViewModel
```

</div>
<div class="morph" style="--morph-name:render;">

```rust
fn render(view: ViewModel) {/*update UI*/}
```

</div>

---

<!--transition: fade 250ms-->

# ![2](https://icongr.am/material/numeric-2-circle.svg?color=ff9900) After

_Core_

<div class="morph" style="--morph-name:update;">

```rust
fn update(event: Event, state: Model) -> (Model, Vec<Effect>)
```

</div>
<div class="morph" style="--morph-name:view;">

```rust
fn view(state: Model) -> ViewModel
```

</div>

_Shell_

<div class="morph" style="--morph-name:http;">

```rust
fn http(effect: Effect) {/*perform HTTP request*/}
```

</div>
<div class="morph" style="--morph-name:render;">

```rust
fn render(view: ViewModel) {/*update UI*/}
```

</div>

---

# ![2](https://icongr.am/material/numeric-2-circle.svg?color=ff9900) Behaviour-centric architecture

- Behaviour is the _primary_ organising principle
- Interaction with the outside world is _secondary_
- UI is also a side-effect

<br/>

---

# ![2](https://icongr.am/material/numeric-2-circle.svg?color=ff9900) Behaviour-centric architecture

- Behaviour is the _primary_ organising principle
- Interaction with the outside world is _secondary_
- UI is also a side-effect

> “It does this… and looks like that!”

---

# ![2](https://icongr.am/material/numeric-2-circle.svg?color=ff9900) Ports and adapters

![bg right:40% fit opacity:0.5 grayscale](../rust_nation_2023/crux.svg)

> Allow an application to equally be driven by users, programs, automated test
> or batch scripts, and to be developed and tested in isolation from its
> eventual run-time devices and databases.

Alistair Cockburn, 2005

[Hexagonal Architecture](https://alistair.cockburn.us/hexagonal-architecture/)

---

# ![2](https://icongr.am/material/numeric-2-circle.svg?color=ff9900) Ports and adapters

![bg grayscale blur:5px opacity:0.1 fit](https://cdn.jsdelivr.net/gh/twitter/twemoji@14.0.2/assets/svg/1f92f.svg)

> The application can be deployed in ‘’headless’’ mode, so only the API is
> available, and other programs can make use of its functionality

Alistair Cockburn, 2005

## [Hexagonal Architecture](https://alistair.cockburn.us/hexagonal-architecture/)

---

# ![2](https://icongr.am/material/numeric-2-circle.svg?color=ff9900) WebAssembly

<style scoped>section figure { margin-left: 100px !important; }</style>

![bg left:30% fit](./wasm.svg)

WebAssembly helps us stay honest!

![h:60](./wasm-ferris.png)

---

![bg right:50% fit](../rust_nation_2023/crux.svg)

![1](https://icongr.am/material/numeric-1-circle.svg?color=666666) _What_ is the
problem with multi-platform app development today?

![2](https://icongr.am/material/numeric-2-circle.svg?color=666666) _Rust_,
_WebAssembly_, and _Ports and Adapters_

![3](https://icongr.am/material/numeric-3-circle.svg?color=ff9900) _Crux_ —
experimental, open source tooling for building _headless_ apps

---

# ![3 w:256 h:256](https://icongr.am/material/numeric-3-circle.svg?color=ff9900) ![Crux](../rust_nation_2023/crux_logo.svg)

![bg right 60%](../rust_nation_2023/sticker.svg)

- Shared _behaviour_
- Capabilities
- Platform _native_ UX
- _Rust_ yay! ![h:30](../rust_nation_2023/rustacean-orig-noshadow.png)

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

# ![3](https://icongr.am/material/numeric-3-circle.svg?color=ff9900) Who benefits?

<style scoped>
table th {
    width: 14%;
}
</style>

![bg right:72% fit](../rust_nation_2023/benefit.png)

---

# ![3](https://icongr.am/material/numeric-3-circle.svg?color=ff9900) _Any_ client

| platform |  language  |   UI    | library |    lib name    |       FFI        |
| -------- | :--------: | :-----: | :-----: | :------------: | :--------------: |
| iOS      |   Swift    | SwiftUI | static  | `libshared.a`  | `uniffi-bindgen` |
| Android  |   Kotlin   | Compose | dynamic | `libshared.so` | `uniffi-bindgen` |
| Web      | TypeScript |  Remix  |  wasm   | `shared.wasm`  |  `wasm-bindgen`  |
| Web      |    Rust    | Leptos  |  crate  |                |                  |
| CLI      |    Rust    |         |  crate  |                |                  |

Type generation with `serde-generate`

---

![3](https://icongr.am/material/numeric-3-circle.svg?color=ff9900)

<style scoped>
  section figure{
    margin: 36px !important;
  }
</style>

![bg 80%](../rust_nation_2023/architecture.svg)

---

<div class="morph" style="--morph-name:title;">

# ![3](https://icongr.am/material/numeric-3-circle.svg?color=ff9900) Capabilities

</div

Fire and forget

```rust
caps.render.render();
```

Request/response

```rust
caps.http.get(API_URL).expect_json().send(Event::Set);
```

Streaming

```rust
caps.sse.get_json(API_URL, Event::Update);
```

---

<div class="morph" style="--morph-name:title;">

# ![3](https://icongr.am/material/numeric-3-circle.svg?color=ff9900) Capabilities

</div>

- Built-in (`Render`)

- `crux_*` crates (`Http`, `KeyValue`, `Platform`, `Time`)

- Custom

  - `ServerSentEvents` in the
    [Counter example](https://github.com/redbadger/crux/blob/master/examples/counter/shared/src/capabilities/sse.rs)
  - `Delay` example in the
    [book](https://redbadger.github.io/crux/guide/capability_apis.html)
  - `Timer` and `PubSub` in the
    [Notes example](https://github.com/redbadger/crux/tree/master/examples/notes/shared/src/capabilities)

- Community contributed

---

# ![3](https://icongr.am/material/numeric-3-circle.svg?color=ff9900) What does a Crux app look like?

```rust
#[derive(Default)]
pub struct App;

impl crux_core::App for App {
    type Event = Event;
    type Model = Model;
    type ViewModel = ViewModel;
    type Capabilities = Capabilities;

    fn update(&self, event: Self::Event, model: &mut Self::Model, caps: &Self::Capabilities) {
        match event {
            Event::Increment => model.count += 1,
            Event::Decrement => model.count -= 1,
            Event::Reset => model.count = 0,
        };

        caps.render.render();
    }

    fn view(&self, model: &Self::Model) -> Self::ViewModel {
        ViewModel {
            count: format!("Count is: {}", model.count),
        }
    }
}
```

---

# ![3](https://icongr.am/material/numeric-3-circle.svg?color=ff9900) What does a test look like?

```rust
#[cfg(test)]
mod test {
    use super::*;
    use crux_core::testing::AppTester;

    #[test]
    fn increments_count() {
        let app = AppTester::<Hello, _>::default();
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

![bg right cover](../rust_nation_2023/crux-bg.svg)

# ![3](https://icongr.am/material/numeric-3-circle.svg?color=ff9900) Demo

## Headless app development in Rust

---

# ![3](https://icongr.am/material/numeric-3-circle.svg?color=ff9900) The crux of Crux

<style scoped>section figure { margin-left: 100px !important; }</style>

![bg left:30% fit](https://cdn.jsdelivr.net/gh/twitter/twemoji@14.0.2/assets/svg/1f970.svg)

<!-- prettier-ignore -->
* a lightweight runtime
  * for headless, multi-platform, composable apps with shared _behaviour_
  * for better _testability_
  * for higher _quality_
  * for better _reliability_, safety, and security
  * and more _joy_ from better tools

---

# Thank you! ![h:40](https://cdn.jsdelivr.net/gh/twitter/twemoji@14.0.2/assets/svg/1f64f.svg)

<style scoped>section figure { margin-right: 100px !important; }</style>

![slides bg fit right:30%](qr_code.png)

[@stuartharris](https://twitter.com/stuartharris)

<br/>

[Slides](https://github.com/StuartHarris/slides/blob/main/rust_global_seattle_2023/slides.pdf)

[Crux Book](https://redbadger.github.io/crux/),
[Crux Github](https://github.com/redbadger/crux),
[Crux Docs](https://docs.rs/crux_core/latest/crux_core/),
[Crux Website](https://red-badger.com/crux)

[Rust Nation 2023 Talk](https://www.youtube.com/watch?v=cWCZms92-1g&t=5s)
