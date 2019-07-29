---
title: Eigenschaftenseiten "HLSL"
ms.date: 07/24/2019
ms.assetid: 0c65f5ec-a2a5-4f5b-8d4c-fa57113a5a1d
f1_keywords:
- VC.Project.FXCompilerTool.AdditionalIncludeDirectories
- VC.Project.FXCompilerTool.SuppressStartupBanner
- VC.Project.FXCompilerTool.EntryPointName
- VC.Project.FXCompilerTool.TreatWarningAsError
- VC.Project.FXCompilerTool.DisableOptimizations
- VC.Project.FXCompilerTool.EnableDebuggingInformation
- VC.Project.FXCompilerTool.ShaderType
- VC.Project.FXCompilerTool.ShaderModel
- VC.Project.FXCompilerTool.AllResourcesBound
- VC.Project.FXCompilerTool.EnableUnboundedDescriptorTables
- VC.Project.FXCompilerTool.SetRootSignature
- VC.Project.FXCompilerTool.PreprocessorDefinitions
- VC.Project.FXCompilerTool.AdditionalOptionsPage
- VC.Project.FXCompilerTool.VariableName
- VC.Project.FXCompilerTool.HeaderFileOutput
- VC.Project.FXCompilerTool.ObjectFileOutput
- VC.Project.FXCompilerTool.AssemblerOutput
- VC.Project.FXCompilerTool.AssemblerOutputFile
- VC.Project.FXCompilerTool.CompileD2DCustomEffect
- VC.Project.FXCompilerTool.MultiProcFXC
ms.openlocfilehash: a45ae433e5adaa8aeaf32215d4af7ad0a247af04
ms.sourcegitcommit: 720b74dddb1cdf4e570d55103158304ee1df81f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2019
ms.locfileid: "68606409"
---
# <a name="hlsl-compiler-property-pages"></a>Eigenschaften Seiten des HLSL-Compilers

