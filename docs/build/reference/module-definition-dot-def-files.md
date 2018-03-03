---
title: Moduldefinitionsdateien (. "Def")-Dateien | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- def files
- module definition files
- .def files
ms.assetid: 08c0bc28-c5d2-47aa-9624-7fc68bcaa4d8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 49f5eb5b75bad22b59cb4fbb98554bbfd44d13b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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