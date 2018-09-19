---
title: / FA, / FA (Listendatei) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.AssemblerListingLocation
- VC.Project.VCCLCompilerTool.ConfigureASMListing
- VC.Project.VCCLWCECompilerTool.AssemblerOutput
- VC.Project.VCCLCompilerTool.AssemblerListingLocation
- /fa
- VC.Project.VCCLCompilerTool.AssemblerOutput
- VC.Project.VCCLCompilerTool.UseUnicodeForAssemblerListing
dev_langs:
- C++
helpviewer_keywords:
- FA compiler option [C++]
- /FA compiler option [C++]
- -FA compiler option [C++]
- listing file type
- assembly-only listing
ms.assetid: c7507d0e-c69d-44f9-b8e2-d2c398697402
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 03b2f4e746632cc91b652ca76587ddad18afd165
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717963"
---
# <a name="fa-fa-listing-file"></a>/FA, /Fa (Listendatei)

Erstellt eine Listendatei, die Assemblercode enthält.

## <a name="syntax"></a>Syntax

> **/ FA**[**c**\][**s**\][**u**] **/FA**_Pfadname_

## <a name="remarks"></a>Hinweise

Die **/FA** -Compileroption generiert eine Assembler-Listendatei für jede Übersetzungseinheit in der Kompilierung, die in der Regel eine C- oder C++-Quelldatei entspricht. Standardmäßig ist nur Assembler in der Listendatei enthalten, die als ANSI codiert ist. Der optionale **c**, **s**, und **u** Argumente **/FA** Steuerelement gibt an, ob Code bzw. dem Quellcode werden zusammen mit den Assembler Auflisten von, und gibt an, ob die Auflistung als UTF-8 codiert ist.

Standardmäßig jede Listendatei Ruft den gleichen Basisnamen wie die Quelldatei, und verfügt über eine ASM-Erweiterung. Wenn Computer Code befindet sich unter Verwendung der **c** Listendatei-Option hat die COD-Erweiterung. Sie können ändern, den Namen und die Erweiterung der Listendatei und das Verzeichnis, in dem es mithilfe erstellt wird, der **/FA** Option.

### <a name="fa-arguments"></a>/ FA-Argumente

Keine<br/>
Nur die Assembler-Sprache ist in der Auflistung enthalten.

**c**<br/>
Dies ist optional. Enthält Computercode in der Auflistung.

**s**<br/>
Dies ist optional. Enthält Quellcode in der Auflistung.

**n**<br/>
Dies ist optional. Codiert im UTF-8-Format Listendatei und umfasst eine Bytereihenfolge. Standardmäßig wird die Datei als ANSI codiert. Verwenden `u` um eine Listendatei zu erstellen, die auf alle Systeme ordnungsgemäß anzeigt, oder wenn Sie Unicode verwenden Quellcodedateien als Eingabe für den Compiler.

Wenn beide **s** und **u** angegeben werden, und wenn eine Quellcodedatei verwendet eine Unicode-Codierung außer UTF-8, und klicken Sie dann auf die Codezeilen in die ASM-Datei eventuell nicht korrekt angezeigt.

### <a name="fa-argument"></a>/ FA-argument

Keine<br/>
Eine *Quelle*ASM-Datei wird für jede Quellcodedatei in der Kompilierung erstellt.

*filename*<br/>
Eine Listendatei mit dem Namen *Filename*.asm wird im aktuellen Verzeichnis abgelegt. Dies ist nur gültig, beim Kompilieren einer einzelnen Quellcodedatei.

*filename.Extension*<br/>
Eine Listendatei mit dem Namen *filename.extension* befindet sich im aktuellen Verzeichnis. Dies ist nur gültig, beim Kompilieren einer einzelnen Quellcodedatei.

*Verzeichnis*__\\__<br/>
Eine *Source_file*ASM-Datei erstellt und platziert Sie in der angegebenen *Directory* für jede Quellcodedatei in der Kompilierung. Beachten Sie den erforderlichen nachgestellten umgekehrten Schrägstrich ein. Nur die Pfade auf dem aktuellen Datenträger sind zulässig.

*Directory*__\\__*Dateiname*<br/>
Eine Listendatei mit dem Namen *Filename*.asm befindet sich in der angegebenen *Directory*. Dies ist nur gültig, beim Kompilieren einer einzelnen Quellcodedatei.

*Directory*__\\__*filename.extension*<br/>
Eine Listendatei mit dem Namen *filename.extension* befindet sich in der angegebenen *Directory*. Dies ist nur gültig, beim Kompilieren einer einzelnen Quellcodedatei.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

2. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Ausgabedateien** Eigenschaftenseite.

3. Ändern der **Assemblyausgabe** -Eigenschaft zum Festlegen der **/FAc** und **/FAS** Optionen für die Assembler-, Computer und Quellcode. Ändern der **verwenden Unicode für Assembler auflisten** -Eigenschaft zum Festlegen der **/FAu** Option für die ANSI-Codepage oder UTF-8-Ausgabe. Ändern der **ASM-Listenspeicherort** Festlegen der **/FA** Option für die Auflistung von Dateinamen und Speicherort.

Das Festlegen sowohl **Assemblyausgabe** und **verwenden Unicode für Assembler auflisten** Eigenschaften können dazu führen, dass [Command-Line-Warnung D9025](../../error-messages/tool-errors/command-line-warning-d9025.md). Verwenden Sie diese Optionen in der IDE zu kombinieren, die **zusätzliche Optionen** Feld der **über die Befehlszeile** Eigenschaftenseite stattdessen.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AssemblerListingLocation%2A> oder <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AssemblerOutput%2A>. An **/FAu**, finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="example"></a>Beispiel

Die folgende Befehlszeile produziert eine kombinierte mit Quellcode und Computer-Codelisting HELLO.cod:

```cmd
CL /FAcs HELLO.CPP
```

## <a name="see-also"></a>Siehe auch

[Ausgabedatei (/ F) Optionen](../../build/reference/output-file-f-options.md)
[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[Festlegen des Pfadnamens](../../build/reference/specifying-the-pathname.md)