---
title: 'HLSL-Eigenschaftenseiten: Allgemein'
ms.date: 11/04/2016
f1_keywords:
- VC.Project.FXCompilerTool.ShaderModel
- VC.Project.FXCompilerTool.PreprocessorDefinitions
- VC.Project.FXCompilerTool.ShaderType
- VC.Project.FXCompilerTool.EnableDebuggingInformation
- VC.Project.FXCompilerTool.AdditionalIncludeDirectories
- VC.Project.FXCompilerTool.DisableOptimizations
- VC.Project.FXCompilerTool.EntryPointName
ms.assetid: 0e02f2a6-f123-43da-b04b-a0719a7c2b03
ms.openlocfilehash: 0fce8a3b2a43cf05024a028a9e3325a929922abb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291469"
---
# <a name="hlsl-property-pages-general"></a>HLSL-Eigenschaftenseiten: Allgemein

Verwenden Sie zum Konfigurieren der folgenden Eigenschaften des HLSL-Compilers („fxc.exe“) die Eigenschaftenseite **Allgemein**. Informationen über den Zugriff auf die **allgemeine** Eigenschaftenseite im Ordner "HLSL" finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

## <a name="uielement-list"></a>UIElement-Liste

- **Zusätzliche Includeverzeichnisse**

   Fügt dem Includepfad mindestens ein Verzeichnis hinzu. Verwenden Sie Semikolons, um die Verzeichnisse zu trennen.

Diese Eigenschaft entspricht dem Befehlszeilenargument **/I[path]**.

- **Einstiegspunktname**

   Gibt den Einstiegspunkt für den Shader an. Der Standardwert ist **main**.

Diese Eigenschaft entspricht dem Befehlszeilenargument **/E[name]**.

- **Optimierungen deaktivieren**

   **Ja (/Od)** deaktiviert Optimierungen, andernfalls **Nein**. Für die **Debugkonfigurationen** ist standardmäßig **Ja (/Od)** und für die **Releasekonfigurationen** ist **Nein** festgelegt.

Das Befehlszeilenargument **/Od** für den HLSL-Compiler gilt implizit für das Befehlszeilenargument **/Gfp**, jedoch ist die Ausgabe möglicherweise nicht mit der Ausgabe identisch, die durch Übergeben beider Befehlszeilenargumente (**/Od** und **/Gfp**) explizit erstellt wird.

- **Debuginformationen aktivieren**

   **Ja (/Zi)** aktiviert Debuginformationen, andernfalls **Nein**. Für die **Debugkonfigurationen** ist standardmäßig **Ja (/Zi)** und für die **Releasekonfigurationen** ist **Nein** festgelegt.

- **Shadertyp**

   Gibt die Art des Shaders an. Verschiedene Arten von Shadern implementieren verschiedene Teile der Grafikpipeline. Bestimmte Arten von Shadern sind nur in neueren Shadermodellen verfügbar (die durch die Eigenschaft **Shadermodell** angegeben werden), z.B. wurden Compute-Shader mit Shadermodell 5 eingeführt.

   Diese Eigenschaft entspricht dem Teil **\[type]** des Befehlszeilenarguments **/T \[type]_\[model]** für den HLSL-Compiler. Die Eigenschaft **Shadermodell** gibt den Teil **[model]** des Arguments an.

- **Shadermodell**

   Gibt das Shadermodell an. Verschiedene Shadermodelle verfügen über unterschiedliche Funktionen. Im Allgemeinen bieten neuere Shadermodelle erweiterte Funktionen, erfordern jedoch modernere Grafikhardware zum Ausführen des Shadercodes. Bestimmte Arten von Shadern (die durch die Eigenschaft **Shadertyp** angegeben werden) sind nur in aktuelleren Shadermodellen verfügbar, z.B. wurden Compute-Shader mit Shadermodell 5 eingeführt.

   Diese Eigenschaft entspricht dem Teil **\[model]** des Befehlszeilenarguments **/T \[type]_\[model]** für den HLSL-Compiler. Die Eigenschaft **Shadertyp** gibt den Teil **[type]** des Arguments an.

- **Präprozessordefinitionen**

   Fügt mindestens eine Präprozessorsymboldefinition hinzu, die auf die HLSL-Quellcodedatei angewendet wird. Verwenden Sie Semikolons, um die Symboldefinitionen zu trennen.

   Diese Eigenschaft entspricht dem Befehlszeilenargument **/D \[definitions]** für den HLSL-Compiler.

## <a name="see-also"></a>Siehe auch

[Eigenschaftenseiten "HLSL"](hlsl-property-pages.md)<br>
[HLSL-Eigenschaftenseiten: Erweitert](hlsl-property-pages-advanced.md)<br>
[HLSL-Eigenschaftenseiten: Ausgabedateien](hlsl-property-pages-output-files.md)
