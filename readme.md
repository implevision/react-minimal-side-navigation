<h1 align="center">react-side-navigation</h1>
<p align="center">  </p>

<h3 align="center">🙋‍♂️ Made by <a href="https://ebtechsol.com">EBTECHSOL</a></h3>

# via npm
npm install @ebtechsol/react-side-navigation

# or yarn
yarn add @ebtechsol/react-side-navigation
```

## Usage

```js
import React from 'react';

import {Navigation} from '@ebtechsol/react-side-navigation';
import '@ebtechsol/react-side-navigation/lib/ReactMinimalSideNavigation.css';

function App() {
    return (
      <>
        <Navigation
            // you can use your own router's api to get pathname
            activeItemId="/management/members"
            onSelect={({itemId}) => {
              // maybe push to the route
            }}
            items={[
              {
                title: 'Dashboard',
                itemId: '/dashboard',
                // you can use your own custom Icon component as well
                // icon is optional
                elemBefore: () => <Icon name="inbox" />,
              },
              {
                title: 'Management',
                itemId: '/management',
                elemBefore: () => <Icon name="users" />,
                subNav: [
                  {
                    title: 'Projects',
                    itemId: '/management/projects',
                    elemBefore: () => <Icon name="cloud-snow" />,
                  },
                  {
                    title: 'Members',
                    itemId: '/management/members',
                    elemBefore: () => <Icon name="coffee" />,
                  },
                ],
              },
              {
                title: 'Another Item',
                itemId: '/another',
                subNav: [
                  {
                    title: 'Teams',
                    itemId: '/management/teams',
                  },
                ],
              },
            ]}
          />
      </>
    );
}

```

## API

#### items

Type: `array`

Navigation items to render.

#### activeItemId

Type: `string`

Currently selected item id.

#### onSelect

Type: `function`

Called when item is clicked.

## Issues

_Looking to contribute? Look for the [Good First Issue](info@ebtechsol.com)
label._

## License

MIT © [EBTECHSOL](https://ebtechsol.com)
