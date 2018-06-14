---
title: 'HLSL-Eigenschaftenseiten: Ausgabedateien | Microsoft-Dokumentation'
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
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33339195"
---
# <a name="hlsl-property-pages-output-files"></a>Eigenschaftenseiten "HLSL": "Ausgabedateien"
Verwenden Sie zum Konfigurieren der folgenden Eigenschaften des HLSL-Compilers („fxc.exe“) die Eigenschaft **Ausgabedateien**. Informationen über das Zugreifen auf die Eigenschaftenseite **Ausgabedateien** im Ordner „HLSL“ finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../ide/working-with-project-properties.md).  
  
## <a name="uielement-list"></a>UIElement-Liste  
 **Header-Variablenname**  
 Gibt den Namen eines Arrays an, das zum Codieren von HLSL-Objektcode verwendet wird. Das Array ist in einer Headerdatei enthalten, die vom HLSL-Compiler ausgegeben wird. Der Name der Headerdatei wird von der Eigenschaft **Headerdateiname** angegeben.  
  
 Diese Eigenschaft entspricht dem Befehlszeilenargument **/Vn[name]**.  
  
 **Headerdateiname**  
 Gibt den Namen der Headerdatei an, die vom HLSL-Compiler ausgegeben wird. Der Header enthält HLSL-Objektcode, der in ein Array codiert wird. Der Name des Arrays wird von der Eigenschaft **Header-Variablenname** angegeben.  
  
 Diese Eigenschaft entspricht dem Befehlszeilenargument **/Fh[name]**.  
  
 **Objektdateiname**  
 Gibt den Namen der Objektdatei an, die vom HLSL-Compiler ausgegeben wird. Der Wert ist standardmäßig **$(OutDir)%(Filename).cso**.  
  
 Diese Eigenschaft entspricht dem Befehlszeilenargument **/Fo[name]**.  
  
 **Assemblyausgabe**  
 Verwenden Sie **Nur die Assembly auflisten (/Fc)**, um nur Assemblysprachanweisungen auszugeben. Verwenden Sie **Assemblycode und -Hexadezimalwerte (/Fx)**, um Assemblysprachanweisungen und den entsprechenden Op-Code in hexadezimal auszugeben. Standardmäßig wird keine Auflistung ausgegeben.  
  
 **Assembler-Ausgabedatei**  
 Gibt den Namen der Assemblylistingdatei an, die vom HLSL-Compiler ausgegeben wird.  
  
 Diese Eigenschaft entspricht den Befehlszeilenargumenten **/Fc[name]** und **/Fx [name]**.  
  
## <a name="see-also"></a>Siehe auch  
 [HLSL Property Pages (HLSL-Eigenschaftenseiten)](../ide/hlsl-property-pages.md)   
 [HLSL Property Pages: General (HLSL-Eigenschaftenseiten: Allgemein)](../ide/hlsl-property-pages-general.md)   
 [Eigenschaftenseiten "HLSL": Erweitert](../ide/hlsl-property-pages-advanced.md)