---
title: Laden aller Importe für eine verzögert geladene DLL | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- __HrLoadAllImportsForDll linker option
ms.assetid: 975fcd97-1a56-4a16-9698-e1a249d2d592
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f054479a6681ba6de57690295fe3ce9f6c83696
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="loading-all-imports-for-a-delay-loaded-dll"></a>Laden aller Importe für eine verzögert geladene DLL
Die **__HrLoadAllImportsForDll** -Funktion, die in delayhlp.cpp definiert ist, weist den Linker an, alle Importe aus einer DLL zu laden, die mit angegeben wurde die [/DELAYLOAD](../../build/reference/delayload-delay-load-import.md) (Linkeroption).  
  
 Laden aller Importe, können Sie Fehlerbehandlung, die an einer Stelle im Code und nicht den eigentlichen aufrufen, um die Importe Ausnahmebehandlung zu verwenden. Es verhindert auch eine Situation, in denen Ihre Anwendung teilweise durch einen Prozess aufgrund der Hilfscode nicht geladen werden einen Import fehlschlägt.  
  
 Aufrufen von **__HrLoadAllImportsForDll** ändert sich nicht auf das Verhalten von Hooks und Fehler behandeln; finden Sie unter [Fehlerbehandlung und Benachrichtigung](../../build/reference/error-handling-and-notification.md) für Weitere Informationen.  
  
 Das an den Namen der DLL **__HrLoadAllImportsForDll** im Vergleich zu den Namen in der DLL-Datei selbst gespeichert und Groß-/Kleinschreibung beachtet.  
  
 Im folgende Beispiel wird gezeigt, wie Aufrufen **__HrLoadAllImportsForDll**:  
  
```  
if (FAILED(__HrLoadAllImportsForDll("delay1.dll"))) {  
   printf ( "failed on snap load, exiting\n" );  
   exit(2);  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Linkerunterstützung für verzögertes Laden von DLLs](../../build/reference/linker-support-for-delay-loaded-dlls.md)