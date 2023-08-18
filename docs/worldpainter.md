---
layout: default
title: WorldPainter
nav_order: 2
has_children: true
---

# World Painter

WorldPainter is a wonderful interactive map generator. When I build custom
worlds, they are often developed with WorldPainter.

Do visit the [WorldPainter website](https://www.worldpainter.net/) a visit
at [https://www.worldpainter.net/](https://www.worldpainter.net/). If you like
the application, please do consider donating to its development!

## Specific settings

I personally use MultiMC as launcher. However, that means that the Minecraft
directory is not as expected, so WorldPainter cannot find a proper installation.
Hence, I have a vanilla installation alongside which I hardly use, just
to make sure that any tools that work together with Minecraft can find it.

To debug issues, set `-Dorg.pepsoft.worldpainter.debugLogging=true` (to enable
DEBUG logging) or even `=extra` (to enable TRACE logging), as mentioned on the
[WorldPainter AdvancedSettings](https://www.worldpainter.net/trac/wiki/AdvancedSettings)
page.

I noticed that the output of WorldPainter displays the following:

```
{INFO  } (  org.pepsoft.worldpainter.App) No supported Minecraft installation found; disabling biomes preview and Biomes Viewer
```

I don't believe this is an issue though. A cursory look at the WorldPainter code
tells me that WorldPainter requires a few specific Minecraft version jars (see
[BiomeSchemeManager.java](https://github.com/Captain-Chaos/WorldPainter/blob/master/WorldPainter/WPCore/src/main/java/org/pepsoft/worldpainter/biomeschemes/BiomeSchemeManager.java#L394)
with the `DESCRIPTORS` variable being seeded with a number of md5sums. A review
of the commit history tells me the last update was for the `1.12` jar file, which
probably means that the biome part here is not applicable for recent installations.

