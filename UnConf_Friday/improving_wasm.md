#Improving WASM

Leptos and Diaxious main things

From one of the core Leptos maintainers he says that he is bullish and Basically ready now about everything you can do in react you can do in Leptos and it is faster and easier to do in Leptos.

If you have web experience and are really comfortable in the web then Dixious that is react like might be a good thing to look at

Leptos is based on signals. If you haven't done either then they are about the same.

Can you explain more about signals? In broad strokes the way Diaxious works is you have your HTML that doesn't change and is static text and they sent that to the browser and you have different elements of the UI that needs to change that involves interactivity that is were the frameworks are different.

The react way is to rerender the whole tree of data. Throw it away and rerender it and then don't worry about things.

Leptos will keep track of which elements and functions of the UI are dependent on what signals or data so it can update only those pieces when they change. It is a little big harder to write but it is faster.

SolidJS is faster than react. If you compare Dixious then Dixious is slower because they do some magic with the compiler.

What is the state of UI libraries in Leptos. Answer UI libraries doesn't really exist yet but if it is just HTML and CSS then you can drop it in without editing it. They are getting there and working on UI frameworks but this is something that is in progress.

The challenge is the Javascript frameworks have such a head start and so many people working on them. However so many Javascript frameworks come in and out of fashion.

It depends somewhat on your goal. The Rust frameworks have kept the same API for there lifetime and for JS there is a ton of different APIs for slightly different problems.

A signals based two way binding but then that was too hard so react came out. And they switched to hooks from callbacks. It is cycal from some degree.

Right now you have to call through javascript to do any DOM manipulation. In terms of developer experience this will not change but performance wise there is not a ton more maybe 5% better but we are already very fast. If you want to do direct DOM mapifulcation. There is something called sledgehammer that batches calls to the DOM to make it faster.

Right now they are working on the Web Assembly component model that changes how you pass data into and out. This will come within the next 5 years and it is slower.

What is the motivation for the browser to do this? Make gmail faster?

Can the componet modlle replace the FFI there are things that allow interprocess communication today. What the component model is trying to achieve is better data passing into and out of the web assembly part. And it adds the abiltity to pass in references.

Have looked at Yew.

Typescript in day job but it has issues and likes rust so why not help advance the Frontend

Wasmtime and wasmer. Prefers Wasmtime, more stable. This is the library that 

What is on the horizon for Leptos? The Islands archiecture. The idea for islands is in a regular react app you send the HTML with a ton of markers of things that might update and then when it gets to the browser you rehydrate this and with islands you can reduce this to the bare minimum and really reduce the bundle size which is one of the issues with webassembly.

Not bundle splitting because that is not really supported by the Rust tooling right now. Also you still need each bundle to have things like an allocator and such that the javascript code gets for free.

This makes it so you can get types across the platform define in the backend and then use on the frontend.

Leptos compiles a backend and a frontend from one project and it separates what is needed for both devices with a cfg_if flag and you need to say that it can be compiled to both places and then you can use it without thinking about it. By default it is available in both places depending on where you put it.

Leptos.dev

Actix and axum are both the web frameworks. Payvex a new backend server that is not out yet but he has blog posts about it. Poum and Rocket are easier to use in some situations.

They are an Axum fan. It uses the standard http crates and integrates with the tower system so you can integrate gprc and such.

Axum is built on hyper which is built on Tokio
