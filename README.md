[Link](https://the-wild-oasis-website-gldn.vercel.app/)

#### What did I learn while coding this project?

> #
>
> - _Client-Side React Apps are re-rendered when the state or parent's state is updated. Client-Side apps are interactive, have components but require a lot of JS to download and client-server data waterfalls. Server-Side Apps have no component or interactivity but also no need to build API. You can fetch all data easy and fast. It closes the data source and displaying all data with no javacsript was needed at all that means faster page load for our users. UI is function of state in Client-Side, function of data in Server-Side. So to provide interactive, has components and easy to fetch, close to the data source and no needs javascript dowloaded the React Server Components were introduced. ,_
> - _**What are React Server Componnets?** React Server Components(RSC) is a completely new full-stack architecture for building React apps. It introduces the server as an integral part of React compoonent trees. React tree extends to the server like a bridge that closes the gap between client and server. And the way in which React does that is by introducing a new kind of component which are server components. React Server Components(RSC) paradigm introdus us the server components that are only rendered on the server, never on the client. They are usually responsible for fetching data right on the server. The server components are only run on the server they have no interactivity, so no state which means that they require exactyly zero Javascript file in the downloadable bundle to do their job. With Server components we can build our application's back-end ,_
> - _Client components are our regular components they responsible for the interactivity. They are responsible for the interactivity, so where the app still function of state. ,_
> - _React Server Components are not active in react app because it needs server to render html before._
> - _In RSC paradigm Server Components are default components. For using Client Components we need to specift the "use client" directive at the top of the module. And Client Components childrens also have to be Client Component. There is no need to specify the "use client" for childrens of Client Components. ,_
> - _The uninteractive part of app doesn't sent any javascript file to the the browser. They are rendered in server. If the component is interactive, the user can effect by clicking, etc. then Client-Component should be used to keep state. ,_
>
> - _Server-client boundary as an split points that are runs on the server and code that runs on the client. We use "use client" in order to create these server-client boundaries which in turn will create client sub-trees. Sub-trees that will be executed in the browser. ,_
> - _Server Components are the default components in the RSC model. Server Components can not be stateful and can't use any hooks. ,_
> - _Client Components are not the default component so they have to be clerified wit "use client" at the top of the module. Client Components are interactive so they can have state or hooks. Client Components can lift state up but server components don't because they haven't state. ,_
> - _Client Components and Server Components can have props but in Server Component they have to be serializable when passed to Client Components. Functions and Classes not serializable. _
> - _ First class way fetching data in React is asycn/await calls in top level code of a Server Component. Also we can fetch data in Client Components. ,_
> - _Server components can import both client and server component but Client Component just can import client component. Client Components can not go back client components. ,_
> - _Client components and server components passed as props and can be render. ,_
> - _On Client Component whenever its state or its parents state changes it will be re-rendered. Whenever the url changes then Server component will be re-render. Because server components are tied to specific routes in the framework.,_
> - _**What are the Good Part of React Server Components?** We can encapsulate all server side concernd right into components as well. We can compose entire full-stack applications by only writing components. And it feels we have one single codebase for front-end and back-end. Server Components are already in the back-end so they have a direct access to the data source. Server components can eliminate all kinds of client-server waterfalls. Instead of fetching one piece of data after another in different client components in the browser, we can just fetch all the data that we need on the server at once and send our stream the final result to the browser all in one go. Server components do not require ant javascript to the browser because that's not where they are executed. We can call this as "Disappearing code" because this fact allows us to import and use huge libraries in the server components without increasing the bundle size at all for free. ,_
> - _**What are the Bad Part of React Server Components?** Things like Context API don't work in server components like all other hooks. We need to make decisions all the time "Should I fetch this data on the server or the client?". If we need mobile app, we have to build an API. Server Components only works with frameworks. ,_
> - _How rendering works in traditional React? The Components that we wrote. Then we compose these component's intances and create tree od component instances which simply calls component tree in React. Rendering means in React call each component function. The result of the calling a component function(return) is a React element which is a Javascript object contains all the necessary information to create DOM elements for the corresponding component instance. As a result of rendering we end up with React element tree which we can also call the virtual DOM. This virtual DOM will be comitted to the actual DOM. ,_
> - _**How RSC works behind the scenes?** First the all Server Componets are rendered on the server as a rendering result a form of React Element. That React Element just contains the output of the Server Component. They only have information on how the DOM for each component will look like, they no longer contain the code itself that was necessart to render each component. The code from the Server Component has disappeared right on the server That the reason of not using hooks in Server Components. Because hooks has disappeared after the component is rendered. That react element has to be that way because it will be sent to the client and it should be serializable. Client Component doesn't be rendered on Server Side. Instead we can imagine this component tree contains a placeholder like a hole in the place where each client component will eventually be rendered. Each of these placeholders or holes contain the serialized props that might have been passed Server Component to current Client Component and the URL to the script that contains the actual component code. And this reference to the code is necessary so then the client component can be executed on the client. So the executed Service Component instances and unexecuted component instances is sent to client which is called RSC payload. This payload is essentially the virtual DOM of all Server Components these have already been rendered and some sub trees of un-rendered client components. This is called the RSC paylaod which that data structure will be sent to the client in the next step. On the Client side the sub-tree of client will be render and the virtual DOM has been completed. ,_
> - _We sent the Server Component as data not an html, because We don't want to be replaced with that new HTML and all current UI state would be lost every Server Component re-render. When the Server Component is re-rendered React is able to merge the current tree on the client with a nre tree coming from the server ,_
> - _As summary React Server Component, we start with a component tree that has both Server and Client Components ans is located on the server. In the RSC architecture the render process is split into two steps. First step where the Server Components are rendered and client components are not. They both exist in the same data structure that we call RSC payload. In RSC payload there is some information for each Client Componetns on the client side later. The RSC payload has a placeholder that includes serialized props passed from a parent Serever Component and the URL that points the script of Client Components code. At the second step with that data React will render the Client Component and render the virtual DOM ,_
> - _One step does not wait to other one to finish. Instead completed render work on the server is streamed to the client right away and integrated seamlessly into the tree on the client over time .,_
> - _SSR (Server Side Rendering) means take the React component tree render it as HTML to the browser. React Bundles which contains the React itself and the Component tree will also need to send browser so that HTML can be hydrated. Hydration is simply back the interactivity to the HTML. In the and we have interactive React App. Only difference is DOM has been genereated on the server not the client.,_
> - _Dynamic SSR is where HTML is generated for each incoming request. _
> - _Server Side Rendering and React Server Components aren't the same thing. They are separate technologies. RSC is not to replace SSR, but to complement it, to work together with it. ,_
> - _The server in Server Side Rendering and the server in React Server Component are not same thing. They can be the same thing but they don't have to be. React Server and React Client are simply two different environments. Two different parts of RSC protocol. React server doesn't even need to be an actual web server. A server is just a computer different from the browser. A computer the developer has access to and can run code on. RSC does not require a running web server. Instead server and client components coulds just be rendered once at build time in a process that we call static site generation. ,_
> - _SSR just take this component tree, render it as HTML and send that HTML to the browser. That the difference is both client and server components are rendered on the web server that Next.js provides. The Client and Server Side run on server on the initial render therefor the output is not DOM nıtes but HTML which is sent to to the browser. Client Components also are rendered on the server on the first render because before React Server Components even existed all components were basically client components. They would all render on the server during server side rendering. Server Componetns will render all components on the server on the initial render. ,_
> - _After the entire component tree being rendered to HTML and shipped off to the browser. After the HTML has been sent, the react bundle needs to be sent. This will contain the React library itself and component's code so that component can be later rendered or hydrated on the client. This bundle will be split many different chunks which will be requested by the client as they become necessary over time. Rendering the Server Components produce the RSC payload which contains rendered server components and props and each Client Component's code URL. RSC Payload is different from the React bundle and it preserve state in the browser as Server Components get re-rendered later. RSC payload is also necessary wit React Bundle or chunks to hydrate the HTML so to make the HTML interactive again. The Client Components are only interactive so only Client Components get hydrated ,_
> - _SSR happents only initial render after that RSC works. On re-renders Client Components only render on the actual client. After the initial render React Server is the same as web server where Next.js is running. The React Client is the same as the user's browser. Whenever the Server Component gets rerendered a new RSC payload is generated an sent to the client, to the actual user's browser ready to be merged into the already existing React tree. The existing UI state can be preserved. ,_
> - _Both Client and Server Componenents are initially rendered on the server when SSR is used after then Server Components run on the actual web server and the client components run on the actual client, actual web browser. ,_
> - _**What is React Suspense?** Suspense is a built-in React Component to catch or to isolate components that are not ready to be rendered yet because they are doing some asynchronous work. And we say that these components or even entire sub trees are suspending because they are not yet ready to be rendered by React. We can say this component even entire sub trees are suspending because they are not ready to be rendered by React. It catches components that are suspending ,_
> - _What causes a component to be suspending? There are two asynchronous tasks. The first one is fetching data using a library that supports Suspense (React Query, Next.js) and second loading additional code using React's lazy loading feature ,_
> - _Suspense is native way to support and handle asynchronous operations in a declarative way. While rendering, suspneding component is found. It will move back up to the closest Suspense parent which we also call a Suspense boundary. It is a boundary because it separates the suspending sub tree from the rest of the app. When Suspense asynchronous works is done all the rendered components are discarded and the fallback component-Spinner- is displayed. We can render the Spinner instead of Product(has asynchronous works component) not the inside of product. Once the suspended component is ready and no longer suspending, React will attempt to render the sub tree under the Suspense boundary. ,_
> - _Components do not automatically suspend just because an asynchronous operation is happening inside them. Integrating async operations with Suspense is hard, ao we can use suspense with React Query, Next.js and Remix. Suspense works just as advertised when combined with React.lazy as we did earlier in the course. ,_
> - _A Fiber tree is an internal representation of each componetnt instance and DOM element of our app. Difference between Fiber tree and virtual DOM is fiber tree is a mutable data structure that is never destroyed. Which make it the perfect place to store state, hooks. And Fiber tree enables so-called concurrent features which allow React to pause rendering with Suspense in the first place. ,_
> - _Behind the scenes in the reconciliation phase whenever we use Suspense, the child tree below the suspense boundary is actually moved into another built-in component called activity. This happens in fiber tree so the activity component can not be seen in the Component tree. The fallback component that we also specify is also already placed in the fiber tree as the sibling of the activity. That fallback is hidden because so-called mode on activity is set to "visible". Meaning that the Suspense children are now visible then as soon as the componet Suspense this mode will be set to "hidden" and as a consequence the fallback spinner will be rendered and the sub tree will be hidden. Once the asynchronous work is done the activity mode gets set back to visible and the final sub-tree can finally be rendered. If a component suspends again later the fallback will be shown again and this entire process runs again as well, always keeping the sub-tree in the fiber tree. ,_
> - _The Suspense children are hidden and remain in the fiber tree means that all state in the sub tree is preserved during subsequent suspending and unsuspending phases ,_
> - _The fallback component will not be shown again if the function that trigged theSuspense wrapped in a transition (startTransition) function. In Next.js, all page navigations are wrapped inside transitions. If a component re-fetches data as a result of a page transition, the fallback component will not be shown again. We can fix this by passing a unique key prop. This will then reset this Suspense boundary ,_
> - _**How does Suspense actually know that a component is suspending?** The component that asynchronous works have done is child componen. So that child component throws a Promise which will trigger the Suspense boundary to render the fallback. ,_
> - _Error boundary always should be a client component. And React Error Boundary caughts only the errors in rendering, not in the callback functions ,_
> - _Root Layout errors are not caught by Error Boundary, if the Root Layout errors will be caught then global-error.js need to be created. That will then replace the entire layout, even the root layout will be gone. The global error needs to define its own HTML and body tag,_
> - _Next.js is a React framework so the rendering is done by new React Component Server Model. Server and Client Components are rendered on the server on the initial render. Next.js uses the React and React-DOM libraries in order to render each route one by one on the server. Next.js splits the rendering work by route and each route can be rendered in different way (static(pre-rendered) or dynamic) ,_
> - _In Next.js each route renders individually, not the entire app. In Static Rendering HTML is generated at build time which means the markup is rendered whenever we run the build command in our Next.js app. The special flavor of Static Rendering is incremental static generation which a route can be re-rendered periodically in the background by refetching the routes data from time to time. Static means rendered just once at build time whenever the data for the route in question doesn't change very often and is not personalized to user ,_
> - _Dynamic Rendering means that the HTML is generated at request time. In other words the server renders a new version of the page for each request that hits the server. It gets used when the data changes constantly and is personalized to the user. Dynamic rendering is also necessary whenever rendering the route requires informatiom that depends on the request itself (search params from URL or a cookie,header). By default in Next.js all routes are rendered statically even page component or another component in the tree fetches some data. The idea behind this the static pages are way faster because they have been already pre-generated and don't need to rebuild for every request which saves time and resources and static assets can easily be hosted on a so-called CDN(Content Delivery Network). This is what happens automatically when we deploy our NExt çjs app to Vercel which is the company that built the NExt.js framework. On the other hand each dynamic route when deployed to Vercel, They will become a serverless function,_
> - _If all routes of an app are static, the entire app can be exported as a static site generation or SSG for short. ,_
> - _There is also Partial Pre-Rendering(PPR) which mixes dynamic and static rendering in the same route. ,_
> - _Developers don't directly choose whether a route should be static or dynamic. Next.js will automatically switch to dynamic rendering under some conditions:
>   1-) The route has a dynamic segment (page uses params)
>   2-) searchParams are used in the page component
>   3-) headers() or cookies() are used in any of the routes' server components
>   4-) An uncached data request in any of the route's server components.
>   We can force Next.js to render a route dynamically simply by manipulating the way fetch requests are cached. ,_
> - _**What is CDN?** CDN is a network of related servers that are related at meny different positions around the world. These servers are all cached so they store a website's static content. It delivers content to each user from a server locates as close as possible to that user. The advantage of this is all data doesn't need to travel entire planet. Most host providers like Vercel, Netlify will automatically host all your website's static assets on a global CDN.,_
> - _**Serverless computing**: The Serverless computing model that we cab run application code without managing the server ourselves. Instead we can run just a single function on a cloud function is running, unlike a traditional Node.js app where the seerver is constantly running. Each dynamic route becomes a serverless function. ,_
> - _**Incremental Static Regeneration(ISR)**: A Next.js features that allows developers tp update the content of a static page in the background even after the website has been built and deployed. This happens by re-fetching the data of a certain component or od entire route after a certain interval. _
> - _**Partial Pre-Rendering(PPR)** combines the best parts of both static and dynamic rendering in the same route. It is a middle ground between fully static pages and fully dynamic pages. A static (pre-rendered) shell is served immediately from CDN, leaving holes for dynamic content. Fully static parts of is served as fast as possible from a CDN. This makes initial loading super fast and that is called a shell because it leaves in some holes for dynamic content. When the static parts are loading, in the meantime the server starts rendering the synamic content which takes a bit longer than just sending the static shell. As soon as the some rendering results are available the server starts streaming the dynamic part of the page to the client filling the holes that we had left. That's means no longer pages force to be dynamically rendered just because one tiny part of the page depends on incoming request or uncached data request.,_
> - _**What is caching?** Caching means taking data that has been fetched or computed and storing it in a temporary location for future access. When we need the same data in the future we can just take it from the cache instead of re-fetching or re-computing it every time the data is needed again. ,_
> - _In Next.js cachin is very aggressive on the server and user's browser. Next.js provides APIs to revalidate the different caches. Revalidating means remove all the data from cache and update with fresh date by fetching or computing the data again based on the original source._
> - _The idea behind caching is makes apps more performant with faster page load and saves computing and data access costs. ,_
> - _There are four different caching mechanisms in Next.js. Three of cache store data on the server. These are Request Memoization, Data Cache and Full Route Cache, On client side we have Router Cache that known as the client side cache ,_
> - _**1- Request Memorization:** Request Memorization is a technique that caches that data that has been fetched with similar get requests during the lifespan of one request by one user. The data is cached and re-used only during exactly one page render. One certain route fetches the same data in multiple places in the component tree during one render only one actual network request will be made. This cache is lije a short tem memory. This cache allows us to fetch same data ans use at multiple places in the tree without making multiple network request(like products). This mechanism works with only native fetch function with same URL and options object. This is actually a React Feature so that woeks in the React component tree not in Route handlers or server actions,_
> - _**2- Data Cache:** Data Cache method stores all the data that has been fetched either in a specific route or from a single fetch request. The data stays there forever unless we decide to revalidate(clear and refetch the data) the cache. The data is available across multiple requests from different users. It even survices when the app is re-deployed. For server to access multiple users who make some fetch request(same product list). This stored data is used for static render routes. When this data is revalidated the corresponding static page will be re-generated. This is the whole idea behind ISR(incremental static regeneration). Data Cache is just used for static data ,_
> - _**3- Full Route Cache:** Full Route Cache stores the entire static pages in the form of HTML and RSC payload. Static pages only rendered once and then be served to multiple users. This cache enables static pages work the way they do basically acting like a storing mechanism for these static routes. This cache is so related with data cache, the full route cache is persisted until the data cache is invalidated, until the data cache is cleared. Because the underlying data changes then the page needs to be regenerated and stored in the cache again in order to reflect the latest data. Unlike the Data Cache, this one does not survive re-deploys. It will be cleared when you deploy a new version of the application,_
> - _**3- Router Cache:**This cache is used to store all pre-fetched and visited pages in the user's browser. This applies to both static and dynamic routes. Because browser doesn't know and care about static or dynamic pages. The idea behinf having all the pages stored in memory allows for instant navigation. But this caching visited pages can cause to be displayed stale data. Dynamic pages are stored for 30 seconds if they are dynamic and for five minutes if they are static pages. There is no way of revalidating this cache, updating these cached pages. Unless the user makes a hard reload or closes the tab we run into the possibility of rendering outdated data ._
> - _This caching mechanisms happens in production mode. Caching doesn't work in development. In development there is no caching._
> - _There is no clear seperation between front-end and back-end in Next.js. This "Knitting" pattern allows us to build full-stack applications just one codebase.The APIs no longer necessary to fetch or mutate data with RSC Model ,_
> - _In Next.js we have Server Actions to mutate data on the server directly from Client Components. And we can send the data with props._
> - _we can render a Server Component inside of a Client Component if we pass the Server Component as a prop by importing rendered Server Component in a Server Component. That situation is possible when Server Component already has been rendered and created a coponent instance sending Client Component as a prop ,_
> - _Client Components can not import server component,can not go back in client-server boundary and import the Server Components from client. Client Components can render Server and Client Component, but Server Component needs to be executed Server Component instance by sending as props._
> - _Server Components import and render all components._
> - _A Component is a definition like a blueprint. Components create instances when they are used. So the component type can be change across to where to be used., A Server Component normally creates a Server Component instance but if it is used under a Client Component then it becomes a Client Component instance. Children of Client Components ("use client") will automatically will be become a client component as well. _
> - _searchParams only available in page.js not in the server components and the page which searchParams props gets is automatically converts a dynamic page. ,_
> - _Navigation in Next.js is always wrapped in a React transition. In a transition a Suspense won't hide the content that has already been rendered earlier. That's the default behavior of suspense. It just swapped it out as the new content comes in. WE can fetch this by padding in a unique key. And the URL changes, the server component will re-render because searchParam unknown at build time ,_
> - _In Pages Router, the main way of mutating data is to create API endpoints. In App Router and RSC architecture we can handle this by using server actions. To create out API endpoint we use a feature called Route Handlers. We can create Route Handlers by creating route.js file can be in any folder that doesn't have page.js. When a request is sent to URL that corresponds the route handler, bo HTML should be returned.Instead the Route handler is gonne be executed and usually will be return JSON data. If there was also a page.js file in the same folder, it would creat a conflict. We can not sent HTML and JSON data at the same time. ,_
> - _**What is Middleware in Next.js ?** A middleware is a function sits between the incoming request and response.Next.js middleware allows us to run some code based on the incoming request but before the response is completed. ,_
> - _Middleware runs before every single route in our Next.js app. We can use a matcher to specify for which routes the middleware should run. Middleware always runs after the request but before the route the user is visiting is rendered and send back. We can think the middleware as a chunk of code that we paste into every single route, into every page.js component. ,_
> - _Only one middleware function needs to be exported from middleware.js in the project root folder. ,_
> - _The main function of middleware is reading incoming cookies and headers and set the cookies and headers on the response. This enables us to implement features like authentication and authorization. Server-side analyticks, redirects based on geolocation, A/B testing._
> - _Middleware needs to produce a response. That happens in two ways. First and more common way is middleware function redirect or rewrite to some route in our app. Middleware runs before routes are rendered. Second way is to directly send a JSON to the client. We can read and set cookies and headers but in this case the route won't ever be reached and rendered. So it's completely bypassed. This can be usefull all we want to do is dens some data as JSON like an API. ,_
> - _In order to allow users to perform some actual actions in Next.js apps the React Server Component Architecture gives us something called Server Actions. React Server Component Architecture is made of Server Components and Server Actions. Server actions provides us to make our app interactive like delete, update, create actions. We use Server Components for fetching data to fetch our data way faster on Server Side ,_
> - _Server Actions are just asynchronous function that run exclusively on the server. They are easly created by adding the new "use server" directive either to the top of a function in a Server Component or to the top of a standalone file from which we can then export multiple Server Actions. Server Actions can be defined right inside a Server Component where they can be used directly or passed as a prop to a Client Component. We usually can not pass functions as props to Client Components. But Server Actions are actually an acception to that rule. Server Actions can flow from the server to the client and be used there. They can be invoked right in the Server Component in which they are created. The second place in which Server Actions can be created is in a dedicated Server Action Module which needs to start with the "use server" directive. Then all functions exported that file simply become Server Actions. Which then be imported any Server or Client Component. ,_
> - _"use server" only for Server Actions, not for Server Components. Server Components are default Components and don't require any directive. ,_
> - _Behind the scenes the way Server Actions work is that Next.js will automatically create an API endpoint for each Server Actions that we create. So Server Action basically gets its own URL which is sent to the client. The function itself never reaches to the client only the URL. The code itself will always stay on the server. In Server Actions, it's safe to directly connect to databases use secret API keys, because that impossible that the code is leaked to the browser. Whenever a Server action is invoked, when it's called as a result of a user interaction behind the scenes a POST request will be made to the endpoint and all inputs that are sent along the request will be serialized. ,_
> - _Server Actions are automatically created API endpoints. The big benefit of server actions that we no longer need to create a separate API or Next.js route handlers in order to mutate data ,_
> - _Server Actions require a running web server unlike Server Components which could run on build time. Server Actions do not work on build time because without a live web server there would be no endpoints to be called and to be executes as a response to users interacting with the application. Server Actions typically used to handle form submissions. Meaning that we can use the Server Action as an action attribute of regular form element. No matter the form is in Server or Client Component. The form element simply automatically take all the form data and send it to the Server Action in a serialized form using the provided API endpoint behind the scenens. Also Server Actions can respond ._
> - _Server actions can be called like regular functions in event handlers and useEffects. Server actions can be used in useEffect and event handlers only it is Client Components. ,_
> - _Server actions are tightly integrated into the Next.js caching and revalidation system. We can easily revalidate the cache on demand with revalidatePath and revalidateTag. We need to update the UI after ran the Server Actions. ,_
>
> #
