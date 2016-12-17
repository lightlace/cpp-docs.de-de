---
title: "Verhalten der Laufzeitbibliothek"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "_DllMainCRTStartup"
  - "CRT_INIT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_CRT_INIT-Makro"
  - "_DllMainCRTStartup-Methode"
  - "DllMain-Funktion"
  - "DLLs [C++], Eintiegspunktfunktion"
  - "DLLs [C++], Laufzeitbibliotheksverhalten"
  - "DLLs [C++], Startsequenz"
  - "Prozessanfügung [C++]"
  - "Prozesstrennung [C++]"
  - "Laufzeit [C++], DLL-Startsequenz"
ms.assetid: e06f24ab-6ca5-44ef-9857-aed0c6f049f2
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Verhalten der Laufzeitbibliothek
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die DLL\-Startsequenz wird vom C\/C\+\+\-Laufzeit\-Bibliothekscode ausgeführt. Dadurch entfällt die Notwendigkeit, wie bei Windows 3.x, ein separates Modul zu verknüpfen.  Im C\/C\+\+\-Laufzeit\-Bibliothekscode ist die **\_DllMainCRTStartup**\-Einstiegspunktfunktion für die DLL enthalten.  Die **\_DllMainCRTStartup**\-Funktion erledigt verschiedene Aufgaben, darunter den Aufruf von **CRT\_INIT**, wodurch die C\/C\+\+\-Laufzeitbibliothek initialisiert und C\+\+\-Konstruktoren für statische, nicht lokale Variablen aufgerufen werden.  Ohne diese Funktion würde die Laufzeitbibliothek in einem nicht initialisierten Zustand verbleiben.  **\_CRT\_INIT** kann sowohl für statisch verknüpften CRT\-Code als auch für das Verknüpfen mit der CRT\-DLL Msvcr90.dll aus einer Benutzer\-DLL heraus verwendet werden.  
  
 Obwohl es möglich ist, über die **\/ENTRY**\-Linkeroption eine andere Einstiegspunktfunktion festzulegen, wird von diesem Schritt abgeraten, da die Einstiegspunktfunktion in diesem Fall alle von **\_DllMainCRTStartup** ausgeführten Aktionen verdoppeln würde.  Beim Erstellen von DLLs in Visual C\+\+ wird **\_DllMainCRTStartup** automatisch eingebunden, sodass Sie keine Einstiegspunktfunktion mit der **\/ENTRY**\-Linkeroption festlegen müssen.  
  
 Zusätzlich zum Initialisieren der C\-Laufzeitbibliothek ruft **\_DllMainCRTStartup** eine Funktion mit dem Namen `DllMain` auf.  Je nach Typ der zu erstellenden DLL stellt Visual C\+\+ eine `DllMain`\-Funktion bereit, die automatisch eingebunden wird, sodass **\_DllMainCRTStartup** immer eine Funktion aufrufen kann.  Wenn Sie die DLL nicht initialisieren müssen, brauchen Sie beim Erstellen der DLL folglich keine weiteren Schritte zu unternehmen.  Falls die DLL jedoch initialisiert werden muss, hängt es vom Typ der zu erstellenden DLL ab, wo Sie eigenen Code einfügen.  Weitere Informationen finden Sie unter [Initialisieren einer DLL](../build/initializing-a-dll.md).  
  
 Der C\/C\+\+\-Laufzeit\-Bibliothekscode ruft Konstruktoren und Destruktoren für statische, nicht lokale Variablen auf.  Im folgenden DLL\-Quellcode stehen `Equus` und `Sugar` beispielsweise für zwei statische, nicht lokale Objekte der Klasse `CHorse`, die in Horses.h definiert ist.  Der Quellcode enthält keine Funktion, die Aufrufe einer Konstruktorfunktion für `CHorse` oder einer Destruktorfunktion aufweist, da diese Objekte unabhängig von Funktionen definiert werden.  Daher müssen Aufrufe dieser Konstruktoren und Destruktoren durch den Laufzeitcode ausgeführt werden.  Diese Funktion wird auch durch den Laufzeit\-Bibliothekscode für Anwendungen ausgeführt.  
  
```  
#include "horses.h"  
  
CHorse  Equus( ARABIAN, MALE );  
CHorse  Sugar( THOROUGHBRED, FEMALE );  
  
BOOL    WINAPI   DllMain (HANDLE hInst,   
                            ULONG ul_reason_for_call,  
                            LPVOID lpReserved)  
...  
```  
  
 Jedes Mal, wenn ein neuer Prozess versucht, die DLL zu verwenden, erstellt das Betriebssystem eine separate Kopie der DLL\-Daten. Dieser Vorgang wird als Prozess anfügen bezeichnet.  Der Laufzeit\-Bibliothekscode für die DLL ruft zunächst die Konstruktoren für alle globalen Objekte \(sofern vorhanden\) und anschließend die `DllMain`\-Funktion auf, wobei "Prozess anfügen" ausgewählt wird.  Der umgekehrte Vorgang wird als "Prozess trennen" bezeichnet: Der Laufzeit\-Bibliothekscode ruft zunächst `DllMain` mit "Prozess trennen" und dann eine Reihe von Terminierungsfunktionen auf, darunter `atexit`\-Funktionen sowie Destruktoren für globale und für statische Objekte.  Beachten Sie, dass die Reihenfolge der Ereignisse bei "Prozess anfügen" genau umgekehrt verläuft wie bei "Prozess trennen".  
  
 Der Laufzeit\-Bibliothekscode wird auch beim Anfügen und Trennen eines Threads aufgerufen, er führt jedoch keine selbstständige Initialisierung oder Terminierung durch.  
  
## Was möchten Sie tun?  
  
-   [Initialisieren einer DLL](../build/initializing-a-dll.md)  
  
## Siehe auch  
 [DLLs in Visual C\+\+](../build/dlls-in-visual-cpp.md)