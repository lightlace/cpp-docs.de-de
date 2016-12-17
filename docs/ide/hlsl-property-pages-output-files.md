---
title: "Eigenschaftenseiten &quot;HLSL&quot;: &quot;Ausgabedateien&quot;"
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
  - "VC.Project.FXCompilerTool.AssemblerOutput"
  - "VC.Project.FXCompilerTool.ObjectFileOutput"
  - "VC.Project.FXCompilerTool.HeaderFileOutput"
  - "VC.Project.FXCompilerTool.VariableName"
  - "VC.Project.FXCompilerTool.AssemblerOutputFile"
dev_langs: 
  - "C++"
ms.assetid: c5ba1e72-30de-43eb-a15a-5b0ae58e55c2
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "brpeek"
manager: "ghogen"
---
# Eigenschaftenseiten &quot;HLSL&quot;: &quot;Ausgabedateien&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Um die folgenden Eigenschaften des HLSL\-Compilers \(fxc.exe\) konfigurieren, verwenden Sie die Eigenschaft **Ausgabedateien**.  Informationen darüber, wie Sie auf die Eigenschaftenseite **Ausgabedateien** im HLSL\-Ordner, finden Sie unter [Gewusst wie: Festlegen von Projekteigenschaften mit Eigenschaftenseiten](../misc/how-to-specify-project-properties-with-property-pages.md) zugreift.  
  
## UIElement-Liste  
 **Header\-Variablenname**  
 Gibt den Namen eines Arrays an, das verwendeter codierten HLSL\-Objektcode ist.  Das Array wird in einer Headerdatei enthalten, die von den HLSL\-Compiler ausgegeben wird.  Der Name der Headerdatei wird durch die Eigenschaft **Header\-Dateiname** angegeben.  
  
 Diese Eigenschaft entspricht dem **\/Vn\[name\]** Befehlszeilenargument.  
  
 **Header\-Dateiname**  
 Gibt den Namen der Headerdatei an, die vom HLSL\-Compiler ausgegeben wird.  Der Header enthält HLSL\-Objektcode, der in ein Array codiert ist.  Der Name des Arrays wird durch die Eigenschaft **Header\-Variablenname** angegeben.  
  
 Diese Eigenschaft entspricht dem **\/Fh\[name\]** Befehlszeilenargument.  
  
 **Objektdateiname**  
 Gibt den Namen der Objektdatei an, die vom HLSL\-Compiler ausgegeben wird.  Standardmäßig ist der Wert **$\(OutDir\)%\(Filename\).cso**.  
  
 Diese Eigenschaft entspricht dem **\/Fo\[name\]** Befehlszeilenargument.  
  
 **Assemblyausgabe**  
 **Nur die Assembly auflisten \(\/Fc\)**, dem aktuell von Assemblysprachanweisungen auszugeben.  **Assemblycode und \-Hexadezimalwerte \(\/Fx\)**, von Assemblysprachanweisungen und der entsprechenden OPCode im Hexadezimalformat auszugeben.  Standardmäßig werden keine Listen ausgegeben.  
  
 **Assembler\-Ausgabedatei**  
 Gibt den Namen der Assemblylistendatei an, die vom HLSL\-Compiler ausgegeben wird.  
  
 Diese Eigenschaft entspricht den **\/Fc\[name\]** und **\/Fx \[name\]** Befehlszeilenargumente.  
  
## Siehe auch  
 [Eigenschaftenseiten "HLSL"](../ide/hlsl-property-pages.md)   
 [Eigenschaftenseiten "HLSL": "Allgemein"](../ide/hlsl-property-pages-general.md)   
 [Eigenschaftenseiten "HLSL": "Erweitert"](../ide/hlsl-property-pages-advanced.md)