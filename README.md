# Reactive HTML example


```typescript
import '@rhtml/hooks';
import '@rhtml/components';
import '@rhtml/graphql';
import '@rhtml/operators';

import { Component, LitElement, html } from '@rxdi/lit-html';

@Component({
  selector: 'app-component',
  template(this: AppComponent) {
    return html`
      <r-part>
        <r-settings .value=${{ fetchPolicy: 'cache-first' }}></r-settings>
        <r-fetch query="{ continents { name } }"></r-fetch>
        <r-render .state=${({ data: { continents } }) => html`
          <r-for .of=${continents}>
            <r-let .item=${({ name }) => name}></r-let>
          </r-for>
        `}>
        </r-render>
      </r-part>
    `;
  }
})
export class AppComponent extends LitElement {}
```


## Start

```bash
npm start
```

## Build

```bash
npm run build
```
