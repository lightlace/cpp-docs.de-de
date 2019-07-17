---
title: /DEPENDENTS
ms.date: 07/15/2019
f1_keywords:
- /dependents
helpviewer_keywords:
- -DEPENDENTS dumpbin option
- /DEPENDENTS dumpbin option
- DEPENDENTS dumpbin option
ms.assetid: 9b31da2a-75ac-4bbf-a3f1-adf8b0ecbbb4
ms.openlocfilehash: 88f0062a6bbca3f9199a12f739c2ade5f9d912cd
ms.sourcegitcommit: 7f5b29e24e1be9b5985044a030977485fea0b50c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2019
ms.locfileid: "68299749"
---
# <a name="dependents"></a>/DEPENDENTS

Sichert die Namen der DLLs, von denen das Image Funktionen importiert. Sie können die Liste verwenden, um zu bestimmen, welche DLLs mit der APP verteilt werden sollen, oder den Namen einer fehlenden Abhängigkeit zu suchen.

## <a name="syntax"></a>Syntax

> **/DEPENDENTS**

Diese Option gilt für alle ausführbaren Dateien, die in der Befehlszeile angegeben sind. Es übernimmt keine Argumente.

## <a name="remarks"></a>Hinweise

Mit der **/Dependents** -Option werden die Namen der DLLs, aus denen das Bildfunktionen importiert, der Ausgabe hinzugefügt. Mit dieser Option werden die Namen der importierten Funktionen nicht gesichert. Verwenden Sie die Option [/Imports](imports-dumpbin.md) , um die Namen der importierten Funktionen anzuzeigen.

Für Dateien, die mit der [/GL](gl-whole-program-optimization.md)-Compileroption erstellt wurden, kann nur die Option [/HEADERS](headers.md) DUMPBIN verwendet werden.

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt die dumpbin-Ausgabe der **/Dependents** -Option für die ausführbare Client [Datei, die in Exemplarische Vorgehensweise erstellt wurde: Erstellen und verwenden Sie eine eigene Dynamic Link](../walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)Library:

```cmd
C:\Users\username\Source\Repos\MathClient\Debug>dumpbin /DEPENDENTS MathClient.exe
Microsoft (R) COFF/PE Dumper Version 14.16.27032.1
Copyright (C) Microsoft Corporation.  All rights reserved.


Dump of file MathClient1322.exe

File Type: EXECUTABLE IMAGE

  Image has the following dependencies:

    MathLibrary.dll
    MSVCP140D.dll
    VCRUNTIME140D.dll
    ucrtbased.dll
    KERNEL32.dll

  Summary

        1000 .00cfg
        1000 .data
        2000 .idata
        1000 .msvcjmc
        3000 .rdata
        1000 .reloc
        1000 .rsrc
        8000 .text
       10000 .textbss
```

## <a name="see-also"></a>Siehe auch

[DUMPBIN-Optionen](dumpbin-options.md)
