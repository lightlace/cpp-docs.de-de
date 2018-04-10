---
title: . OBJ-Dateien als Linkereingabe | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- linker [C++], OBJ files as input
- object files, linker output
- OMF object files
- LINK tool [C++], .obj files
- COFF files
- OBJ files as linker input
- .obj files as linker input
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9a2896822e97bdbb5ffdf8f869e67beadc1675b7
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="obj-files-as-linker-input"></a>.OBJ-Dateien als Linkereingabe

Der Linkertool (LINK. EXE-Datei) akzeptiert OBJ-Dateien, die im Common Object File Format (COFF).

## <a name="remarks"></a>Hinweise

Microsoft bietet eine vollständige Beschreibung des Dateiformats allgemeine Objekt. Weitere Informationen finden Sie unter [PE Format](https://msdn.microsoft.com/library/windows/desktop/ms680547).

## <a name="unicode-support"></a>Unterstützung für Unicode

Ab Visual Studio 2005 werden unterstützt Microsoft Visual C++-Compiler Unicode-Zeichen in Bezeichnern gemäß der Definition von ISO/IEC C- und C++-Standards. Ältere Versionen des Compilers unterstützt nur ASCII-Zeichen in Bezeichnern. Verwenden zur Unterstützung von Unicode in die Namen der Funktionen, Klassen und statische Variablen Compiler und Linker Unicode-UTF-8-Codierung für COFF-Symbole in der OBJ-Dateien. UTF-8-Codierung ist kompatibel mit der ASCII-Codierung, die von früheren Versionen von Visual Studio verwendet.

Weitere Informationen zu den Compiler und Linker finden Sie unter [Unicode-Unterstützung im Compiler und Linker](../../build/reference/unicode-support-in-the-compiler-and-linker.md). Weitere Informationen zu den Unicode-Standard, finden Sie unter der [Unicode](http://go.microsoft.com/fwlink/p/?linkid=37123) Organisation.

## <a name="see-also"></a>Siehe auch

[LINK-Eingabedateien](../../build/reference/link-input-files.md)  
[Linkeroptionen](../../build/reference/linker-options.md)  
[Unterstützung für Unicode](../../text/support-for-unicode.md)  
[Unicode-Unterstützung im Compiler und Linker](../../build/reference/unicode-support-in-the-compiler-and-linker.md)  
[Unicode-standard](http://go.microsoft.com/fwlink/p/?linkid=37123)  
[PE-Format](https://msdn.microsoft.com/library/windows/desktop/ms680547)  
