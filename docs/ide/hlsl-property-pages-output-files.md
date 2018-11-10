---
title: 'Eigenschaftenseiten "HLSL": "Ausgabedateien"'
ms.date: 11/04/2016
f1_keywords:
- VC.Project.FXCompilerTool.AssemblerOutput
- VC.Project.FXCompilerTool.ObjectFileOutput
- VC.Project.FXCompilerTool.HeaderFileOutput
- VC.Project.FXCompilerTool.VariableName
- VC.Project.FXCompilerTool.AssemblerOutputFile
ms.assetid: c5ba1e72-30de-43eb-a15a-5b0ae58e55c2
ms.openlocfilehash: 96736b58eed280a0b4e91b9cb47cb53dc2e91cd4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50513701"
---
# <a name="hlsl-property-pages-output-files"></a>Eigenschaftenseiten "HLSL": "Ausgabedateien"

Verwenden Sie zum Konfigurieren der folgenden Eigenschaften des HLSL-Compilers („fxc.exe“) die Eigenschaft **Ausgabedateien**. Informationen über das Zugreifen auf die Eigenschaftenseite **Ausgabedateien** im Ordner „HLSL“ finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../ide/working-with-project-properties.md).

## <a name="uielement-list"></a>UIElement-Liste

- **Header-Variablenname**

   Gibt den Namen eines Arrays an, das zum Codieren von HLSL-Objektcode verwendet wird. Das Array ist in einer Headerdatei enthalten, die vom HLSL-Compiler ausgegeben wird. Der Name der Headerdatei wird von der Eigenschaft **Headerdateiname** angegeben.

Diese Eigenschaft entspricht dem Befehlszeilenargument **/Vn[name]**.

- **Headerdateiname**

   Gibt den Namen der Headerdatei an, die vom HLSL-Compiler ausgegeben wird. Der Header enthält HLSL-Objektcode, der in ein Array codiert wird. Der Name des Arrays wird von der Eigenschaft **Header-Variablenname** angegeben.

Diese Eigenschaft entspricht dem Befehlszeilenargument **/Fh[name]**.

- **Objektdateiname**

   Gibt den Namen der Objektdatei an, die vom HLSL-Compiler ausgegeben wird. Der Wert ist standardmäßig **$(OutDir)%(Filename).cso**.

Diese Eigenschaft entspricht dem Befehlszeilenargument **/Fo[name]**.

- **Assemblyausgabe**

   Verwenden Sie **Nur die Assembly auflisten (/Fc)**, um nur Assemblysprachanweisungen auszugeben. Verwenden Sie **Assemblycode und -Hexadezimalwerte (/Fx)**, um Assemblysprachanweisungen und den entsprechenden Op-Code in hexadezimal auszugeben. Standardmäßig wird keine Auflistung ausgegeben.

- **Assembler-Ausgabedatei**

   Gibt den Namen der Assemblylistingdatei an, die vom HLSL-Compiler ausgegeben wird.

   Diese Eigenschaft entspricht den Befehlszeilenargumenten **/Fc[name]** und **/Fx [name]**.

## <a name="see-also"></a>Siehe auch

[Eigenschaftenseiten "HLSL"](../ide/hlsl-property-pages.md)<br>
[Eigenschaftenseiten "HLSL": Allgemein](../ide/hlsl-property-pages-general.md)<br>
[Eigenschaftenseiten "HLSL": Erweitert](../ide/hlsl-property-pages-advanced.md)