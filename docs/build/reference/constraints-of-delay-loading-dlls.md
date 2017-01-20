---
title: "Beschr&#228;nkungen f&#252;r das verz&#246;gerte Laden von DLLs"
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
  - "Einschränkungen [C++], Verzögertes Laden von DLLs"
  - "Verzögertes Laden von DLLs, Einschränkungen"
  - "DLLs [C++], Einschränkungen"
ms.assetid: 0097ff65-550f-4a4e-8ac3-39bf6404f926
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Beschr&#228;nkungen f&#252;r das verz&#246;gerte Laden von DLLs
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Es gibt Einschränkungen hinsichtlich des verzögerten Ladens von Importen.  
  
-   Datenimporte können nicht unterstützt werden.  Eine Problemumgehung besteht darin, den Datenimport explizit über `LoadLibrary` \(oder `GetModuleHandle`, wenn Sie wissen, dass die Hilfsfunktion für das verzögerte Laden die DLL geladen hat\) und `GetProcAddress` selbst zu handhaben.  
  
-   Ein verzögertes Laden von Kernel32.dll wird nicht unterstützt.  Diese DLL ist erforderlich, damit die Routinen der Hilfsfunktion für das verzögerte Laden das verzögerte Laden durchführen können.  
  
-   Das [Binden](../../build/reference/binding-imports.md) von Einstiegspunkten, die weitergeleitet werden, wird nicht unterstützt.  
  
-   Das verzögerte Laden einer DLL führt möglicherweise nicht zum selben Verwalten des Prozesses, wenn pro Prozess stattfindende Initialisierungen vorhanden sind, die am Einstiegspunkt der verzögert geladenen DLL stattfinden.  Zu anderen Fällen gehört der statische TLS \(Thread Local Storage\), der über [\_\_declspec\(thread\)](../../cpp/thread.md) deklariert wird und der nicht verarbeitet wird, wenn die DLL über `LoadLibrary` geladen wird.  Der dynamische TLS ist über `TlsAlloc`, `TlsFree`, `TlsGetValue` und `TlsSetValue` immer noch zur Verwendung in statischen oder verzögert geladenen DLLs verfügbar.  
  
-   Statische \(globale\) Funktionszeiger sollten für importierte Funktionen erneut initialisiert werden, nach die Funktion erstmals aufgerufen wurde.  Der Grund ist, dass der Funktionszeiger bei der ersten Verwendung auf den Thunk zeigt.  
  
-   Derzeit gibt es keine Möglichkeit, das Laden nur bestimmter Verfahren aus einer DLL bei Verwendung des normalen Importmechanismus zu verzögern.  
  
-   Benutzerdefinierte Aufrufkonventionen \(wie die Verwendung von Bedingungscodes in x86\-Architekturen\) werden nicht unterstützt.  Außerdem werden die Gleitkommaregister auf keiner Plattform gespeichert.  Wenn Ihre benutzerdefinierte Hilfsroutine oder Hookroutinen Gleitkommatypen verwenden, müssen sie den Gleitkommazustand auf Computern mit Registeraufrufkonventionen mit Gleitkommaparametern vollständig speichern und wiederherstellen.  Seien Sie vorsichtig mit dem verzögerten Laden der CRT\-DLL, wenn Sie CRT\-Funktionen aufrufen, die Gleitkommaparameter in einem numerischen Datenprozessorstapel in der Hilfsfunktion annehmen.  
  
## Siehe auch  
 [Linkerunterstützung für verzögertes Laden von DLLs](../../build/reference/linker-support-for-delay-loaded-dlls.md)   
 [LoadLibrary\-Funktion](http://msdn.microsoft.com/library/windows/desktop/ms684175.aspx)   
 [GetModuleHandle\-Funktion](http://msdn.microsoft.com/library/windows/desktop/ms683199.aspx)   
 [GetProcAddress\-Funktion](http://msdn.microsoft.com/library/windows/desktop/ms683212.aspx)   
 [TlsAlloc\-Funktion](http://msdn.microsoft.com/library/windows/desktop/ms686801.aspx)   
 [TlsFree\-Funktion](http://msdn.microsoft.com/library/windows/desktop/ms686804.aspx)   
 [TlsGetValue\-Funktion](http://msdn.microsoft.com/library/windows/desktop/ms686812.aspx)   
 [TlsSetValue\-Funktion](http://msdn.microsoft.com/library/windows/desktop/ms686818.aspx)