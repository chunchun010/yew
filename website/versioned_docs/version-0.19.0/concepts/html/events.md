---
title: "Events"
---

## Introduction

Yew integrates with the [`web-sys`](https://rustwasm.github.io/wasm-bindgen/api/web_sys/) crate and
uses the events from that crate. The [table below](#event-types) lists all of the `web-sys`
events that are accepted in the `html!` macro.

You can still add a [`Callback`](../components/callbacks.md) for an event that is not listed in the table
below, see [Manual event listener](#manual-event-listener).

## Event Types

:::tip
All the event types mentioned in the following table are re-exported under `yew::events`.
Using the types from `yew::events` makes it easier to ensure version compatibility than
if you were to manually include `web-sys` as a dependency in your crate because you won't
end up using a version which conflicts with the version that Yew specifies.
:::

The event listener name is the expected name when adding an event `Callback` in the `html` macro:

```rust
use yew::{html, Callback};

html! {
    <button onclick={Callback::from(|_| ())}>
    //      ^^^^^^^ event listener name
        { "Click me!" }
    </button>
};
```

The event name is the listener without the "on" prefix, therefore, the `onclick` event listener
listens for `click` events.

| Event listener name         | `web_sys` Event Type                                                                  |
| --------------------------- | ------------------------------------------------------------------------------------- |
| `onabort`                   | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onauxclick`                | [MouseEvent](https://docs.rs/web-sys/latest/web_sys/struct.MouseEvent.html)           |
| `onblur`                    | [FocusEvent](https://docs.rs/web-sys/latest/web_sys/struct.FocusEvent.html)           |
| `oncancel`                  | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `oncanplay`                 | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `oncanplaythrough`          | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onchange`                  | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onclick`                   | [MouseEvent](https://docs.rs/web-sys/latest/web_sys/struct.MouseEvent.html)           |
| `onclose`                   | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `oncontextmenu`             | [MouseEvent](https://docs.rs/web-sys/latest/web_sys/struct.MouseEvent.html)           |
| `oncuechange`               | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `ondblclick`                | [MouseEvent](https://docs.rs/web-sys/latest/web_sys/struct.MouseEvent.html)           |
| `ondrag`                    | [DragEvent](https://docs.rs/web-sys/latest/web_sys/struct.DragEvent.html)             |
| `ondragend`                 | [DragEvent](https://docs.rs/web-sys/latest/web_sys/struct.DragEvent.html)             |
| `ondragenter`               | [DragEvent](https://docs.rs/web-sys/latest/web_sys/struct.DragEvent.html)             |
| `ondragexit`                | [DragEvent](https://docs.rs/web-sys/latest/web_sys/struct.DragEvent.html)             |
| `ondragleave`               | [DragEvent](https://docs.rs/web-sys/latest/web_sys/struct.DragEvent.htmk)             |
| `ondragover`                | [DragEvent](https://docs.rs/web-sys/latest/web_sys/struct.DragEvent.html)             |
| `ondragstart`               | [DragEvent](https://docs.rs/web-sys/latest/web_sys/struct.DragEvent.html)             |
| `ondrop`                    | [DragEvent](https://docs.rs/web-sys/latest/web_sys/struct.DragEvent.html)             |
| `ondurationchange`          | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onemptied`                 | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onended`                   | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onerror`                   | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onfocus`                   | [FocusEvent](https://docs.rs/web-sys/latest/web_sys/struct.FocusEvent.html)           |
| `onfocusin`                 | [FocusEvent](https://docs.rs/web-sys/latest/web_sys/struct.FocusEvent.html)           |
| `onfocusout`                | [FocusEvent](https://docs.rs/web-sys/latest/web_sys/struct.FocusEvent.html)           |
| `onformdata`                | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `oninput`                   | [InputEvent](https://docs.rs/web-sys/latest/web_sys/struct.InputEvent.html)           |
| `oninvalid`                 | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onkeydown`                 | [KeyboardEvent](https://docs.rs/web-sys/latest/web_sys/struct.KeyboardEvent.html)     |
| `onkeypress`                | [KeyboardEvent](https://docs.rs/web-sys/latest/web_sys/struct.KeyboardEvent.html)     |
| `onkeyup`                   | [KeyboardEvent](https://docs.rs/web-sys/latest/web_sys/struct.KeyboardEvent.html)     |
| `onload`                    | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onloadeddata`              | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onloadedmetadata`          | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onloadstart`               | [ProgressEvent](https://docs.rs/web-sys/latest/web_sys/struct.ProgressEvent.html)     |
| `onmousedown`               | [MouseEvent](https://docs.rs/web-sys/latest/web_sys/struct.MouseEvent.html)           |
| `onmouseenter`              | [MouseEvent](https://docs.rs/web-sys/latest/web_sys/struct.MouseEvent.html)           |
| `onmouseleave`              | [MouseEvent](https://docs.rs/web-sys/latest/web_sys/struct.MouseEvent.html)           |
| `onmousemove`               | [MouseEvent](https://docs.rs/web-sys/latest/web_sys/struct.MouseEvent.html)           |
| `onmouseout`                | [MouseEvent](https://docs.rs/web-sys/latest/web_sys/struct.MouseEvent.html)           |
| `onmouseover`               | [MouseEvent](https://docs.rs/web-sys/latest/web_sys/struct.MouseEvent.html)           |
| `onmouseup`                 | [MouseEvent](https://docs.rs/web-sys/latest/web_sys/struct.MouseEvent.html)           |
| `onpause`                   | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onplay`                    | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onplaying`                 | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onprogress`                | [ProgressEvent](https://docs.rs/web-sys/latest/web_sys/struct.ProgressEvent.html)     |
| `onratechange`              | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onreset`                   | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onresize`                  | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onscroll`                  | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onsecuritypolicyviolation` | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onseeked`                  | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onseeking`                 | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onselect`                  | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onslotchange`              | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onstalled`                 | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onsubmit`                  | [FocusEvent](https://docs.rs/web-sys/latest/web_sys/struct.FocusEvent.html)           |
| `onsuspend`                 | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `ontimeupdate`              | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `ontoggle`                  | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onvolumechange`            | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onwaiting`                 | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onwheel`                   | [WheelEvent](https://docs.rs/web-sys/latest/web_sys/struct.WheelEvent.html)           |
| `oncopy`                    | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `oncut`                     | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onpaste`                   | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onanimationcancel`         | [AnimationEvent](https://docs.rs/web-sys/latest/web_sys/struct.AnimationEvent.html)   |
| `onanimationend`            | [AnimationEvent](https://docs.rs/web-sys/latest/web_sys/struct.AnimationEvent.html)   |
| `onanimationiteration`      | [AnimationEvent](https://docs.rs/web-sys/latest/web_sys/struct.AnimationEvent.html)   |
| `onanimationstart`          | [AnimationEvent](https://docs.rs/web-sys/latest/web_sys/struct.AnimationEvent.html)   |
| `ongotpointercapture`       | [PointerEvent](https://docs.rs/web-sys/latest/web_sys/struct.PointerEvent.html)       |
| `onloadend`                 | [ProgressEvent](https://docs.rs/web-sys/latest/web_sys/struct.ProgressEvent.html)     |
| `onlostpointercapture`      | [PointerEvent](https://docs.rs/web-sys/latest/web_sys/struct.PointerEvent.html)       |
| `onpointercancel`           | [PointerEvent](https://docs.rs/web-sys/latest/web_sys/struct.PointerEvent.html)       |
| `onpointerdown`             | [PointerEvent](https://docs.rs/web-sys/latest/web_sys/struct.PointerEvent.html)       |
| `onpointerenter`            | [PointerEvent](https://docs.rs/web-sys/latest/web_sys/struct.PointerEvent.html)       |
| `onpointerleave`            | [PointerEvent](https://docs.rs/web-sys/latest/web_sys/struct.PointerEvent.html)       |
| `onpointerlockchange`       | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onpointerlockerror`        | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onpointermove`             | [PointerEvent](https://docs.rs/web-sys/latest/web_sys/struct.PointerEvent.html)       |
| `onpointerout`              | [PointerEvent](https://docs.rs/web-sys/latest/web_sys/struct.PointerEvent.html)       |
| `onpointerover`             | [PointerEvent](https://docs.rs/web-sys/latest/web_sys/struct.PointerEvent.html)       |
| `onpointerup`               | [PointerEvent](https://docs.rs/web-sys/latest/web_sys/struct.PointerEvent.html)       |
| `onselectionchange`         | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onselectstart`             | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `onshow`                    | [Event](https://docs.rs/web-sys/latest/web_sys/struct.Event.html)                     |
| `ontouchcancel`             | [TouchEvent](https://docs.rs/web-sys/latest/web_sys/struct.TouchEvent.html)           |
| `ontouchend`                | [TouchEvent](https://docs.rs/web-sys/latest/web_sys/struct.TouchEvent.html)           |
| `ontouchmove`               | [TouchEvent](https://docs.rs/web-sys/latest/web_sys/struct.TouchEvent.html)           |
| `ontouchstart`              | [TouchEvent](https://docs.rs/web-sys/latest/web_sys/struct.TouchEvent.html)           |
| `ontransitioncancel`        | [TransitionEvent](https://docs.rs/web-sys/latest/web_sys/struct.TransitionEvent.html) |
| `ontransitionend`           | [TransitionEvent](https://docs.rs/web-sys/latest/web_sys/struct.TransitionEvent.html) |
| `ontransitionrun`           | [TransitionEvent](https://docs.rs/web-sys/latest/web_sys/struct.TransitionEvent.html) |
| `ontransitionstart`         | [TransitionEvent](https://docs.rs/web-sys/latest/web_sys/struct.TransitionEvent.html) |

## Typed event target

:::caution
In this section **target ([Event.target](https://developer.mozilla.org/en-US/docs/Web/API/Event/target))**
is always referring to the element at which the event was dispatched from.


This will **not** always be the element at which the `Callback` is placed.
:::

In event `Callback`s you may want to get the target of that event. For example, the
`change` event gives no information but is used to notify that something has changed.

In Yew getting the target element in the correct type can be done in a few ways and we will go through
them here. Calling [`web_sys::Event::target`](https://rustwasm.github.io/wasm-bindgen/api/web_sys/struct.Event.html#method.target)
on an event returns an optional [`web_sys::EventTarget`](https://rustwasm.github.io/wasm-bindgen/api/web_sys/struct.EventTarget.html)
type, which might not seem very useful when you want to know the value of your input element.

In all the approaches below we are going to tackle the same problem, so it's clear where the approach
differs opposed to the problem at hand.

**The Problem:**

We have an `onchange` `Callback` on my `<input>` element and each time it is invoked we want to send
an [update](../components#update) `Msg` to our component.

Our `Msg` enum looks like this:

```rust
pub enum Msg {
    InputValue(String),
}
```

### Using `JsCast`

The [`wasm-bindgen`](https://rustwasm.github.io/wasm-bindgen/api/wasm_bindgen/index.html) crate has
a useful trait; [`JsCast`](https://rustwasm.github.io/wasm-bindgen/api/wasm_bindgen/trait.JsCast.html)
which allows us to hop and skip our way to the type we want, as long as it implements `JsCast`. We can
do this cautiously, which involves some runtime checks and failure types like `Option` and `Result`,
or we can do it dangerously.

Enough talk, more code:

```toml title="Cargo.toml"
[dependencies]
# need wasm-bindgen for JsCast
wasm-bindgen = "0.2"
```

```rust
//highlight-next-line
use wasm_bindgen::JsCast;
use web_sys::{EventTarget, HtmlInputElement};
use yew::{
    events::Event,
    html,
    Component, Context, Html,
};

pub struct Comp;

pub enum Msg {
    InputValue(String),
}

impl Component for Comp {
    type Message = Msg;
    type Properties = ();

    fn create(_: &Context<Self>) -> Self {
        Self
    }

    fn view(&self, ctx: &Context<Self>) -> Html {
        let link = ctx.link();

        // Use batch_callback so if something unexpected happens we can return
        // None and do nothing
        let on_cautious_change = link.batch_callback(|e: Event| {
            // When events are created the target is undefined, it's only
            // when dispatched does the target get added.
            let target: Option<EventTarget> = e.target();
            // Events can bubble so this listener might catch events from child
            // elements which are not of type HtmlInputElement
            //highlight-next-line
            let input = target.and_then(|t| t.dyn_into::<HtmlInputElement>().ok());

            input.map(|input| Msg::InputValue(input.value()))
        });

        let on_dangerous_change = link.callback(|e: Event| {
            let target: EventTarget = e
                .target()
                .expect("Event should have a target when dispatched");
            // You must KNOW target is a HtmlInputElement, otherwise
            // the call to value would be Undefined Behaviour (UB).
            //highlight-next-line
            Msg::InputValue(target.unchecked_into::<HtmlInputElement>().value())
        });

        html! {
            <>
                <label for="cautious-input">
                    { "My cautious input:" }
                    <input onchange={on_cautious_change}
                        id="cautious-input"
                        type="text"
                    />
                </label>
                <label for="dangerous-input">
                    { "My dangerous input:" }
                    <input onchange={on_dangerous_change}
                        id="dangerous-input"
                        type="text"
                    />
                </label>
            </>
        }
    }
}
```
:::tip
Use `batch_callback` when you want to conditionally return a value from a `Callback`.
:::

The methods from `JsCast` are [`dyn_into`](https://rustwasm.github.io/wasm-bindgen/api/wasm_bindgen/trait.JsCast.html#method.dyn_into)
and [`unchecked_into`](https://rustwasm.github.io/wasm-bindgen/api/wasm_bindgen/trait.JsCast.html#method.unchecked_into)
and you can probably see, they allowed
us to go from `EventTarget` to [`HtmlInputElement`](https://rustwasm.github.io/wasm-bindgen/api/web_sys/struct.HtmlInputElement.html).
The `dyn_into` method is cautious because at
runtime it will check whether the type is actually a `HtmlInputElement` and if not return an
`Err(JsValue)`, the [`JsValue`](https://rustwasm.github.io/wasm-bindgen/api/wasm_bindgen/struct.JsValue.html)
is a catch-all type and is essentially giving you back the object to try again.

At this point you might be thinking... when is the dangerous version ok to use? In the case above it
is safe<sup>1</sup> as we've set the `Callback` on to an element with no children so the target can
only be that same element.


_<sup>1</sup> As safe as anything can be when JS land is involved._

### Using `TargetCast`

**It is highly recommended to read [Using JsCast](#using-jscast) first!**

:::note
`TargetCast` was designed to feel very similar to `JsCast` - this is to allow new users to get a feel
for the behaviour of `JsCast` but with the smaller scope of events and their targets.

`TargetCast` vs `JsCast` is purely preference, you will find that `TargetCast` implements something
similar to what you would using `JsCast`.
:::

The `TargetCast` trait builds off of `JsCast` and is specialized towards getting typed event targets
from events.

`TargetCast` comes with Yew so no need to add a dependency in order to use the trait methods on events
but it works in a very similar way to `JsCast`.

```rust
use web_sys::HtmlInputElement;
use yew::{
    events::Event,
    html,
    // Need to import TargetCast
    //highlight-next-line
    Component, Context, Html, TargetCast,
};

pub struct Comp;

pub enum Msg {
    InputValue(String),
}

impl Component for Comp {
    type Message = Msg;
    type Properties = ();

    fn create(_: &Context<Self>) -> Self {
        Self
    }

    fn view(&self, ctx: &Context<Self>) -> Html {
        let link = ctx.link();

        let on_cautious_change = link.batch_callback(|e: Event| {
            //highlight-next-line
            let input = e.target_dyn_into::<HtmlInputElement>();

            input.map(|input| Msg::InputValue(input.value()))
        });

        let on_dangerous_change = link.callback(|e: Event| {
            // You must KNOW target is a HtmlInputElement, otherwise
            // the call to value would be Undefined Behaviour (UB).
            //highlight-next-line
            Msg::InputValue(e.target_unchecked_into::<HtmlInputElement>().value())
        });

        html! {
            <>
                <label for="cautious-input">
                    { "My cautious input:" }
                    <input onchange={on_cautious_change}
                        id="cautious-input"
                        type="text"
                    />
                </label>
                <label for="dangerous-input">
                    { "My dangerous input:" }
                    <input onchange={on_dangerous_change}
                        id="dangerous-input"
                        type="text"
                    />
                </label>
            </>
        }
    }
}
```
If you followed the advice above and read about `JsCast`, or know the trait, you can probably
see that `TargetCast::target_dyn_into` feels similar to `JsCast::dyn_into` but specifically
does the cast on the target of the event. `TargetCast::target_unchecked_into` is similar to
`JsCast::unchecked_into`, and as such all the same warnings above `JsCast` apply to `TargetCast`.


### Using `NodeRef`

[`NodeRef`](../components/refs.md) can be used instead of querying the event given to a `Callback`.

```rust
//highlight-start
use web_sys::HtmlInputElement;
use yew::{html, Component, Context, Html, NodeRef};
//highlight-end

pub struct Comp {
    //highlight-next-line
    my_input: NodeRef,
}

pub enum Msg {
    InputValue(String),
}

impl Component for Comp {
    type Message = Msg;
    type Properties = ();

    fn create(_: &Context<Self>) -> Self {
        Self {
            //highlight-next-line
            my_input: NodeRef::default(),
        }
    }

    fn view(&self, ctx: &Context<Self>) -> Html {
        let link = ctx.link();

        let my_input_ref = self.my_input.clone();

        let onchange = link.batch_callback(move |_| {
            //highlight-next-line
            let input = my_input_ref.cast::<HtmlInputElement>();

            input.map(|input| Msg::InputValue(input.value()))
        });

        html! {
            <>
                <label for="my-input">
                    { "My input:" }
                    //highlight-next-line
                    <input ref={self.my_input.clone()}
                        {onchange}
                        id="my-input"
                        type="text"
                    />
                </label>
            </>
        }
    }
}
```
Using `NodeRef`, you can ignore the event and use the `NodeRef::cast` method to get an
`Option<HtmlInputElement>` - this is optional as calling `cast` before the `NodeRef` has been
set, or when the type doesn't match will return `None`.

You might also see by using `NodeRef` we don't have to send the `String` back in the
`Msg::InputValue` as we always have `my_input` in the component state - so we could do the following:

```rust
use web_sys::HtmlInputElement;
use yew::{html, Component, Context, Html, NodeRef};

pub struct Comp {
    my_input: NodeRef,
}

pub enum Msg {
    // Signal the input element has changed
    //highlight-next-line
    InputChanged,
}

impl Component for Comp {
    type Message = Msg;
    type Properties = ();

    fn create(_: &Context<Self>) -> Self {
        Self {
            my_input: NodeRef::default(),
        }
    }

    //highlight-start
    fn update(&mut self, _: &Context<Self>, msg: Self::Message) -> bool {
        match msg {
            Msg::InputChanged => {
                if let Some(input) = self.my_input.cast::<HtmlInputElement>() {
                    let value = input.value();
                    // do something with value

                    true
                } else {
                    false
                }
            }
        }
    }
    //highlight-end

    fn view(&self, ctx: &Context<Self>) -> Html {
        let link = ctx.link();
        //highlight-next-line
        let onchange = link.callback(|_| Msg::InputChanged);

        html! {
            <label for="my-input">
                { "My input:" }
                <input ref={self.my_input.clone()}
                    {onchange}
                    id="my-input"
                    type="text"
                />
            </label>
        }
    }
}
```

Which approach you take depends on your component and your preferences, there is no _blessed_ way
per se.

## Manual event listener

You may want to listen to an event that is not supported by Yew's `html` macro, see the
[supported events listed here](#event-types).

In order to add an event listener to one of elements manually we need the help of
[`NodeRef`](../components/refs) so that in the `rendered` method we can add a listener using the
[`web-sys`](https://rustwasm.github.io/wasm-bindgen/api/web_sys/index.html) and
[wasm-bindgen](https://rustwasm.github.io/wasm-bindgen/api/wasm_bindgen/index.html) API.
We do this in `rendered` as this is the only time we can guarantee that the element exists in
the browser, Yew needs some time to create them after `view` is called.

The examples below are going to show adding listeners for the made-up `custard` event. All events
either unsupported by yew or custom can be represented as a
[`web_sys::Event`](https://rustwasm.github.io/wasm-bindgen/api/web_sys/struct.Event.html). If you
need to access a specific method or field on a custom / unsupported event then you can use the
methods of [`JsCast`](https://rustwasm.github.io/wasm-bindgen/api/wasm_bindgen/trait.JsCast.html)
in order to convert to the type required.

### Using `Closure` (verbose)

Using the `web-sys` and `wasm-bindgen` API's directly for this can be a bit painful.. so brace
yourself ([there is a more concise way thanks to `gloo`](#using-gloo-concise)).

```rust
use wasm_bindgen::{prelude::Closure, JsCast};
use web_sys::HtmlElement;
use yew::{
    events::Event,
    html,
    Component, Context, Html, NodeRef,
};

pub struct Comp {
    my_div: NodeRef,
    custard_listener: Option<Closure<dyn Fn(Event)>>,
}

pub enum Msg {
    Custard,
}

impl Component for Comp {
    type Message = Msg;
    type Properties = ();

    fn create(_: &Context<Self>) -> Self {
        Self {
            my_div: NodeRef::default(),
            custard_listener: None,
        }
    }

    fn update(&mut self, _: &Context<Self>, msg: Self::Message) -> bool {
        match msg {
            Msg::Custard => {
                // do something about custard..
                true
            }
        }
    }

    fn view(&self, _: &Context<Self>) -> Html {
        html! {
            <div ref={self.my_div.clone()} id="my-div"></div>
        }
    }

    fn rendered(&mut self, ctx: &Context<Self>, first_render: bool) {
        if !first_render {
            return;
        }

        if let Some(element) = self.my_div.cast::<HtmlElement>() {
            // Create your Callback as you normally would
            let oncustard = ctx.link().callback(|_: Event| Msg::Custard);

            // Create a Closure from a Box<dyn Fn> - this has to be 'static
            let listener =
                Closure::<dyn Fn(Event)>::wrap(
                    Box::new(move |e: Event| oncustard.emit(e))
                );
            element
                .add_event_listener_with_callback(
                    "custard",
                    listener.as_ref().unchecked_ref()
                )
                .unwrap();

			// Need to save listener in the component otherwise when the
			// event is fired it will try and call the listener that no longer
			// exists in memory!
            self.custard_listener = Some(listener);
        }
    }

    fn destroy(&mut self, _: &Context<Self>) {
        // All done with the component but need to remove
        // the event listener before the custard_listener memory
        // goes out of scope.
        if let (Some(element), Some(listener)) = (
            self.my_div.cast::<HtmlElement>(),
            self.custard_listener.take(),
        ) {
            element
                .remove_event_listener_with_callback(
                    "custard",
                    listener.as_ref().unchecked_ref()
                )
                .unwrap();
        }
    }
}
```

For more information on `Closures`, see
[The `wasm-bindgen` Guide](https://rustwasm.github.io/wasm-bindgen/examples/closures.html).

### Using `gloo` (concise)

The easier way is with `gloo`, more specifically [`gloo_events`](https://docs.rs/gloo-events/0.1.1/gloo_events/index.html)
which is an abstraction for `web-sys`, `wasm-bindgen`.

`gloo_events` has the `EventListener` type which can be used to create and store the
event listener.

```toml title="Cargo.toml"
[dependencies]
gloo-events = "0.1"
```

```rust
use web_sys::HtmlElement;
use yew::{
    events::Event,
    html,
    Component, Context, Html, NodeRef,
};

use gloo_events::EventListener;

pub struct Comp {
    my_div: NodeRef,
    custard_listener: Option<EventListener>,
}

pub enum Msg {
    Custard,
}

impl Component for Comp {
    type Message = Msg;
    type Properties = ();

    fn create(_: &Context<Self>) -> Self {
        Self {
            my_div: NodeRef::default(),
            custard_listener: None,
        }
    }

    fn update(&mut self, _: &Context<Self>, msg: Self::Message) -> bool {
        match msg {
            Msg::Custard => {
                // do something about custard..
                true
            }
        }
    }

    fn view(&self, _: &Context<Self>) -> Html {
        html! {
            <div ref={self.my_div.clone()} id="my-div"></div>
        }
    }

    fn rendered(&mut self, ctx: &Context<Self>, first_render: bool) {
        if !first_render {
            return;
        }

        if let Some(element) = self.my_div.cast::<HtmlElement>() {
            // Create your Callback as you normally would
            let oncustard = ctx.link().callback(|_: Event| Msg::Custard);

            let listener = EventListener::new(
                &element,
                "custard",
                move |e| oncustard.emit(e.clone())
            );

            self.custard_listener = Some(listener);
        }
    }
}
```

Notice that when using an `EventListener` you don't need to do anything when the
component is about to be destroyed as the `EventListener` has a `drop` implementation
which will remove the event listener from the element.

For more information on `EventListener`, see the
[gloo_events docs.rs](https://docs.rs/gloo-events/0.1.1/gloo_events/struct.EventListener.html).