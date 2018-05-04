---
title: Moduldefinitionsdateien (. "Def")-Dateien | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- def files
- module definition files
- .def files
ms.assetid: 08c0bc28-c5d2-47aa-9624-7fc68bcaa4d8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 57bad3a63e910918b6a22b6263f0df3faca0dcd1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="module-definition-def-files"></a>Moduldefinitionsdateien (.Def)
Moduldefinitionsdateien (.def) Geben Sie den Linker mit Informationen über Exporte, Attribute und andere Informationen über das Programm zu verknüpfenden. Eine DEF-Datei ist besonders hilfreich, wenn Sie eine DLL erstellen. Da sind [Optionen des Linkers](../../build/reference/linker-options.md) verwendet werden können statt moduldefinitionsanweisungen, DEF-Dateien sind im Allgemeinen nicht erforderlich. Sie können auch [__declspec(dllexport)](../../build/exporting-from-a-dll-using-declspec-dllexport.md) als eine Möglichkeit, geben Sie die exportierten Funktionen.  
  
 Sie können eine DEF-Datei aufrufen, während der Linkerphase mit der [/DEF (Moduldefinitionsdatei festlegen)](../../build/reference/def-specify-module-definition-file.md) (Linkeroption).  
  
 Wenn Sie eine .exe-Datei, die über keine Exportdaten verfügt erstellen, wird die über eine DEF-Datei Ihrer langsamer und größer Laden der Datei Ausgabe stellen.  
  
 Ein Beispiel finden Sie unter [exportieren aus einer DLL mithilfe von DEF-Dateien](../../build/exporting-from-a-dll-using-def-files.md).  
  
 Finden Sie in den folgenden Abschnitten Weitere Informationen:  
  
-   [Regeln für Moduldefinitionsanweisungen](../../build/reference/rules-for-module-definition-statements.md)  
  
-   [EXPORTE](../../build/reference/exports.md)  
  
-   [HEAPSIZE](../../build/reference/heapsize.md)  
  
-   [BIBLIOTHEK](../../build/reference/library.md)  
  
-   [NAME](../../build/reference/name-c-cpp.md)  
  
-   [ABSCHNITTE](../../build/reference/sections-c-cpp.md)  
  
-   [STACKSIZE](../../build/reference/stacksize.md)  
  
-   [STUB](../../build/reference/stub.md)  
  
-   [VERSION](../../build/reference/version-c-cpp.md)  
  
-   [Reservierte Wörter](../../build/reference/reserved-words.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Referenz zur C/C++-Erstellung](../../build/reference/c-cpp-building-reference.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)  