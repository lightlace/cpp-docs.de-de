---
title: 'Eigenschaftenseiten "HLSL": Allgemein | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.FXCompilerTool.ShaderModel
- VC.Project.FXCompilerTool.PreprocessorDefinitions
- VC.Project.FXCompilerTool.ShaderType
- VC.Project.FXCompilerTool.EnableDebuggingInformation
- VC.Project.FXCompilerTool.AdditionalIncludeDirectories
- VC.Project.FXCompilerTool.DisableOptimizations
- VC.Project.FXCompilerTool.EntryPointName
dev_langs: C++
ms.assetid: 0e02f2a6-f123-43da-b04b-a0719a7c2b03
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: be548966f6e75afde2c137c8beab38903844667c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="hlsl-property-pages-general"></a>Eigenschaftenseiten "HLSL": "Allgemein"
Um die folgenden Eigenschaften des HLSL-Compilers (fxc.exe) zu konfigurieren, verwenden die **allgemeine** Eigenschaftenseite. Informationen über den Zugriff auf die **allgemeine** Eigenschaftenseite im Ordner "HLSL" finden Sie unter [arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md).  
  
## <a name="uielement-list"></a>UIElement-Liste  
 **Zusätzliche Includeverzeichnisse**  
 Fügt eine oder mehrere Verzeichnisse der Include-Pfad an. Verwenden Sie Semikolons, um die Verzeichnisse zu trennen.  
  
 Diese Eigenschaft entspricht der **/i [Pfad] /** Befehlszeilenargument.  
  
 **EntryPoint-Name**  
 Gibt den Einstiegspunkt für den Shader. Standardmäßig ist der Wert **main**.  
  
 Diese Eigenschaft entspricht der **/e [Name]** Befehlszeilenargument.  
  
 **Deaktivieren von Optimierungen**  
 **Ja (/ Od)** um Optimierungen zu deaktivieren, andernfalls **keine**. Standardmäßig ist der Wert **Ja (/ Od)** für **Debuggen** Konfigurationen und **keine** für **Version** Konfigurationen.  
  
 Die **/Od** Befehlszeilenargument für den HLSL-Compiler implizit gilt die **/Gfp** Befehlszeilenargument, aber die Ausgabe möglicherweise nicht identisch mit der Ausgabe, die erstellt wird, indem Sie beide übergeben der   **/od**  und **/Gfp** Befehlszeilenargumente explizit.  
  
 **Aktivieren Sie die Debuginformationen**  
 **Ja (/ Zi)** Debuginformationen; aktivieren, andernfalls **keine**. Standardmäßig ist der Wert **Ja (/ Zi)** für **Debuggen** Konfigurationen und **keine** für **Version** Konfigurationen.  
  
 **Shadertyp**  
 Gibt die Art des Shader. Verschiedene Arten von Shadern implementieren verschiedene Teile der Grafikpipeline. Bestimmte Arten von Shadern stehen nur in neueren Shader-Modelle (werbeeinblendungen angegeben werden, indem die **Shadermodell** Eigenschaft) – z. B. compute Shadern in Shadermodell 5 eingeführt wurden.  
  
 Diese Eigenschaft entspricht der **[Typ]** Teil der **/t [Typ] _ [Modell]** Befehlszeilenargument für den HLSL-Compiler. Die **Shader Modelle** Eigenschaft gibt an, die **[Modell]** Teil des Arguments.  
  
 **Shadermodell**  
 Gibt das Shadermodell an. Verschiedene Shader Modelle verfügen über andere Funktionen. Im Allgemeinen aktuelleren Shader Modelle bieten erweiterte Funktionen jedoch erfordern mehr moderner Grafikhardware Ausführen des Shader-Codes. Bestimmte Arten von Shader (werbeeinblendungen angegeben werden, indem der **Shader-Typ** Eigenschaft) stehen nur in neueren Shader-Modelle – z. B. compute Shadern in Shadermodell 5 eingeführt wurden.  
  
 Diese Eigenschaft entspricht der **[Modell]** Teil der **/t [Typ] _ [Modell]** Befehlszeilenargument für den HLSL-Compiler. Die **Shadertyp** Eigenschaft gibt an, die **[Typ]** Teil des Arguments.  
  
 **Präprozessor-Definitionen**  
 Fügt eine oder mehrere Präprozessorsymbol Definitionen der HLSL-Quellcodedatei zuweisen. Verwenden Sie Semikolons, um die Symboldefinitionen.  
  
 Diese Eigenschaft entspricht der **/d [Definitionen]** Befehlszeilenargument für den HLSL-Compiler.  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaftenseiten "HLSL"](../ide/hlsl-property-pages.md)   
 [Eigenschaftenseiten "HLSL": erweitert](../ide/hlsl-property-pages-advanced.md)   
 [Eigenschaftenseiten "HLSL": Ausgabedateien](../ide/hlsl-property-pages-output-files.md)