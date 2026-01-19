### Section
A closeread section is created using opening and closing fenced divs with the `.cr-section` class. This defines the scrollytelling block.

```
:::{.cr-section}
This is a Closeread section
:::
```

This section can be enhanced with stickies (content remains fixed while the user scrolls) and triggers (content that activates the sticky as the user scrolls).

### Stickies
This is an element within a closeread section. It could be a block of text, image, video, or any element that can be rendered in the browser.
It's the element you want to perform closeread on.

```
:::{#cr-identifier}
This block of text is a sticky
:::
```

Since the sticky must be enclosed within a section, the full code would be:

```
:::{.cr-section}
This is a closeread section

:::{#cr-identifier}
This block of text is a sticky within the closeread section

:::

:::
```

### Triggers
A trigger is an element that activates a sticky in a closeread document. How it works:
- identify the point in the doc where you want the sticky to be activated
- at that point, reference the sticky's identifier - just replace the cr- prefix with @

So `cr-identifier` becomes `@cr-identifier`

```
:::{.cr-section}
This is a Closeread section

I want the sticky to appear here --> @cr-identifier

:::{#cr-identifier}
This block of text is a sticky within the closeread section
:::

:::
```

### Focus
Focus effects are prebuilt functions within closeread that add interactivity and dynamism to projects. 
- scaling: magnifies or reduces the size of an element by a given factor --> `scale-by="3"` (triples the size of the sticky)
- panning: moves the view to a specified section of the sticky --> `pan-to"-30px,30px"` (pans 30px left and 30px down)
- zooming: enlarges a specific portion of the context to focus the reader's attention --> `zoom-to="3"` (zooms into line 3)
- highlighting: visually emphasizes a span of text or a line by changing its style or color --> `highlight="2-3` (highlights lines 2 to 3)
