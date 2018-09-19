---
title: -Fx (eingefügten Code zusammenführen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.ExpandAttributedSource
- /Fx
- VC.Project.VCCLCompilerTool.ExpandAttributedSource
dev_langs:
- C++
helpviewer_keywords:
- Fx compiler option [C++]
- -Fx compiler option [C++]
- injected code
- merging injected code
- /Fx compiler option [C++]
ms.assetid: 14f0e301-3bab-45a3-bbdf-e7ce66f20560
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0bd95ea00a63f28f04874f873cf0a4e991fac0fc
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45710520"
---
# <a name="fx-merge-injected-code"></a>/Fx (Eingefügten Code zusammenführen)

Erzeugt eine Kopie jeder Quelldatei mit injiziertem Code, der in die Quelle eingefügt ist.

## <a name="syntax"></a>Syntax

```
/Fx
```

## <a name="remarks"></a>Hinweise

Damit eine zusammengeführte Quelldatei von einer unveränderten Quelldatei unterschieden werden kann, fügt **/Fx** die Erweiterung „.mrg“ zwischen dem Dateinamen und der Dateierweiterung ein. Eine Datei mit dem Namen „MeinCode.cpp“, die attribuierten Code enthält und mit **/Fx** erstellt wird, erzeugt eine Datei mit dem Namen „MyCode.mrg.cpp“, die den folgenden Code enthält:

```
//+++ Start Injected Code
[no_injected_text(true)];      // Suppress injected text, it has
                               // already been injected
#pragma warning(disable: 4543) // Suppress warnings about skipping
                               // injected text
#pragma warning(disable: 4199) // Suppress warnings from attribute
                               // providers
//--- End Injected Code
```

In einer MRG-Datei wird Code, der aufgrund eines Attributs injiziert wurde, wie folgt abgetrennt:

```
//+++ Start Injected Code
...
//--- End Injected Code
```

Das [no_injected_text](../../windows/no-injected-text.md) -Attribut wird in eine MRG-Datei eingebettet, was die Kompilierung der MRG-Datei ohne erneute Injizierung von Text ermöglicht.

Es sollte Ihnen bewusst sein, dass die MRG-Quelldatei als Darstellung des vom Compiler injizierten Quellcodes beabsichtigt ist. Die MRG-Datei lässt sich möglicherweise nicht genau wie die ursprüngliche Quelldatei kompilieren oder ausführen.

Makros werden in der MRG-Datei nicht erweitert.

Wenn Ihr Programm eine Headerdatei umfasst, die injizierten Code verwendet, erstellt **/Fx** eine „.mrg.h“-Datei für den betreffenden header. **/Fx** führt keine Includedateien zusammen, die keinen injizierten Code verwenden.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken  Sie auf die Eigenschaftenseite **Ausgabedateien** .

1. Ändern Sie die **Expand Attributed Source** -Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ExpandAttributedSource%2A>.

## <a name="see-also"></a>Siehe auch

[Ausgabedatei (/ F) Optionen](../../build/reference/output-file-f-options.md)
[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)