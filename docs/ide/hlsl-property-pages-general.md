---
title: "Eigenschaftenseiten &quot;HLSL&quot;: &quot;Allgemein&quot;"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "VC.Project.FXCompilerTool.ShaderModel"
  - "VC.Project.FXCompilerTool.PreprocessorDefinitions"
  - "VC.Project.FXCompilerTool.ShaderType"
  - "VC.Project.FXCompilerTool.EnableDebuggingInformation"
  - "VC.Project.FXCompilerTool.AdditionalIncludeDirectories"
  - "VC.Project.FXCompilerTool.DisableOptimizations"
  - "VC.Project.FXCompilerTool.EntryPointName"
dev_langs: 
  - "C++"
ms.assetid: 0e02f2a6-f123-43da-b04b-a0719a7c2b03
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "brpeek"
manager: "ghogen"
---
# Eigenschaftenseiten &quot;HLSL&quot;: &quot;Allgemein&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Um die folgenden Eigenschaften des HLSL\-Compilers \(fxc.exe\) konfigurieren, verwenden Sie die Eigenschaftenseite **Allgemein**.  Informationen darüber, wie Sie auf die Eigenschaftenseite **Allgemein** im HLSL\-Ordner, finden Sie unter [Gewusst wie: Festlegen von Projekteigenschaften mit Eigenschaftenseiten](../misc/how-to-specify-project-properties-with-property-pages.md) zugreift.  
  
## UIElement-Liste  
 **Zusätzliche Includeverzeichnisse**  
 Fügt eine oder mehrere Verzeichnisse Includepfad hinzu.  verwendet Semikolons, um die Verzeichnisse zu trennen.  
  
 Diese Eigenschaft entspricht dem **\/I\[path\]** Befehlszeilenargument.  
  
 **Einstiegspunktname**  
 Gibt den Einstiegspunkt für den Shader an.  Standardmäßig ist der Wert **main**.  
  
 Diese Eigenschaft entspricht dem **\/E\[name\]** Befehlszeilenargument.  
  
 **Optimierungen deaktivieren**  
 **Ja \(\/Od\)**, um der Optimierungen deaktivieren möchten; andernfalls **Nein**.  Standardmäßig ist der Wert **Ja \(\/Od\)** für **Debug**\-Konfigurationen und **Nein** für **Release**\-Konfigurationen.  
  
 Das **\/Od** Befehlszeilenargument zum HLSL\-Compiler wendet implizit das **\/Gfp** Befehlszeilenargument, aber ausgegeben kann nicht in die Ausgabe identisch sein, die erzeugt wird, indem Sie explizit die **\/Od** und **\/Gfp** Befehlszeilenargumente übergeben.  
  
 **Debuginformationen aktivieren**  
 **Ja \(\/Zi\)**, von Debuginformationen zu ermöglichen; andernfalls **Nein**.  Standardmäßig ist der Wert **Ja \(\/Zi\)** für **Debug**\-Konfigurationen und **Nein** für **Release**\-Konfigurationen.  
  
 **Shadertyp**  
 Gibt die Art des Shaders an.  Verschiedene Arten von verschiedenen Teilen des Shaderwerkzeuges der Grafikpipeline.  Bestimmte Arten von Shadern sind nur in späteren Shadermodellen \(die durch die Eigenschaft **Shadermodell** angegeben werden\) – z. B. wurden Berechnungsshader in Shadermodell 5 eingeführt.  
  
 Diese Eigenschaft entspricht dem **\[type\]** Teil des **\/T \[type\]\_\[model\]** Befehlszeilenarguments zum HLSL\-Compiler.  Die Eigenschaft **Shadermodelle** gibt den **\[model\]** Teil des Arguments an.  
  
 **Shadermodell**  
 Legt das Shadermodell fest.  Verschiedene Shadermodelle haben unterschiedliche Funktionen.  Im Allgemeinen bieten neuere Shadermodelle an, erweiterte Funktionen erfordern aber modernere Grafikhardware, den Shadercode auszuführen.  Bestimmte Arten von Shadern \(die durch die Eigenschaft **Shadertyp** angegeben werden\), sind nur im späteren Shader Modell – z. B. Berechnungsshader wurden in eingeführt. Shadermodell 5 verfügbar.  
  
 Diese Eigenschaft entspricht dem **\[model\]** Teil des **\/T \[type\]\_\[model\]** Befehlszeilenarguments zum HLSL\-Compiler.  Die Eigenschaft **Shadertyp** gibt den **\[type\]** Teil des Arguments an.  
  
 **Präprozessordefinitionen**  
 Fügt eine oder mehrere Präprozessorsymboldefinitionen hinzu, um auf die HLSL\-Quellcodedatei anzuwenden.  verwendet Semikolons, um die Symboldefinitionen zu trennen.  
  
 Diese Eigenschaft entspricht dem **\/D \[definitions\]** Befehlszeilenargument zum HLSL\-Compiler.  
  
## Siehe auch  
 [Eigenschaftenseiten "HLSL"](../ide/hlsl-property-pages.md)   
 [Eigenschaftenseiten "HLSL": "Erweitert"](../ide/hlsl-property-pages-advanced.md)   
 [Eigenschaftenseiten "HLSL": "Ausgabedateien"](../ide/hlsl-property-pages-output-files.md)