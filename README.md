# CRA and CTA

    CRA is `create-react-app`
    CTA is `create-tsrouter-app`

## First look compare

<details>
  <summary>Create project</summary>

  ##### CRA
  ```bash
  pnpx create-react-app cra-app
  cd cra-app
  pnpm start
  ```
  Then go to <http://localhost:3000>
  ##### CTA
  ```bash
  ```bash
  pnpx create-tsrouter-app cta-app
  cd cta-app
  pnpm start
  ```
  Then go to <http://localhost:3000>
</details>

<details>
  <summary>Update first text on your screen</summary>

  ##### CRA `Learn React` to `Learn React on CRA`
  ```bash
  nano src/App.js
  ```
  ```bash
  import logo from './logo.svg';
  import './App.css';

  function App() {
    return (
      <div className="App">
        <header className="App-header">
          <img src={logo} className="App-logo" alt="logo" />
          <p>
            Edit <code>src/App.js</code> and save to reload.
          </p>
          <a
            className="App-link"
            href="https://reactjs.org"
            target="_blank"
            rel="noopener noreferrer"
          >
            Learn React on CRA
          </a>
        </header>
      </div>
    );
  }
  ```
  ##### CTA `Learn React` to `Learn React on CTA`
  ```bash
  nano src/App.jsx
  ```
  ```bash
  import logo from "./logo.svg";
  import "./App.css";


  function App() {
    return (
      <div className="App">
        <header className="App-header">
          <img src={logo} className="App-logo" alt="logo" />
          <p>
            Edit <code>src/App.jsx</code> and save to reload.
          </p>
          <a
            className="App-link"
            href="https://reactjs.org"
            target="_blank"
            rel="noopener noreferrer"
          >
            Learn React on CTA
          </a>
          <a
            className="App-link"
            href="https://tanstack.com"
            target="_blank"
            rel="noopener noreferrer"
          >
            Learn TanStack
          </a>
        </header>
      </div>
    );
  }

  export default App;
  ```
</details>

## CTA Section

<details>
  <summary>Add Route</summary>
  
  ##### CTA clone `about` from `index`
  ```bash
  nano src/main.jsx
  ```
  ```bash
  ...
  const indexRoute = createRoute({
    getParentRoute: () => rootRoute,
    path: "/",
    component: App,
  });

  const aboutRoute = createRoute({
    getParentRoute: () => rootRoute,
    path: "/about",
    component: () => <div>About Route</div>,
  });

  # const routeTree = rootRoute.addChildren([indexRoute]);
  const routeTree = rootRoute.addChildren([indexRoute, aboutRoute]);
  ...
  ```
  Then go to <http://localhost:3000/about>
</details>

<details>
  <summary>Create with a template</summary>

  ##### Create new project with CTA
  ```bash
  pnpx create-tsrouter-app cta-app-with-template --template file-router
  cd cta-app-with-template
  pnpm start
  ```
  Then go to <http://localhost:3000>

  ##### Add new route
  ```bash
  nano src/routes/about.tsx
  ```
  ```bash
  import { createFileRoute } from "@tanstack/react-router";

  export const Route = createFileRoute("/about")({
      component: RouteComponent,
  });

  function RouteComponent() {
      return <div>About</div>;
  }
  ```
  Then go to <http://localhost:3000/about>
</details>

<details>
  <summary>Create with a style</summary>

  ##### Create new project with CTA
  ```bash
  pnpx create-tsrouter-app cta-app-with-style --template file-router --tailwind
  cd cta-app-with-style
  pnpm start
  ```
  Then go to <http://localhost:3000>
</details>

## Reference
<https://www.youtube.com/watch?v=10J6RyMOxN0>