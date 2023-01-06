<p align='center'>
  <img
    src='https://lh3.googleusercontent.com/E3gjlVKsDAXZeSJTLeXPKMq70Yv-buQwHWWiHn6q4ipgoZXAjwD0gQf3_lsN_e0xQb-Vuko7BTy23790_c0NGM4WUR2Kf6QNUc2_5NVAqtieYDXGc5qOvd-ugi_8ONM0IHW6RkPdoI0VK7xymEHL7BS5yfg2lIIqmBOpuF-6xMbcfbxqY01V13C41qBM5896S1Cmy5KgyMn4UBaSXNRp-kBfIPmEMmgBIowBgXrpDAfDW6B1_BUBzsqo34c3zD2ELNQdtykYZXl9m6WTVBOLqI5o5dUEzIfpHHS7PD1DNeliDg91d07ZiFfs6ykOEgyhtiaBW87rKMat2pqGYVAFGlOvKnwd8U--kBsHGbAElLkqq7_gopK0OgtH_ZOtM73Goe_CpFn66xLB4BiFX9SUG8kBtXItMXuLecgM0Y5NPzZw7PbGPxkHu5L1FKzxKh7bbURDkh7KfoXqT0ZeO_Ote7HTICAXkrbwDQu_cKMqt2blNimX7_0Lt-zPIANGTvTHDRMKyHPX7cy9vLb5AuapTy6MoWp8md7c2XjsvLQVG-0O_tFNUkE5jo4wl45Dz8kOKlatF0IdPCgKCfe3pLbhAmuppNYie2Z2sQEEPysdsfjWBQO5VSmPFCtxtz1FmU7McVaO0WY1cDDPEiLONZptsqMIpcbY_FK7S018M365aL-RZZgXwxZecLaz7Ybb_aZ2oZs-clf15NQUfbrNljXEpeMPirPpoIE7LvMED2z8Vu4S_Us7C28tcllCgFpUbKyU2jNv2wAq0gY9CM1FCjfaHj_FcaAFRc46cFjXOnHWVhsJsj4gcJQsTxKdFCNWjG9XtEpXW57C-Lor6_lcok9jGUA6dJn7IAijKeUiXV-WxWQLPB0vlOtEZTcVXhawx7YZpZMZ8RLAPQ2pOdAipOIItQoWuJ389S688UDzFzKhGz-p5AXLgVMK47chfhdVbMxwj96GP1PD80lfEEWmyfJmGbbSF5-m3MadgfyGJWCJvjBiIcxBomzyPqaGt4obe0oaA0XPeW1dt1KDrL87MBu4avHrMw=s263-no?authuser=4'
    style='filter: drop-shadow(0 0 12px #f5015f)'
    width='160'
  />
</p>

<h3 align='center'>Frigatto's</h3>

<p align='center'>Intuitive and user-friendly SCSS library to help you write your stylesheets</p>

## Frigatto's

**Frigatto's** is an intuitive and easy-to-use SCSS library to help you write your stylesheets, providing functions for font configuration, flexbox, position, etc

## Credits

**Author**: Alberto Frigatto

**Email**: albertofrigatto.comercial@gmail.com

