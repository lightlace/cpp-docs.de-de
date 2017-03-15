---
title: "&quot;FreeLibrary&quot; und &quot;AfxFreeLibrary&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "FreeLibrary"
  - "AfxFreeLibrary"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Erweiterungs-DLLs [C++], Entladen"
  - "AfxFreeLibrary-Methode"
  - "Entladen von DLLs"
  - "FreeLibrary-Methode"
  - "DLLs [C++], Verknüpfen"
  - "Explizite Verknüpfung [C++]"
  - "DLLs [C++], Entladen"
ms.assetid: 4a48d290-3971-43e9-8e97-ba656cd0c8f8
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# &quot;FreeLibrary&quot; und &quot;AfxFreeLibrary&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prozesse, die explizit mit einer DLL\-Aufruf die [" FreeLibrary "](http://go.microsoft.com/fwlink/p/?LinkID=259188)\-Funktion auf, wenn das DLL\-Modul nicht mehr benötigt wird.  Diese Funktion setzt den Verweiszähler des Moduls herab und entfernt, falls der Zähler auf Null steht, die Zuordnung zum Adressbereich des Prozesses.  
  
 In einer MFC\-Anwendung mit [AfxFreeLibrary](../Topic/AfxFreeLibrary.md) statt `FreeLibrary`, um eine Erweiterungs\-DLL zu entladen.  Die Schnittstelle \(Funktionsprototyp\) für `AfxFreeLibrary` ist mit `FreeLibrary` identisch.  
  
## Was möchten Sie tun?  
  
-   [Implizite Verknüpfungen verwenden](../build/linking-implicitly.md)  
  
-   [Festlegen, welche Verknüpfungsmethode verwendet werden soll](../build/determining-which-linking-method-to-use.md)  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [LoadLibrary und AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [GetProcAddress](../build/getprocaddress.md)  
  
## Siehe auch  
 [DLLs in Visual C\+\+](../build/dlls-in-visual-cpp.md)   
 [FreeLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259188)   
 [AfxFreeLibrary](../Topic/AfxFreeLibrary.md)