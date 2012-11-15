

This font-face definition, create a new familly InterstateBlack which is using different font file depending of the platform
```
@font-face {
    font-family: 'InterstateBlack';
    src: url('fonts/interstate-black-webfont.eot');
    src: url('fonts/interstate-black-webfont.eot?#iefix') format('embedded-opentype'),
         url('fonts/interstate-black-webfont.woff') format('woff'),
         url('fonts/interstate-black-webfont.ttf') format('truetype'),
         url('fonts/interstate-black-webfont.svg#InterstateBlackRegular') format('svg');
    font-weight: normal;
    font-style: normal;
}
```