Sie können den HLSL-Compiler-Eigenschaftenseiten („fxc.exe“) verwenden, um zu konfigurieren, wie die einzelnen HLSL-Shaderdateien erstellt werden. Sie können auch Befehlszeilenargumente für den HLSL-Compiler angeben, indem Sie die Eigenschaft **zusätzliche Optionen** der **Befehlszeilen** -Eigenschaften Seite verwenden. Dies schließt Argumente ein, die nicht mithilfe anderer Eigenschaften der HLSL-Eigenschaften Seiten konfiguriert werden können. Informationen über den HLSL-Compiler finden Sie unter [Effect-Compiler Tool](https://go.microsoft.com/fwlink/p/?LinkID=258285&clcid=0x409).

## <a name="hlsl-general-property-page"></a>HLSL-Eigenschaften Seite "Allgemein"

### <a name="additional-include-directories"></a>Zusätzliche Includeverzeichnisse

Gibt mindestens ein Verzeichnis an, das dem include-Pfad hinzugefügt werden soll. Verwenden Sie Semikolons als Trennzeichen, wenn mehrere Verzeichnisse vorhanden sind. (/I [Pfad])

### <a name="entrypoint-name"></a>Name des Einstiegs Punkts

Gibt den Namen des Einstiegs Punkts für den Shader an (/E [Name]).

### <a name="disable-optimizations"></a>Optimierungen deaktivieren

**Ja (/Od)** deaktiviert Optimierungen, andernfalls **Nein**. Für die **Debugkonfigurationen** ist standardmäßig **Ja (/Od)** und für die **Releasekonfigurationen** ist **Nein** festgelegt.

Das Befehlszeilenargument **/Od** für den HLSL-Compiler gilt implizit für das Befehlszeilenargument **/Gfp**, jedoch ist die Ausgabe möglicherweise nicht mit der Ausgabe identisch, die durch Übergeben beider Befehlszeilenargumente ( **/Od** und **/Gfp**) explizit erstellt wird.

### <a name="enable-debugging-information"></a>Debuginformationen aktivieren

**Ja (/Zi)** aktiviert Debuginformationen, andernfalls **Nein**. Für die **Debugkonfigurationen** ist standardmäßig **Ja (/Zi)** und für die **Releasekonfigurationen** ist **Nein** festgelegt.

### <a name="shader-type"></a>Shadertyp

Gibt die Art des Shaders an. Verschiedene Arten von Shadern implementieren verschiedene Teile der Grafikpipeline. Bestimmte Arten von Shadern sind nur in neueren Shadermodellen verfügbar (die durch die Eigenschaft **Shadermodell** angegeben werden), z.B. wurden Compute-Shader mit Shadermodell 5 eingeführt.

Diese Eigenschaft entspricht dem Teil **\[type]** des Befehlszeilenarguments **/T \[type]_\[model]** für den HLSL-Compiler. Die Eigenschaft **Shadermodell** gibt den Teil **[model]** des Arguments an.

**Optionen**

- **Effect class (Effect-Klasse)**
- **Vertex-Shader**
- **Pixel-Shader**
- **Geometrie-Shader**
- **Rumpf-Shader**
- **Domänen-Shader**
- **Compute-Shader**
- **Bibliothek**
- **Stamm Signatur Objekt generieren**

### <a name="shader-model"></a>Shadermodell

Gibt das Shadermodell an. Verschiedene Shadermodelle verfügen über unterschiedliche Funktionen. Im Allgemeinen bieten neuere Shadermodelle erweiterte Funktionen, erfordern jedoch modernere Grafikhardware zum Ausführen des Shadercodes. Bestimmte Arten von Shadern (die durch die Eigenschaft **Shadertyp** angegeben werden) sind nur in aktuelleren Shadermodellen verfügbar, z.B. wurden Compute-Shader mit Shadermodell 5 eingeführt.

Diese Eigenschaft entspricht dem Teil **\[model]** des Befehlszeilenarguments **/T \[type]_\[model]** für den HLSL-Compiler. Die Eigenschaft **Shadertyp** gibt den Teil **[type]** des Arguments an.

### <a name="all-resources-bound"></a>Alle Ressourcen gebunden

Der Compiler geht davon aus, dass alle Ressourcen, auf die ein Shader verweisen kann, gebunden sind und sich für die Dauer der Shader-Ausführung in einem guten Zustand befinden (/all_resources_bound). Verfügbar für Shadermodell 5.1 und höher.

### <a name="enable-unbounded-descriptor-tables"></a>Unbegrenzte deskriptortabellen aktivieren

Informieren Sie den Compiler, dass ein Shader eine Deklaration eines Ressourcen Arrays mit einem ungebundenen Bereich (/enable_unbounded_descriptor_tables) enthalten kann. Verfügbar für Shadermodell 5.1 und höher.

### <a name="set-root-signature"></a>Stamm Signatur festlegen

Stamm Signatur an Shader-Bytecode (/setrootsignature) anfügen. Verfügbar für Shadermodell 5.0 und höher.

### <a name="preprocessor-definitions"></a>Präprozessordefinitionen

Fügt mindestens eine Präprozessorsymboldefinition hinzu, die auf die HLSL-Quellcodedatei angewendet wird. Verwenden Sie Semikolons, um die Symboldefinitionen zu trennen.

Diese Eigenschaft entspricht dem Befehlszeilenargument **/D \[definitions]** für den HLSL-Compiler.

### <a name="compile-a-direct2d-custom-pixel-shader-effect"></a>Direct2D benutzerdefinierten Pixelshadereffekt kompilieren

Kompiliert einen benutzerdefinierten Direct2D-Effekt mit Pixelshadern. Verwenden Sie diese Option nicht für einen benutzerdefinierten Vertex- oder Computeeffekt.

### <a name="multi-processor-compilation"></a>Kompilierung mit mehreren Prozessoren

Führen Sie mehrere Instanzen gleichzeitig aus.

## <a name="advanced-property-page"></a>Erweiterte Eigenschaften Seite

### <a name="suppress-startup-banner"></a>Startbanner unterdrücken

Unterdrückt die Anzeige des Startbanners und der Informationsmeldung. /nologo

### <a name="treat-warnings-as-errors"></a>Warnungen als Fehler behandeln

Behandelt alle Compilerwarnungen als Fehler. Bei einem neuen Projekt kann es empfehlenswert sein, /WX in allen Kompilierungen zu verwenden. Das Beheben aller Warnungen stellt sicher, dass die geringstmögliche Anzahl schwer zu findender Codefehler vorhanden ist.

## <a name="output-files-property-page"></a>Ausgabedateien (Eigenschaften Seite)

### <a name="header-variable-name"></a>Header Variablen Name

Gibt einen Namen für den Variablennamen in der Header Datei an (/VN [Name]).

### <a name="header-file-name"></a>Header Dateiname

Gibt einen Namen für die Headerdatei mit Objektcode an. (/FH [Name])

### <a name="object-file-name"></a>Name der Objektdatei

Gibt einen Namen für die Objektdatei an. (/FO [Name])

### <a name="assembler-output"></a>Assembler-Ausgabe

Gibt die Inhalte der Ausgabedatei für die Assemblysprache an. (/FC,/FX)

**Optionen**

- **Keine Auflistung** -keine Auflistung.
- Assemblyausschließliches **auflisten** : assemblycodedatei
- Assemblycode **und Hex** -Assemblycode und hexadezimal

### <a name="assembler-output-file"></a>Assembler-Ausgabedatei

Gibt den Dateinamen für die Assembly-Codelisten Datei an

## <a name="see-also"></a>Siehe auch

[C++Referenz zur Projekteigenschaften Seite](property-pages-visual-cpp.md)<br>
[Eigenschaftenseiten "Befehlszeile"](command-line-property-pages.md)<br>
[Compiling Shaders (Kompilieren von Shaders)](https://go.microsoft.com/fwlink/p/?LinkID=258284&clcid=0x409)
