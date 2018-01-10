---
title: "Beschränkungen für das verzögerte Laden von DLLs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- constraints [C++], delayed loading of DLLs
- delayed loading of DLLs, constraints
- DLLs [C++], constraints
ms.assetid: 0097ff65-550f-4a4e-8ac3-39bf6404f926
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cd3f641a3ac03705ff7f3765d995d5c40bccda7d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="constraints-of-delay-loading-dlls"></a>Beschränkungen für das verzögerte Laden von DLLs
Es gibt Einschränkungen hinsichtlich des verzögerten Ladens von Importen.  
  
-   Datenimporte können nicht unterstützt werden. Eine Problemumgehung besteht darin, den Datenimport explizit über `LoadLibrary` (oder `GetModuleHandle`, wenn Sie wissen, dass die Hilfsfunktion für das verzögerte Laden die DLL geladen hat) und `GetProcAddress` selbst zu handhaben.  
  
-   Ein verzögertes Laden von Kernel32.dll wird nicht unterstützt. Diese DLL ist erforderlich, damit die Routinen der Hilfsfunktion für das verzögerte Laden das verzögerte Laden durchführen können.  
  
-   [Binden von](../../build/reference/binding-imports.md) von Einstiegspunkten, die weitergeleitet werden, wird nicht unterstützt.  
  
-   Das verzögerte Laden einer DLL führt möglicherweise nicht zum selben Verwalten des Prozesses, wenn pro Prozess stattfindende Initialisierungen vorhanden sind, die am Einstiegspunkt der verzögert geladenen DLL stattfinden. Anderen Fällen gehört der statische TLS (Thread local Storage) mit deklarierten [__declspec(thread)](../../cpp/thread.md), die nicht behandelt, wenn die DLL über `LoadLibrary`. Der dynamische TLS ist über `TlsAlloc`, `TlsFree`, `TlsGetValue` und `TlsSetValue` immer noch zur Verwendung in statischen oder verzögert geladenen DLLs verfügbar.  
  
-   Statische (globale) Funktionszeiger sollten für importierte Funktionen erneut initialisiert werden, nach die Funktion erstmals aufgerufen wurde. Der Grund ist, dass der Funktionszeiger bei der ersten Verwendung auf den Thunk zeigt.  
  
-   Derzeit gibt es keine Möglichkeit, das Laden nur bestimmter Verfahren aus einer DLL bei Verwendung des normalen Importmechanismus zu verzögern.  
  
-   Benutzerdefinierte Aufrufkonventionen (wie die Verwendung von Bedingungscodes in x86-Architekturen) werden nicht unterstützt. Außerdem werden die Gleitkommaregister auf keiner Plattform gespeichert. Wenn Ihre benutzerdefinierte Hilfsroutine oder Hookroutinen Gleitkommatypen verwenden, müssen sie den Gleitkommazustand auf Computern mit Registeraufrufkonventionen mit Gleitkommaparametern vollständig speichern und wiederherstellen. Seien Sie vorsichtig mit dem verzögerten Laden der CRT-DLL, wenn Sie CRT-Funktionen aufrufen, die Gleitkommaparameter in einem numerischen Datenprozessorstapel in der Hilfsfunktion annehmen.  
  
## <a name="see-also"></a>Siehe auch  
 [Linkerunterstützung für verzögertes Laden von DLLs](../../build/reference/linker-support-for-delay-loaded-dlls.md)   
 [LoadLibrary-Funktion](http://msdn.microsoft.com/library/windows/desktop/ms684175.aspx)   
 [GetModuleHandle-Funktion](http://msdn.microsoft.com/library/windows/desktop/ms683199.aspx)   
 [GetProcAddress-Funktion](http://msdn.microsoft.com/library/windows/desktop/ms683212.aspx)   
 [TlsAlloc-Funktion](http://msdn.microsoft.com/library/windows/desktop/ms686801.aspx)   
 [TlsFree-Funktion](http://msdn.microsoft.com/library/windows/desktop/ms686804.aspx)   
 [TlsGetValue-Funktion](http://msdn.microsoft.com/library/windows/desktop/ms686812.aspx)   
 [TlsSetValue-Funktion](http://msdn.microsoft.com/library/windows/desktop/ms686818.aspx)