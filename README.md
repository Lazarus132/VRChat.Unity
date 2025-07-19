# VRChat.Unity
# LazarusShader (Unity Shader für Blender-kompatible PBR-Maps)

Ein vollständig integrierter Shader für Unity – optimiert für Assets, die aus **Blender** exportiert wurden. Der Shader bietet eine breite Palette an **physikalisch-basierten Rendering-Funktionen**, **Rad-Texturierung**, **Emission**, **AudioLink**, **POM** (Parallax Occlusion Mapping), **Rim- & Ramp-Lighting** sowie **Custom Reflection Support**.

---

## 🔧 Installation

1. **Unity 2019+** oder höher (empfohlen: 2022+)
2. **Importiere das Shader-Paket** in dein Projekt (`.unitypackage` oder manuell als Ordner)
3. Wechsle im Material zu **Shader → VRChat → LazarusShaderHLSL**
4. Stelle sicher, dass deine Maps korrekt zugewiesen sind (s. Setup unten)

---

## 💼 Unterstützte Shader-Features

### ✅ Standard PBR Maps (aus Blender):

| Map          | Unity Slot             | Property             |
|--------------|------------------------|----------------------|
| Albedo       | `_MainTex`             | `Textur verwenden`  |
| Normal Map   | `_NormalTex`           | `Normalenkarte verwenden` |
| Roughness    | `_RoughnessTex`        | `Rauheits-Textur verwenden` |
| Metallic     | `_MetallicTex`         | `Metallisch-Textur verwenden` |
| AO           | `_AOTex`               | `AO-Textur verwenden` |
| Emission     | `_EmissionTex`         | `Emissions-Textur verwenden` |

---

## 🧪 Besondere Features

- ✅ **Rendering-Modi (Opaque, Cutout, Fade, Transparent)**  
- ✅ **Rad-Modus (Off, Mask, Overlay, Both) mit Textur, Rotation, AudioLink**
- ✅ **Emission (SDR/HDR) mit optionalem Wheel-Modus**
- ✅ **HDR & SDR Tint** mit Schaltern
- ✅ **Rim-Light & Ramp-Lighting** Unterstützung
- ✅ **Heightmap / Parallax Occlusion Mapping (POM)**
- ✅ **IBL (Image-Based Lighting) mit Skybox oder Custom Cube/2D**
- ✅ **Full AudioLink Support**: Rotation, Helligkeit, Textur
- ✅ **Interaktives UV-Zentrum** für Radtextur in Editor-GUI
- ✅ **Auto Image Aspect Detection** (bei aktiviertem AutoScale)

---

## 📸 Beispiel: Blender → Unity Workflow

1. **Blender exportieren** als `.glTF` oder `.FBX` mit PBR Maps:
   - Albedo (BaseColor), Roughness, Metallic, Normal, AO
2. Importiere die Maps in Unity
3. Erstelle Material → Wähle `VRChat/LazarusShaderHLSL`
4. Weise Texturen zu → Aktiviere entsprechende Toggle in der GUI
5. Optional: Aktiviere Transparenz über den Modus „Fade“ oder „Transparent“

---

## 🧩 Unity GUI – Tabs

- **Albedo & Normal** → Textur, Normal Map, Höhenmap
- **PBR** → Metallic, Roughness, AO, ID-Masken
- **Emission** → Textur, Farbe, Modus
- **Rad** → Form, Radius, Rotation, AudioLink
- **Reflexion** → Cubemap, Custom Refl.
- **Sonstiges** → Tönung, Transparenz, IBL-Stärke

---

## 🛠️ Fehlerbehebung

| Problem | Lösung |
|--------|--------|
| Transparenz funktioniert nicht | Stelle `Render Mode = Fade` oder `Transparent`, dann `Transparenz` setzen |
| Shader zeigt falsch invertierte Roughness | In Unity: `_RoughnessTex` verwenden, kein Invert nötig |
| Rad nicht sichtbar | Prüfe `Rad-Modus ≠ Aus`, Radius & Form-Parameter, AudioLink nicht leer |
| Shaderfehler: `_RenderMode` unknown | Achte darauf, dass `_RenderMode` im Shader CBUFFER vorhanden ist |
| GUI doppelt sichtbar | Stelle sicher, dass keine `_Mode`-Property im Shader vorhanden ist, die vom ShaderGUI nicht genutzt wird |

---

## 🧪 Optional: Unity Automation

Verwende die beiliegenden Skripte:

- `LazarusShaderGUI.cs` → GUI Tabs und Features
- `LazarusProfileLoader.cs` → Initiale Material-Profile laden
- `LazarusImportWatcher.cs` → Blender-Import Autoerkennung
- `LazarusBlenderFinder.cs` → Blender-Installation suchen und verknüpfen

---

## 📄 Lizenz

Dieses Shaderprojekt ist open, anpassbar und für persönliche oder kommerzielle VRChat-/Unity-Projekte nutzbar.

---

## 🤝 Mitwirken

Feature-Wünsche? Probleme beim Setup? Kontaktiere den Entwickler oder poste Issues.

---

