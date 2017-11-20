---
title: "\"LoadLibrary\" und \"AfxLoadLibrary\" | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: LoadLibrary
dev_langs: C++
helpviewer_keywords:
- DLLs [C++], AfxLoadLibrary
- DLLs [C++], LoadLibrary
- AfxLoadLibrary method
- LoadLibrary method
- explicit linking [C++]
ms.assetid: b4535d19-6243-4146-a31a-a5cca4c7c9e3
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7de79303e414691df7b069b55b82b2ba39f6ea1e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="loadlibrary-and-afxloadlibrary"></a>"LoadLibrary" und "AfxLoadLibrary"
Verarbeitet Aufruf [LoadLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259187) (oder ["AfxLoadLibrary"](../mfc/reference/application-information-and-management.md#afxloadlibrary)) zum expliziten Verknüpfen einer DLL. Wenn der Aufruf erfolgreich ist, ordnet die Funktion die angegebene DLL im Adressbereich des aufrufenden Prozesses zu und gibt ein Handle für die DLL zurück. Dieses Handle kann zusammen mit anderen Funktionen, beispielsweise `GetProcAddress` und `FreeLibrary`, für die explizite Verknüpfung verwendet werden.  
  
 `LoadLibrary` versucht, die DLL mithilfe derselben Suchfolge aufzufinden, die für die implizite Verknüpfung verwendet wird. Wenn das System die DLL nicht finden kann oder die Einstiegspunktfunktion FALSE zurückgibt, wird von `LoadLibrary` zurückgegeben. Wenn im Aufruf von `LoadLibrary` ein DLL-Modul angegeben ist, das bereits im Adressraum des aufrufenden Prozesses zugeordnet ist, gibt die Funktion einfach ein Handle für die DLL zurück und erhöht den Referenzzähler des Moduls.  
  
 Wenn die DLL über eine Einstiegspunktfunktion verfügt, ruft das Betriebssystem die Funktion im Kontext des Threads auf, durch den `LoadLibrary` aufgerufen wurde. Die Einstiegspunktfunktion wird nicht aufgerufen, wenn die DLL bereits an den Prozess angefügt ist, da es einen früheren Aufruf von `LoadLibrary` ohne entsprechenden Aufruf der `FreeLibrary`-Funktion gegeben hat.  
  
 Für MFC-Anwendungen, die MFC-Erweiterungs-DLLs laden, empfehlen wir die Verwendung `AfxLoadLibrary` anstelle von `LoadLibrary`. `AfxLoadLibrary` behandelt die Threadsynchronisierung vor dem Aufruf von `LoadLibrary`. Die Schnittstelle (Funktionsprototyp) zu `AfxLoadLibrary` ist mit `LoadLibrary` identisch.  
  
 Wenn die DLL von Windows nicht geladen werden kann, versucht der Prozess, die Verarbeitung fortzusetzen. So könnte der Prozess z. B. dem Benutzer den Fehler melden und ihn veranlassen, einen anderen Pfad für die DLL anzugeben.  
  
> [!IMPORTANT]
>  Ist der Code für die Ausführung unter Windows NT 4, Windows 2000 oder Windows XP (vor Installation von SP1), stellen Sie sicher, dass sämtliche DLLs der vollständige Pfadname angegeben. Unter diesen Betriebssystemen wird beim Laden von Dateien zuerst das aktuelle Verzeichnis durchsucht. Wenn Sie den Pfad für die Datei nicht qualifizieren, wird unter Umständen eine falsche Datei geladen.  
  
## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?  
  
-   [Gewusst wie: implizit mit einer DLL verknüpfen](../build/linking-an-executable-to-a-dll.md#linking-implicitly)  
  
-   [Welche Verknüpfungsmethode ermitteln](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [Den Suchpfad, der von Windows, zum Auffinden einer DLL verwendet wird](../build/search-path-used-by-windows-to-locate-a-dll.md)  
  
-   [FreeLibrary und AfxFreeLibrary](../build/freelibrary-and-afxfreelibrary.md)  
  
-   [GetProcAddress](../build/getprocaddress.md)  
  
## <a name="see-also"></a>Siehe auch  
 [DLLs in Visual C++](../build/dlls-in-visual-cpp.md)   
 [LoadLibrary](http://go.microsoft.com/fwlink/p/?LinkID=259187)   
 ["AfxLoadLibrary"](../mfc/reference/application-information-and-management.md#afxloadlibrary)