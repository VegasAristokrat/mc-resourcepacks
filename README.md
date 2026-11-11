# mc-resourcepacks

Kleine Ressourcenpakete für unseren Minecraft-Server (NeoForge 1.21.1).

## genblock-fix.zip

Entfernt die schwarzen Quadrate, die die Mod **Plants and Rocks** verursacht.

Ursache: Die Mod setzt beim Generieren Platzhalter-Blöcke (`plants_and_rocks:genblock_*`),
die sich erst auflösen, wenn ihr Chunk tickt. Ihr Modell verweist auf eine vollständig
transparente Textur (`voidtexture`), wird aber mit `render_type: solid` gezeichnet —
der Solid-Pass verwirft Alpha-0-Pixel nicht und malt sie schwarz.

Dieses Paket überschreibt nur die drei Modelldateien mit leeren Modellen. Die Mod-JAR
bleibt unangetastet; Blöcke, Kollision und Welt ändern sich nicht.

Installation: ZIP nach `.minecraft/resourcepacks/`, im Spiel aktivieren und in der Liste
über „Mod Resources" ziehen.
