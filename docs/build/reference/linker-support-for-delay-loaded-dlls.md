---
title: "Linkerunterst&#252;tzung f&#252;r verz&#246;gertes Laden von DLLs | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Verzögertes Laden von DLLs, Linkerunterstützung"
ms.assetid: b2d7e449-2809-42b1-9c90-2c0ca5e31a14
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Linkerunterst&#252;tzung f&#252;r verz&#246;gertes Laden von DLLs
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verzögertes Laden von DLLs wird nun vom Linker von Visual C\+\+ unterstützt.  Daher müssen Sie nicht mehr die [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)]\-Funktionen **LoadLibrary** und **GetProcAddress** verwenden, um das verzögerte Laden von DLLs zu implementieren.  
  
 Vor Visual C\+\+ 6.0 konnte eine DLL zur Laufzeit ausschließlich durch Verwenden von **LoadLibrary** und **GetProcAddress** geladen werden. Die DLL wurde dann vom Betriebssystem geladen, wenn die ausführbare Datei oder die DLL, von der sie verwendet wurde, geladen wurde.  
  
 Beginnend mit Visual C\+\+ 6.0 werden vom Linker beim statischen Verknüpfen mit einer DLL Optionen bereitgestellt, um das Laden der DLL zu verzögern, bis das Programm eine Funktion in dieser DLL aufruft.  
  
 Eine DLL kann von einer Anwendung verzögert geladen werden, indem die Linkeroption [\/DELAYLOAD \(Importe verzögert laden\)](../../build/reference/delayload-delay-load-import.md) mit einer Hilfsfunktion verwendet wird, deren Standardimplementierung von Visual C\+\+ bereitgestellt wird.  Die DLL wird von der Hilfsfunktion zur Laufzeit geladen, indem **LoadLibrary** und **GetProcAddress** aufgerufen werden.  
  
 Verzögertes Laden einer DLL sollte unter folgenden Umständen in Betracht gezogen werden:  
  
-   Das Programm ruft möglicherweise keine Funktion in der DLL auf.  
  
-   Eine Funktion in der DLL wird möglicherweise erst spät im Programmablauf aufgerufen.  
  
 Verzögertes Laden einer DLL kann angegeben werden, wenn entweder ein EXE\-Projekt oder ein DLL\-Projekt erstellt wird.  Von einem DLL\-Projekt, das das Laden einer oder mehrerer DLL verzögert, sollte selbst kein verzögert geladener Einstiegspunkt in **DLLmain** aufgerufen werden.  
  
 In den folgenden Themen wird verzögertes Laden von DLLs beschrieben:  
  
-   [Festlegen von DLLs für verzögertes Laden](../../build/reference/specifying-dlls-to-delay-load.md)  
  
-   [Explizites Entladen einer verzögert geladenen DLL](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md)  
  
-   [Laden aller Importe für eine verzögert geladene DLL](../../build/reference/loading-all-imports-for-a-delay-loaded-dll.md)  
  
-   [Bindung von Importen](../../build/reference/binding-imports.md)  
  
-   [Fehlerbehandlung und Benachrichtigung](../../build/reference/error-handling-and-notification.md)  
  
-   [Sichern von verzögert geladenen Importen](../../build/reference/dumping-delay-loaded-imports.md)  
  
-   [Beschränkungen für das verzögerte Laden von DLLs](../../build/reference/constraints-of-delay-loading-dlls.md)  
  
-   [Die Hilfsfunktion](assetId:///6279c12c-d908-4967-b0b3-cabfc3e91d3d)  
  
-   [Entwickeln eigener Hilfsfunktionen](../../build/reference/developing-your-own-helper-function.md)  
  
## Siehe auch  
 [DLLs in Visual C\+\+](../../build/dlls-in-visual-cpp.md)   
 [Verknüpfung](../../build/reference/linking.md)