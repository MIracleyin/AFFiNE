# Feature Flags

## Usage

-   set provider

```tsx
import { FeatureFlagsProvider } from '@toeverything/datasource/feature-flags';

const App = () => {
    return (
        <FeatureFlagsProvider>
            <Page />
        </FeatureFlagsProvider>
    );
};
```

-   use flag

```ts
import { useFlag } from '@toeverything/datasource/feature-flags';

const App = () => {
    //                   flag key, default value
    const flag1 = useFlag('flag1', false);
    // ^? boolean
    const flag2 = useFlag<boolean>('flag2');
    // ^? boolean | undefined
    return flag1 && <div>The flag1 is enable!</div>;
};
```

## How to add a new feature flag?

-   Enter [Portal](https://portal.featureflag.co/switch-manage)
-   Click `New Switch` button
    -   Input `Switch Name`, and Enter
    -   Adjust data and save

# Test flags

**When entering development mode feature flag will NOT be updated in real time**

-   `activateFfcDevMode()` play with feature flags locally
-   `quitFfcDevMode()` quit dev mode

## Running unit tests

Run `nx test datasource/feature-flags` to execute the unit tests via [Jest](https://jestjs.io).

## References

-   [Feature Flag Portal](https://portal.featureflag.co/)
-   [Feature Flag React Web APP DEMO](https://featureflag.moyincloud.com/ksrm/React_Web_APP.html)
