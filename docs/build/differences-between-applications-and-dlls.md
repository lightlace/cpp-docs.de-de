---
title: "Unterschiede zwischen Anwendungen und DLLs"
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
  - "Anwendungen [C++], und DLLs (Vergleich)"
  - "DLLs [C++], Im Vergleich zu Anwendungen"
  - "Ausführbare Dateien [C++], DLLs im Vergleich zu Anwendungen"
ms.assetid: 8f271523-d8d0-4ad1-84d2-0c5645d7fd5b
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Unterschiede zwischen Anwendungen und DLLs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obwohl sowohl DLLs als auch Anwendungen ausführbare Programmmodule sind, unterscheiden sie sich in verschiedener Hinsicht.  Der auffälligste Unterschied für den Endbenutzer liegt darin, dass DLLs keine Programme sind, die direkt ausgeführt werden können.  Im Hinblick auf das System gibt es zwei grundsätzliche Unterschiede zwischen Anwendungen und DLLs:  
  
-   Von einer Anwendung können mehrere Instanzen gleichzeitig im System ausgeführt werden, während eine DLL nur eine Instanz haben kann.  
  
-   Eine Anwendung kann im Unterschied zu einer DLL über einen Stapel, globalen Arbeitsspeicher, Dateihandles und eine Meldungswarteschlange verfügen.  
  
## Was möchten Sie tun?  
  
-   [Aus einer DLL exportieren](../build/exporting-from-a-dll.md)  
  
-   [Eine ausführbare Datei mit einer DLL verknüpfen](../build/linking-an-executable-to-a-dll.md)  
  
-   [Initialisieren einer DLL](../build/initializing-a-dll.md)  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Vorteile der Verwendung von DLLs](../build/advantages-of-using-dlls.md)  
  
-   [MFC\-fremde DLLs: Übersicht](../build/non-mfc-dlls-overview.md)  
  
-   [Reguläre, statisch mit MFC verknüpfte DLLs](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [Reguläre, dynamisch mit MFC verknüpfte DLLs](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [Erweiterungs\-DLLs: Übersicht](../build/extension-dlls-overview.md)  
  
## Siehe auch  
 [DLLs in Visual C\+\+](../build/dlls-in-visual-cpp.md)