---
title: "Automatisches Verlinken der MFC-Bibliotheksversion | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "defaultlib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Automatische Links [C++]"
  - "defaultlib in MFC"
  - "Verknüpfen [C++]"
  - "Verknüpfen [C++], automatisches verlinken der MFC-Bibliotheksversion"
  - "Verknüpfen [C++], von MFC"
  - "MFC-Bibliotheken, verknüpfen mit"
  - "MFC-Bibliotheken, Versionen"
ms.assetid: 02af4a20-2034-4fce-b200-c2202c3c8311
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Automatisches Verlinken der MFC-Bibliotheksversion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In Versionen vor Version 3.0 von MFC \(vor Visual C\+\+\-Version 2.0\), mussten Sie die richtige Version der MFC\-Bibliothek in der Eingabeliste von Bibliotheken für den Linker manuell angeben.  Mit MFC, Version 3.0 ist es nicht mehr erforderlich, die Version der MFC\-Bibliothek manuell angeben können.  Stattdessen helfen die MFC\-Headerdateien automatisch die richtige Version der MFC\-Bibliothek, anhand der Werte, die mit `#define`, wie **\_DEBUG** oder **\_UNICODE** definiert werden.  Die MFC\-Headerdateien fügen **\/defaultlib**\-Direktive hinzu, die der Linker Link in einer bestimmten Version der MFC\-Bibliothek anweisen.  
  
 Beispielsweise weist das folgende Codefragment von der AFX.H\-Headerdatei den Linker an, um in der NAFXCWD.LIB\- oder NAFXCW.LIB\-Version von MFC, abhängig von Verknüpfung entweder, ob Sie die Debugversion von MFC verwenden:  
  
 `#ifndef _UNICODE`  
  
 `#ifdef _DEBUG`  
  
 `#pragma comment(lib, "nafxcwd.lib")`  
  
 `#else`  
  
 `#pragma comment(lib, "nafxcw.lib")`  
  
 `#endif`  
  
 `#else`  
  
 `#ifdef _DEBUG`  
  
 `#pragma comment(lib, "uafxcwd.lib")`  
  
 `#else`  
  
 `#pragma comment(lib, "uafxcw.lib")`  
  
 `#endif`  
  
 `#endif`  
  
 MFC\-Headerdateien verknüpfen auch in allen erforderlichen Bibliotheken, einschließlich MFC\-Bibliotheken, Win32\-Bibliotheken, OLE\-Bibliotheken, OLE\-Bibliotheken, die von Beispielen, ODBC\-Bibliotheken, z. B erstellt werden.  Die Win32\-Bibliotheken schließen Kernel32.Lib, User32.Lib und GDI32.Lib ein.  
  
## Siehe auch  
 [MFC\-Bibliotheksversionen](../mfc/mfc-library-versions.md)