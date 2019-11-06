# test vue todo-graphql
A simple Todo PWA (Progressive Web App)

# Tutorial
- Install node modules:
  ```bash
  npm install
  ```

- Open `src/apollo.js` and configure GraphQL Endpoint as follows: 
```js

import Vue from 'vue'
import VueApollo from 'vue-apollo'
import { ApolloClient } from 'apollo-client'
import { HttpLink } from 'apollo-link-http'
import { InMemoryCache } from 'apollo-cache-inmemory'

const httpLink = new HttpLink({
  // You should use an absolute URL here
  uri: 'https://myapp.herokuapp.com/v1/graphql'
})

// Create the apollo client
export const apolloClient = new ApolloClient({
  link: httpLink,
  cache: new InMemoryCache(),
  connectToDevTools: true
})

const apolloProvider = new VueApollo({
  defaultClient: apolloClient
})

// Install the vue plugin
Vue.use(VueApollo)

export default apolloProvider

```

- Compile and hot-reload for development
```bash
  npm run serve
```

- Production Build
```bash
  npm run build
```