**Linkedin**: [Click Here](https://www.linkedin.com/in/alberto-frigatto-a72022251)

## Table of contents

- [Quick start](#quick-start)
- [Usage](#usage)

## Quick start

download the library here via Github or npm

```
npm i frigattos
```

Install the SCSS compiler:

- [npm]('https://www.npmjs.com/package/sass'): `npm i sass`
- [chocolatey]('https://community.chocolatey.org/packages/sass'): `choco install sass`
- homebrew: `brew install sass/sass/sass`

In a SCSS file import the library:

```scss
@use 'path_to_library/frigattos';
```

## Usage

The library itself will produce a basic setup resetting the style of HTML tags

### Functions

- [Border radius](#border-radius)
- [Flexbox](#flexbox)
- [Fonts](#fonts)
- [Geometric shapes](#geometric-shapes)
- [Position](#position)
- [Scrollbar](#scrollbar)

## Border radius

The library provides functions for border radius:

```scss
@include frigattos.radius-top($radius);
```

Rounds the top border of the element

**Parameters**

- **$radius**: length units

```scss
@include frigattos.radius-bottom($radius);
```

Rounds the bottom border of the element

**Parameters**

- **$radius**: length units

```scss
@include frigattos.radius-left($radius);
```

Rounds the left border of the element

**Parameters**

- **$radius**: length units

```scss
@include frigattos.radius-right($radius);
```

Rounds the right border of the element

**Parameters**

- **$radius**: length units

## Flexbox

The library provides functions for flexbox:

```scss
@include frigattos.center;
```

Turns the element into a flex container with centered items

```scss
@include frigattos.column-center;
```

Turns the element into a column flex container with the items aligned to the center

```scss
@include frigattos.column;
```

Turns the element into a column flex container

## Fonts

Fonts available in the library:

- **Sans serif**
  - [Lato](https://fonts.google.com/specimen/Lato?query=lato) - Default
  - [Montserrat](https://fonts.google.com/specimen/Montserrat?query=mont)
  - [Noto Sans](https://fonts.google.com/noto/specimen/Noto+Sans?query=noto)
  - [Open sans](https://fonts.google.com/specimen/Open+Sans?query=open)
  - [Poppins](https://fonts.google.com/specimen/Poppins?query=poppins)
  - [Roboto](https://fonts.google.com/specimen/Roboto?query=roboto)
  - [Ubuntu](https://fonts.google.com/specimen/Ubuntu?query=ubuntu)
- **Serif**
  - [Lora](https://fonts.google.com/specimen/Lora?query=lora) - default
  - [Merriweather](https://fonts.google.com/specimen/Merriweather?query=Merriweather)
  - [Roboto Slab](https://fonts.google.com/specimen/Roboto+Slab?query=Roboto+Slab)
  - [Source Serif Pro](https://fonts.google.com/specimen/Source+Serif+Pro?query=Source+Serif+Pro)
- **Handwriting**
  - [Dancing script](https://fonts.google.com/specimen/Dancing+Script?query=dancing) - default
- **Monospace**
  - [IBM Plex Mono](https://fonts.google.com/specimen/IBM+Plex+Mono?query=IBM+Plex+Mono) - default
  - [Roboto Mono](https://fonts.google.com/specimen/Roboto+Mono?query=Roboto+Mono)

> Fonts are taken from [Google Fonts](https://fonts.google.com)

The library provides a function for including and configuring fonts:

```scss
@include frigattos.include-fonts($fonts...);
```

**Parameters**

- **$fonts**: string or map - arbitrary argument

### Using with string

**Including only one font:**

```scss
// By name
@include frigattos.include-fonts('poppins');
@include frigattos.include-fonts('ibm plex mono');
@include frigattos.include-fonts('roboto slab');

// By type
@include frigattos.include-fonts('handwriting'); // dancing script
@include frigattos.include-fonts('monospace'); // ibm plex mono
@include frigattos.include-fonts('sans serif'); // lato
```

Including only one font per string, in addition to including it, it will also be set as the default font for texts and titles

> ⚠️ If you just want to include a single font without setting it as the default font, use the function with [maps](#using-with-map)

---

**Including more than one font:**

```scss
// By name
@include frigattos.include-fonts('roboto', 'lora');

// By type
@include frigattos.include-fonts('handwriting', 'serif');
```

Including more than one font per string, the function will only import the fonts without defining them in any tag

> ⚠️ If you want to include more than one font and define them, use the function with [maps](#using-with-map)

### Using with map

To include a font, the map must have two properties:

- **name** - font name or type
- **define** - Where the font will be set

**Define values**

- **full typography** - Defines the font for text tags (p, span, blockquote...) and heading (h1-h6)
- **headings** - Defines the font for heading tags (h1-h6)
- **text** - Defines the font for text tags (p, span, blockquote...)
- **code** - Defines the font for code tags (code, samp, kbd)
- **none** - Only import

Examples:

```scss
@include frigattos.include-fonts(
  (
    'name': 'noto sans',
    'define': 'text'
  ),
  (
    'name': 'serif',
    'define': 'headings'
  ),
  (
    'name': 'roboto mono',
    'define': 'code'
  )
);
```

## Geometric shapes

The library provides functions for geometric shapes:

```scss
@include frigattos.square($width, $background, $radius: .4rem);
```

Creates a square

**Parameters**

- **$width**: length units
- **$background**: color
- **$radius**: length units - default value: .4rem

```scss
@include frigattos.circle($width, $background);
```

Creates a square

**Parameters**

- **$width**: length units
- **$background**: color

## Position

The library provides functions for position:

```scss
element {
  @include frigattos.position-center($position: absolute);
}
```

Positions the element in the center of its container

**Parameters**

- **$position**: position values - default value: absolute

```scss
element {
  @include frigattos.position-top-left($position: absolute, $top: 0, $left: 0);
}
```

Positions the element based on top and left

**Parameters**

- **$position**: position values - default value: absolute
- **$top**: length units - default value: 0
- **$left**: length units - default value: 0

```scss
element {
  @include frigattos.position-top-right($position: absolute, $top: 0, $right: 0);
}
```

Positions the element based on top and right

**Parameters**

- **$position**: position values - default value: absolute
- **$top**: length units - default value: 0
- **$right**: length units - default value: 0

```scss
element {
  @include frigattos.position-bottom-left($position: absolute, $bottom: 0, $left: 0);
}
```

Positions the element based on bottom and left

**Parameters**

- **$position**: position values - default value: absolute
- **$bottom**: length units - default value: 0
- **$left**: length units - default value: 0

```scss
element {
  @include frigattos.position-bottom-right($position: absolute, $bottom: 0, $right: 0);
}
```

Positions the element based on bottom and right

**Parameters**

- **$position**: position values - default value: absolute
- **$bottom**: length units - default value: 0
- **$right**: length units - default value: 0

## Scrollbar

The library provides a function for scrollbar:

```scss
element {
  @include frigattos.include-scrollbar($thumb-background, $track-background, $width: 1rem)
}
```

Defines a scrollbar for the element

**Parameters**

- **$thumb-background**: color
- **$track-background**: color
- **$width**: length units - default value: 1rem

Thanks for using my library 😃