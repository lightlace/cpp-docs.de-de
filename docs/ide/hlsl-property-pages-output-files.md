---
title: 'Eigenschaftenseiten "HLSL": Ausgabedateien | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.FXCompilerTool.AssemblerOutput
- VC.Project.FXCompilerTool.ObjectFileOutput
- VC.Project.FXCompilerTool.HeaderFileOutput
- VC.Project.FXCompilerTool.VariableName
- VC.Project.FXCompilerTool.AssemblerOutputFile
dev_langs:
- C++
ms.assetid: c5ba1e72-30de-43eb-a15a-5b0ae58e55c2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4fd1dc3ba92201567f24aa84ff8dddcd96798b38
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="hlsl-property-pages-output-files"></a>Eigenschaftenseiten "HLSL": "Ausgabedateien"
Um die folgenden Eigenschaften des HLSL-Compilers (fxc.exe) zu konfigurieren, verwenden die **Ausgabedateien** Eigenschaft. Informationen über den Zugriff auf die **Ausgabedateien** Eigenschaftenseite im Ordner "HLSL" finden Sie unter [arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md).  
  
## <a name="uielement-list"></a>UIElement-Liste  
 **Header-Variablenname**  
 Gibt den Namen eines Arrays, die zum codierten HLSL-Objektcode verwendet wird. Das Array ist in einer Headerdatei, die Ausgabe wird vom Compiler "HLSL" enthalten. Der Name der Headerdatei wird gemäß der **Headerdateinamen** Eigenschaft.  
  
 Diese Eigenschaft entspricht der **/Vn [Name]** Befehlszeilenargument.  
  
 **Headerdateinamen**  
 Gibt den Namen der Headerdatei, die vom Compiler "HLSL" ausgegeben wird. Der Header enthält HLSL-Objektcode, die in ein Array codiert ist. Der Name des Arrays wird angegeben, indem die **Header Variablenname** Eigenschaft.  
  
 Diese Eigenschaft entspricht der **/Fh [Name]** Befehlszeilenargument.  
  
 **Name der Objektdatei**  
 Gibt den Namen der Objektdatei, die vom Compiler "HLSL" ausgegeben wird. Standardmäßig ist der Wert **$(OutDir) % (Dateiname) .cso**.  
  
 Diese Eigenschaft entspricht der **/Fo [Name]** Befehlszeilenargument.  
  
 **Assemblyausgabe**  
 **Nur die Assembly auflisten (/ Fc)** nur Assemblysprache-Anweisungen ausgegeben. **Assemblycode und Hex (/ Fx)** Assemblysprache-Anweisungen und den entsprechenden Op-Code im Hexadezimalformat ausgegeben. Standardmäßig ist kein Angebot Ausgabe.  
  
 **Assembler-Ausgabedatei**  
 Gibt den Namen der Assemblylistendatei, die vom Compiler "HLSL" ausgegeben wird.  
  
 Diese Eigenschaft entspricht der **/FC [Name]** und **/FX [Name]** Befehlszeilenargumente.  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaftenseiten "HLSL"](../ide/hlsl-property-pages.md)   
 [Eigenschaftenseiten "HLSL": Allgemein](../ide/hlsl-property-pages-general.md)   
 [Eigenschaftenseiten "HLSL": Erweitert](../ide/hlsl-property-pages-advanced.md)