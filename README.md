# svelte-copyright

A Svelte component for displaying a copyright notice.

## Installation

Run the following command to install the `svelte-copyright` in your project.

```bash
npm install svelte-copyright
```

## Props

The following Props are available to configure the `<Copyright>` component.

| Prop | Type | Description |
| `allRightsReserved` | bool | [OPTIONAL] A flag used to determine if the "All rights reserved" text is displayed at the end of the copyright text. (default value: `false`) |
| `someRightsReserved` | bool | [OPTIONAL] A flag used to determine if the "Some rights reserved" text is displayed at the end of the copyright text. (default value: `false`) |
| `noRightsReserved` | bool | [OPTIONAL] A flag used to determine if the "No rights reserved" text is displayed at the end of the copyright text. (default value: `false`) |
| `ownerName` | [OPTIONAL] The name of the copyright owner. |
| `startingYear` | [OPTIONAL] If provided, will set the starting, or creation year of the copyright range. If not provided, only the end year (or current year if no end year is provided) will be displayed |
| `endYear` | [OPTIONAL] If provided, will set the end year, or the last year the copyrighted material was updated. (default value: the current year) |


## Styling the Component

The following CSS variables are available to style the `<Copyright>` component.

| CSS Property | Default Value |
| :-- | :-- |
| `--copyright-margin` | 0 |
| `--copyright-padding` | 0 |
| `--copyright-font-size` | 1rem |
| `--copyright-font-weight` | 400 |
| `--copyright-font-family` | system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif |
| `--copyright-color` | oklch(0, 0, 0) |
| `--copyright-line-height` | 1.2rem |

## Examples

```svelte
<Copyright />

<Copyright startingYear={2022} />

<Copyright companyName="Stark Industries" />

<Copyright
    companyName="Stark Industries"
    companyNamePosition="start"
/>

<Copyright
    companyName="Stark Industries"
    startingYear={2022}\
    allRightsReserved
/>

<Copyright
    companyName="Stark Industries"
    startingYear={2022}
    endYear={2024}
    someRightsReserved
/>

<Copyright
    companyName="Stark Industries"
    startingYear={2022}
    endYear={2024}
    noRightsReserved
/>
```

```
©2025

©2022-2025

©2025 Stark Industries

Stark Industries ©2025

©2022-2025 Stark Industries All rights reserved

Stark Industries ©2022-2025 All rights reserved

Stark Industries ©2022-2024 All rights reserved

©2022-2024 Stark Industries Some rights reserved

©2022-2024 Stark Industries No rights reserved
```
