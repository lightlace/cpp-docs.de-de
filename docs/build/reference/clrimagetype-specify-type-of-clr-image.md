---
title: / CLRIMAGETYPE (Angeben des CLR-Images) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /CLRIMAGETYPE
- VC.Project.VCLinkerTool.CLRImageType
dev_langs:
- C++
helpviewer_keywords:
- /CLRIMAGETYPE linker option
- -CLRIMAGETYPE linker option
ms.assetid: 04c60ee6-9dd7-4391-bc03-6926ad0fa116
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b5efb2e73e854591be7134753cec21a708fff3e5
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2018
ms.locfileid: "34705009"
---
# <a name="clrimagetype-specify-type-of-clr-image"></a>/CLRIMAGETYPE (Angeben des CLR-Bildtyps)

Legen Sie die CLR-imagetyps in das verknüpfte Bild.

## <a name="syntax"></a>Syntax

> **/ CLRIMAGETYPE:**{**IJW**|**REINER**|**SICHERE**|**SAFE32BITPREFERRED**}

## <a name="remarks"></a>Hinweise

Der Linker akzeptiert systemeigene Objekte und auch MSIL-Objekte, die mithilfe von kompiliert sind ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md). Die **/CLR: pure** und **/CLR: safe** Compileroptionen wurden in Visual Studio 2015 als veraltet markiert und werden in Visual Studio 2017 nicht unterstützt. Bei der Übergabe gemischter Objekte im selben Build entspricht die Überprüfbarkeit der erstellten Ausgabedatei standardmäßig der geringsten Überprüfbarkeitsstufe der Eingabemodule. Z. B., wenn Sie ein systemeigenes Image und ein Image im gemischten Modus übergeben (kompiliert mit **"/ CLR"**), das resultierende Image ein Image im gemischten Modus sein wird.

Sie können **/CLRIMAGETYPE** auf eine niedrigere Ebene Überprüfbarkeitsstufe angeben, wenn das gesuchte ist.

Weitere Informationen zum Bestimmen des CLR-Imagetyps einer Datei finden Sie unter [/CLRHEADER](../../build/reference/clrheader.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Erweitern Sie die **Konfigurationseigenschaften** Knoten.

1. Erweitern Sie die **Linker** Knoten.

1. Wählen Sie die **erweitert** Eigenschaftenseite.

1. Ändern der **CLR-Imagetyps** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRImageType%2A>.

## <a name="see-also"></a>Siehe auch

- [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)
- [Linkeroptionen](../../build/reference/linker-options.md)
