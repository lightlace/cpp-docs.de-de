---
title: "LoadLibrary und AfxLoadLibrary | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LoadLibrary"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AfxLoadLibrary-Methode"
  - "DLLs [C++], AfxLoadLibrary"
  - "DLLs [C++], LoadLibrary"
  - "Explizite Verknüpfung [C++]"
  - "LoadLibrary-Methode"
ms.assetid: b4535d19-6243-4146-a31a-a5cca4c7c9e3
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# LoadLibrary und AfxLoadLibrary
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prozesse rufen [LoadLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259187) \(oder [AfxLoadLibrary](../Topic/AfxLoadLibrary.md)\) auf, um eine explizite Verknüpfung mit einer DLL herzustellen.  Wenn der Aufruf erfolgreich ist, ordnet die Funktion die angegebene DLL im Adressbereich des aufrufenden Prozesses zu und gibt ein Handle für die DLL zurück. Dieses Handle kann zusammen mit anderen Funktionen, beispielsweise `GetProcAddress` und `FreeLibrary`, für die explizite Verknüpfung verwendet werden.  
  
 `LoadLibrary` versucht, die DLL mithilfe derselben Suchfolge aufzufinden, die für die implizite Verknüpfung verwendet wird.  Wenn das System die DLL nicht finden kann oder die Einstiegspunktfunktion FALSE zurückgibt, wird von `LoadLibrary` zurückgegeben.  Wenn im Aufruf von `LoadLibrary` ein DLL\-Modul angegeben ist, das bereits im Adressraum des aufrufenden Prozesses zugeordnet ist, gibt die Funktion einfach ein Handle für die DLL zurück und erhöht den Referenzzähler des Moduls.  
  
 Wenn die DLL über eine Einstiegspunktfunktion verfügt, ruft das Betriebssystem die Funktion im Kontext des Threads auf, durch den `LoadLibrary` aufgerufen wurde.  Die Einstiegspunktfunktion wird nicht aufgerufen, wenn die DLL bereits an den Prozess angefügt ist, da es einen früheren Aufruf von `LoadLibrary` ohne entsprechenden Aufruf der `FreeLibrary`\-Funktion gegeben hat.  
  
 Für MFC\-Anwendungen, die Erweiterungs\-DLLs laden, wird empfohlen, `AfxLoadLibrary` statt `LoadLibrary` zu verwenden.  `AfxLoadLibrary` behandelt die Threadsynchronisierung vor dem Aufruf von `LoadLibrary`.  Die Schnittstelle \(Funktionsprototyp\) zu `AfxLoadLibrary` ist mit `LoadLibrary` identisch.  
  
 Wenn die DLL von Windows nicht geladen werden kann, versucht der Prozess, die Verarbeitung fortzusetzen.  So könnte der Prozess z. B. dem Benutzer den Fehler melden und ihn veranlassen, einen anderen Pfad für die DLL anzugeben.  
  
> [!IMPORTANT]
>  Wenn der Code unter Windows NT 4, Windows 2000 oder Windows XP \(vor Installation von SP1\) ausgeführt werden soll, vergewissern Sie sich, dass für sämtliche DLLs der vollständige Pfadname angegeben ist.  Unter diesen Betriebssystemen wird beim Laden von Dateien zuerst das aktuelle Verzeichnis durchsucht.  Wenn Sie den Pfad für die Datei nicht qualifizieren, wird unter Umständen eine falsche Datei geladen.  
  
## Was möchten Sie tun?  
  
-   [Implizite Verknüpfungen verwenden](../build/linking-implicitly.md)  
  
-   [Festlegen, welche Verknüpfungsmethode verwendet werden soll](../build/determining-which-linking-method-to-use.md)  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Der von Windows verwendete Suchpfad zum Auffinden einer DLL](../build/search-path-used-by-windows-to-locate-a-dll.md)  
  
-   ["FreeLibrary" und "AfxFreeLibrary"](../build/freelibrary-and-afxfreelibrary.md)  
  
-   [GetProcAddress](../build/getprocaddress.md)  
  
## Siehe auch  
 [DLLs in Visual C\+\+](../build/dlls-in-visual-cpp.md)   
 [LoadLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259187)   
 [AfxLoadLibrary](../Topic/AfxLoadLibrary.md)