---
title: "Dynamic Link Library-Unterst&#252;tzung | Microsoft Docs"
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
  - "DLLs [C++], MFC"
  - "MFC-DLLs [C++], Reguläre DLLs"
  - "NAFXDW.LIB"
  - "NAFXDWD.LIB"
  - "Reguläre DLLs [C++], Projektziele als DLLs"
  - "USRDLLs, DLL-Unterstützung"
ms.assetid: cc31c69f-3c78-4db1-9ecd-0fd8dc3217e3
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Dynamic Link Library-Unterst&#252;tzung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die NAFXCW.lib\- und NAFXCWD.lib\-Bibliotheken \(in der STATIC\-Link\-Bibliotheks\-Namenskonventionstabelle in [Bibliotheks\-Namenskonventionen](../mfc/library-naming-conventions.md)\) erstellen das Projekt als Dynamic Link Library, aufgerufen ein "Reguläre DLL" \(früher ein "USRDLL"\) das mit Anwendungen verwendet werden, die nicht mit der Klassenbibliothek erstellt werden.  Diese DLL\-Unterstützung ist nicht das Gleiche wie MFCx0.DLL und MFCx0D.DLL \(bezeichnet als "AFXDLL"\), die die gesamte Klassenbibliothek in einer DLL enthalten.  Weitere Informationen finden Sie unter [DLLs](../build/dlls-in-visual-cpp.md).  Eine Tabelle von DLL\-Namen, finden Sie unter [Namenskonventionen für MFC\-DLLs](../build/naming-conventions-for-mfc-dlls.md).  
  
## Siehe auch  
 [MFC\-Bibliotheksversionen](../mfc/mfc-library-versions.md)