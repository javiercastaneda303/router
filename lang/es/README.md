# @atomico/router

pequeño controlador de rutas

```jsx
import { h, render } from "@atomico/core";
import { Router } from "@atomico/router";
import { Welcome, Blog, NotFound } from "./pages";

render(
	<Router>
		<Welcome path="/" />
		<Blog path="/blog" />
		<NotFound default />
	</Router>
);
```

## useRoute

permite escuchar el estado de una ruta especifica.

```jsx
import { useRoute } from "@atomico/router";

function Component() {
	let [inRoute, params] = useRouter("/");
}
```

- `/id` : fix route
- `/:id` : param
- `/:id?` : optional param
- `/:id...` : param rest

## useRedirect

returns a redirect callback

```jsx
import { useRedirect } from "@atomico/router";

function Component() {
	let redirect = useRedirect();
	redirect("/");
	redirect("/users");
}
```

## Router

select from the children the route that matches the pattern.

```jsx
import { h, render } from "@atomico/core";
import { Router } from "@atomico/router";
import { Welcome, Blog, NotFound } from "./pages";

render(
	<Router>
		<Welcome path="/" />
		<Blog path="/blog" />
		<NotFound default />
	</Router>
);
```