---
title: "Moduldefinitionsdateien (.Def)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".DEF-Dateien"
  - "DEF-Dateien"
  - "Moduldefinitionsdateien"
ms.assetid: 08c0bc28-c5d2-47aa-9624-7fc68bcaa4d8
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Moduldefinitionsdateien (.Def)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Moduldefinitionsdateien \(**.def**\) versorgen den Linker mit Informationen über Exporte, Attribute und andere Informationen im Hinblick auf das zu verknüpfende Programm.  Eine DEF\-Datei ist besonders beim Erstellen einer DLL von Nutzen.  Da anstelle von Moduldefinitionsanweisungen auch [Linkeroptionen](../../build/reference/linker-options.md) verwendet werden können, sind DEF\-Dateien im Allgemeinen nicht erforderlich.  Sie können auch [\_\_declspec\(dllexport\)](../../build/exporting-from-a-dll-using-declspec-dllexport.md) zur Angabe exportierter Funktionen verwenden.  
  
 Eine DEF\-Datei kann während der Linkerphase mit der Linkeroption [\/DEF \(Moduldefinitionsdatei angeben\)](../../build/reference/def-specify-module-definition-file.md) aufgerufen werden.  
  
 Falls Sie eine EXE\-Datei erstellen, die ohne Exporte auskommt, ist die Ausgabedatei bei Verwendung der DEF\-Datei umfangreicher und wird langsamer geladen.  
  
 Ein Beispiel finden Sie unter [Exportieren aus einer DLL mithilfe von DEF\-Dateien](../../build/exporting-from-a-dll-using-def-files.md).  
  
 Weitere Informationen finden Sie in den folgenden Abschnitten:  
  
-   [Regeln für Moduldefinitionsanweisungen](../../build/reference/rules-for-module-definition-statements.md)  
  
-   [EXPORTS](../../build/reference/exports.md)  
  
-   [HEAPSIZE](../../build/reference/heapsize.md)  
  
-   [LIBRARY](../../build/reference/library.md)  
  
-   [NAME](../../build/reference/name-c-cpp.md)  
  
-   [SECTIONS](../../build/reference/sections-c-cpp.md)  
  
-   [STACKSIZE](../../build/reference/stacksize.md)  
  
-   [STUB](../../build/reference/stub.md)  
  
-   [VERSION](../../build/reference/version-c-cpp.md)  
  
-   [Reservierte Wörter](../../build/reference/reserved-words.md)  
  
## Siehe auch  
 [Referenz zur C\/C\+\+\-Erstellung](../../build/reference/c-cpp-building-reference.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)   
 [Frequently Asked Questions on Building](assetId:///56a3bb8f-0181-4989-bab4-a07ba950ab08)