---
title: 'HLSL-Eigenschaftenseiten: Allgemein | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.FXCompilerTool.ShaderModel
- VC.Project.FXCompilerTool.PreprocessorDefinitions
- VC.Project.FXCompilerTool.ShaderType
- VC.Project.FXCompilerTool.EnableDebuggingInformation
- VC.Project.FXCompilerTool.AdditionalIncludeDirectories
- VC.Project.FXCompilerTool.DisableOptimizations
- VC.Project.FXCompilerTool.EntryPointName
dev_langs:
- C++
ms.assetid: 0e02f2a6-f123-43da-b04b-a0719a7c2b03
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 77cc9a44076999633fd17b049cbcfad75f65eb7e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33340137"
---
# <a name="hlsl-property-pages-general"></a>Eigenschaftenseiten "HLSL": "Allgemein"
Verwenden Sie zum Konfigurieren der folgenden Eigenschaften des HLSL-Compilers („fxc.exe“) die Eigenschaftenseite **Allgemein**. Informationen über das Zugreifen auf die Eigenschaftenseite **Allgemein** im Ordner „HLSL“ finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../ide/working-with-project-properties.md).  
  
## <a name="uielement-list"></a>UIElement-Liste  
 **Zusätzliche Includeverzeichnisse**  
 Fügt dem Includepfad mindestens ein Verzeichnis hinzu. Verwenden Sie Semikolons, um die Verzeichnisse zu trennen.  
  
 Diese Eigenschaft entspricht dem Befehlszeilenargument **/I[path]**.  
  
 **Einstiegspunktname**  
 Gibt den Einstiegspunkt für den Shader an. Der Standardwert ist **main**.  
  
 Diese Eigenschaft entspricht dem Befehlszeilenargument **/E[name]**.  
  
 **Optimierungen deaktivieren**  
 **Ja (/Od)** deaktiviert Optimierungen, andernfalls **Nein**. Für die **Debugkonfigurationen** ist standardmäßig **Ja (/Od)** und für die **Releasekonfigurationen** ist **Nein** festgelegt.  
  
 Das Befehlszeilenargument **/Od** für den HLSL-Compiler gilt implizit für das Befehlszeilenargument **/Gfp**, jedoch ist die Ausgabe möglicherweise nicht mit der Ausgabe identisch, die durch Übergeben beider Befehlszeilenargumente (**/Od** und **/Gfp**) explizit erstellt wird.  
  
 **Debuginformationen aktivieren**  
 **Ja (/Zi)** aktiviert Debuginformationen, andernfalls **Nein**. Für die **Debugkonfigurationen** ist standardmäßig **Ja (/Zi)** und für die **Releasekonfigurationen** ist **Nein** festgelegt.  
  
 **Shadertyp**  
 Gibt die Art des Shaders an. Verschiedene Arten von Shadern implementieren verschiedene Teile der Grafikpipeline. Bestimmte Arten von Shadern sind nur in neueren Shadermodellen verfügbar (die durch die Eigenschaft **Shadermodell** angegeben werden), z.B. wurden Compute-Shader mit Shadermodell 5 eingeführt.  
  
 Diese Eigenschaft entspricht dem Teil **[Type]** des Befehlszeilenarguments **/T [type]_[model]** für den HLSL-Compiler. Die Eigenschaft **Shadermodell** gibt den Teil **[model]** des Arguments an.  
  
 **Shadermodell**  
 Gibt das Shadermodell an. Verschiedene Shadermodelle verfügen über unterschiedliche Funktionen. Im Allgemeinen bieten neuere Shadermodelle erweiterte Funktionen, erfordern jedoch modernere Grafikhardware zum Ausführen des Shadercodes. Bestimmte Arten von Shadern (die durch die Eigenschaft **Shadertyp** angegeben werden) sind nur in aktuelleren Shadermodellen verfügbar, z.B. wurden Compute-Shader mit Shadermodell 5 eingeführt.  
  
 Diese Eigenschaft entspricht dem Teil **[model]** des Befehlszeilenarguments **/T [type]_[model]** für den HLSL-Compiler. Die Eigenschaft **Shadertyp** gibt den Teil **[type]** des Arguments an.  
  
 **Präprozessordefinitionen**  
 Fügt mindestens eine Präprozessorsymboldefinition hinzu, die auf die HLSL-Quellcodedatei angewendet wird. Verwenden Sie Semikolons, um die Symboldefinitionen zu trennen.  
  
 Diese Eigenschaft entspricht dem Befehlszeilenargument **/D [definitions]** für den HLSL-Compiler.  
  
## <a name="see-also"></a>Siehe auch  
 [HLSL Property Pages (HLSL-Eigenschaftenseiten)](../ide/hlsl-property-pages.md)   
 [HLSL Property Pages: Advanced (HLSL-Eigenschaftenseiten: Erweitert)](../ide/hlsl-property-pages-advanced.md)   
 [Eigenschaftenseiten "HLSL": Ausgabedateien](../ide/hlsl-property-pages-output-files.md)