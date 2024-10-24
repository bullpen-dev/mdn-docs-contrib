---
title: <system-color>
slug: Web/CSS/system-color
page-type: css-type
browser-compat: css.types.color.system-color
---

{{CSSRef}}

The **`<system-color>`** [CSS](/en-US/docs/Web/CSS) [data type](/en-US/docs/Web/CSS/CSS_Types) usually reflects the default color choices used for the different parts of a web page.

However, user agents can provide an accessibility feature called _forced colors mode_, in which colors are restricted into a user- and user agent-defined palette, overriding the author's choice of colors in certain properties. In forced colors mode, `<system-color>` exposes the chosen colors, so that the rest of the page can integrate with them. An example of forced colors mode is [high contrast mode on Windows](https://blogs.windows.com/msedgedev/2020/09/17/styling-for-windows-high-contrast-with-new-standards-for-forced-colors/).

In forced colors mode, authors should use colors from the `<system-color>` type for all properties that are _not_ in the set of properties whose colors are overridden. This ensures that the page consistently uses the same color palette across all properties.

Authors can detect forced colors mode using the [`forced-colors`](/en-US/docs/Web/CSS/@media/forced-colors) media feature.

A `<system-color>` value can be used anywhere a [`<color>`](/en-US/docs/Web/CSS/color_value) can be used.

## Syntax

Note that these keywords are _case insensitive_, but are listed here with mixed case for readability.

- `AccentColor`
  - : Background of accented user interface controls
- `AccentColorText`
  - : Text of accented user interface controls
- `ActiveText`
  - : Text of active links
- `ButtonBorder`
  - : Base border color of controls
- `ButtonFace`
  - : Background color of controls
- `ButtonText`
  - : Text color of controls
- `Canvas`
  - : Background of application content or documents
- `CanvasText`
  - : Text color in application content or documents
- `Field`
  - : Background of input fields
- `FieldText`
  - : Text in input fields
- `GrayText`
  - : Text color for disabled items (e.g. a disabled control)
- `Highlight`
  - : Background of selected items
- `HighlightText`
  - : Text color of selected items
- `LinkText`
  - : Text of non-active, non-visited links
- `Mark`
  - : Background of text that has been specially marked (such as by the HTML `mark` element)
- `MarkText`
  - : Text that has been specially marked (such as by the HTML `mark` element)
- `SelectedItem`
  - : Background of selected items, for example, a selected checkbox
- `SelectedItemText`
  - : Text of selected items
- `VisitedText`
  - : Text of visited links

### Deprecated system color keywords

The following keywords were defined in earlier versions of the CSS Color Module. They are now deprecated for use on public web pages.

- `ActiveBorder`
  - : Active window border.
- `ActiveCaption`
  - : Active window caption. Should be used with `CaptionText` as foreground color.
- `AppWorkspace`
  - : Background color of multiple document interface.
- `Background`
  - : Desktop background.
- `ButtonHighlight`
  - : The color of the border facing the light source for 3-D elements that appear 3-D due to that layer of surrounding border.
- `ButtonShadow`
  - : The color of the border away from the light source for 3-D elements that appear 3-D due to that layer of surrounding border.
- `CaptionText`
  - : Text in caption, size box, and scrollbar arrow box. Should be used with the `ActiveCaption` background color.
- `InactiveBorder`
  - : Inactive window border.
- `InactiveCaption`
  - : Inactive window caption. Should be used with the `InactiveCaptionText` foreground color.
- `InactiveCaptionText`
  - : Color of text in an inactive caption. Should be used with the `InactiveCaption` background color.
- `InfoBackground`
  - : Background color for tooltip controls. Should be used with the `InfoText` foreground color.
- `InfoText`
  - : Text color for tooltip controls. Should be used with the `InfoBackground` background color.
- `Menu`
  - : Menu background. Should be used with the `MenuText` or `-moz-MenuBarText` foreground color.
- `MenuText`
  - : Text in menus. Should be used with the `Menu` background color.
- `Scrollbar`
  - : Background color of scroll bars.
- `ThreeDDarkShadow`
  - : The color of the darker (generally outer) of the two borders away from the light source for 3-D elements that appear 3-D due to two concentric layers of surrounding border.
- `ThreeDFace`
  - : The face background color for 3-D elements that appear 3-D due to two concentric layers of surrounding border. Should be used with the `ButtonText` foreground color.
- `ThreeDHighlight`
  - : The color of the lighter (generally outer) of the two borders facing the light source for 3-D elements that appear 3-D due to two concentric layers of surrounding border.
- `ThreeDLightShadow`
  - : The color of the darker (generally inner) of the two borders facing the light source for 3-D elements that appear 3-D due to two concentric layers of surrounding border.
- `ThreeDShadow`
  - : The color of the lighter (generally inner) of the two borders away from the light source for 3-D elements that appear 3-D due to two concentric layers of surrounding border.
- `Window`
  - : Window background. Should be used with the `WindowText` foreground color.
- `WindowFrame`
  - : Window frame.
- `WindowText`
  - : Text in windows. Should be used with the `Window` background color.

## Examples

### Using system colors

In this example we have a button that normally gets its contrast using the {{cssxref("box-shadow")}} property. In forced colors mode, `box-shadow` is forced to `none`, so the example uses the `forced-colors` media feature to ensure there is a border of the appropriate color (`ButtonBorder` in this case).

#### HTML

```html
<button class="button">Press me!</button>
```

#### CSS

```css
.button {
  border: 0;
  padding: 10px;
  box-shadow:
    -2px -2px 5px gray,
    2px 2px 5px gray;
}

@media (forced-colors: active) {
  .button {
    /* Use a border instead, since box-shadow
    is forced to 'none' in forced-colors mode */
    border: 2px ButtonBorder solid;
  }
}
```

#### Result

{{EmbedLiveSample("Using system colors")}}

### Default colors

This example demonstrates the default colors for each of the currently supported system colors.

#### HTML

```HTML
<ul>
  <li style="background-color: AccentColor;">AccentColor: Background of accented user interface controls</li>
  <li style="color: AccentColorText;">AccentColorText: Text of accented user interface controls</li>
  <li style="color: ActiveText;">ActiveText: Text of active links</li>
  <li style="border: 2px solid ButtonBorder;">ButtonBorder: Base border color of controls</li>
  <li style="background-color: ButtonFace;">ButtonFace: Background color of controls</li>
  <li style="color: ButtonText;">ButtonText: Text color of controls</li>
  <li style="background-color: Canvas;">Canvas: Background of application content or documents</li>
  <li style="color: CanvasText;">CanvasText: Text color in application content or documents</li>
  <li style="background-color: Field;">Field: Background of input fields</li>
  <li style="color: FieldText;">FieldText: Text in input fields</li>
  <li style="color: GrayText;">GrayText: Text color for disabled items (e.g., a disabled control)</li>
  <li style="background-color: Highlight;">Highlight: Background of selected items</li>
  <li style="color: HighlightText;">HighlightText: Text color of selected items</li>
  <li style="color: LinkText;">LinkText: Text of non-active, non-visited links</li>
  <li style="background-color: Mark;">Mark: Background of specially marked text</li>
  <li style="color: MarkText;">MarkText: Text of specially marked text</li>
  <li style="background-color: SelectedItem;">SelectedItem: Background of selected items</li>
  <li style="color: SelectedItemText;">SelectedItemText: Text of selected items</li>
  <li style="color: VisitedText;">VisitedText: Text of visited links</li>
</ul>
```

#### Result

{{EmbedLiveSample("Default colors")}}

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [`<color>`](/en-US/docs/Web/CSS/color_value): the data type these keywords belong to
