# Ultra Commerce

## Javascript API Client for Vue Storefront

### Requirements

- node 8+
- npm or yarn

### Adding to your app

```bash
yarn add ultracommerce-api-client-js-vsf
```

### Example usage

test.js

```javascript
const ucApi = require('ultracommerce-api-client-js-vsf')

// Development: Ignore expired certificate if hosted locally.
// process.env.NODE_TLS_REJECT_UNAUTHORIZED = '0';

const basePath = 'https://api.your.domain/api/v1'

const config = new ucApi.Configuration()
const username = 'your-username'
const password = 'your-password'

config.baseOptions = {
  auth: { username, password }
}

const catalog = new ucApi.CatalogEndpointApi(config, basePath)

const main = async () => {
  const res = await catalog.findAllCategoriesUsingGET1()
  console.log(res.data)
}

main()
```

```bash
node test.js
```
