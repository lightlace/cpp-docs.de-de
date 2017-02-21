---
title: "Vorteile der Verwendung von DLLs | Microsoft Docs"
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
  - "DLLs [C++], Vorteile"
  - "Dynamisches Verknüpfen [C++]"
  - "Dynamisches Laden bzw. Verknüpfen [C++]"
  - "Verknüpfen [C++], Dynamisch und statisch im Vergleich"
  - "Links [C++], Dynamisch und statisch im Vergleich"
ms.assetid: 8956c8ee-e7b3-446f-a0c6-462381747690
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Vorteile der Verwendung von DLLs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die dynamische Verknüpfung hat die folgenden Vorteile:  
  
-   Sie spart Arbeitsspeicher und reduziert die Auslagerung.  Eine einzelne DLL kann von vielen Prozessen gleichzeitig verwendet werden. Dabei wird eine einzelne, in den Arbeitsspeicher geladene Kopie der DLL gemeinsam genutzt.  Im Gegensatz dazu muss Windows für jede mit einer Static Link Library erstellte Anwendung eine Kopie des Bibliothekscodes in den Arbeitsspeicher laden.  
  
-   Sie spart Festplattenspeicher.  Viele Anwendungen können eine einzelne, auf der Festplatte gespeicherte Kopie der DLL gemeinsam nutzen.  Im Gegensatz dazu wird für jede Anwendung, die mit einer Static Link Library erstellt wurde, der Bibliothekscode als separate Kopie in deren ausführbares Bild eingebunden.  
  
-   Sie vereinfacht das Upgrade der DLL.  Wenn sich die Funktionen in einer DLL ändern, müssen die Anwendungen, die diese DLL verwenden, nicht neu kompiliert oder neu verknüpft werden, solange sich die Argumente und Rückgabewerte der Funktion nicht ändern.  Im Gegensatz dazu erfordert ein statisch verknüpfter Objektcode, dass die Anwendung neu verknüpft wird, wenn sich die Funktionen ändern.  
  
-   Sie ermöglicht die Unterstützung nach der Vermarktung.  Eine Treiber\-DLL für ein Anzeigegerät kann z. B. so geändert werden, dass ein Gerät unterstützt wird, das zum Zeitpunkt der Auslieferung der Anwendung noch gar nicht verfügbar war.  
  
-   Sie unterstützt mehrere Programmiersprachen.  Programme, die in verschiedenen Programmiersprachen erstellt wurden, können dieselbe DLL\-Funktion aufrufen, solange sie die Aufrufkonvention der Funktion einhalten.  Die Programme und die DLL\-Funktion müssen in folgenden Punkten kompatibel sein: die von der Funktion erwartete Reihenfolge, in der Argumente auf den Stapel verschoben werden, ob die Funktion oder die Anwendung für das Bereinigen des Stapels verantwortlich ist und ob Argumente in Registern übergeben werden.  
  
-   Sie bietet einen Mechanismus zur Erweiterung der MFC\-Bibliotheksklassen.  Sie können Klassen von bestehenden MFC\-Klassen ableiten und diese in einer MFC\-Erweiterungs\-DLL speichern, die dann von MFC\-Anwendungen genutzt werden kann.  
  
-   Sie erleichtert die Erstellung von internationalen Versionen.  Das Erstellen internationaler Anwendungsversionen wird erheblich vereinfacht, wenn Sie Ressourcen in einer DLL speichern.  Sie können die Zeichenfolgen für jede Sprachversion der Anwendung in einer separaten Ressourcen\-DLL speichern und die Versionen so einrichten, dass jede Sprachversion ihre eigenen Ressourcen lädt.  
  
 Ein möglicher Nachteil bei der Verwendung von DLLs liegt darin, dass die Anwendung nicht unabhängig ausgeführt werden kann; sie hängt von der Existenz eines separaten DLL\-Moduls ab.  
  
## Was möchten Sie tun?  
  
-   [Aus einer DLL exportieren](../build/exporting-from-a-dll.md)  
  
-   [Eine ausführbare Datei mit einer DLL verknüpfen](../build/linking-an-executable-to-a-dll.md)  
  
-   [Initialisieren einer DLL](../build/initializing-a-dll.md)  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [MFC\-fremde DLLs: Übersicht](../build/non-mfc-dlls-overview.md)  
  
-   [Reguläre, statisch mit MFC verknüpfte DLLs](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [Reguläre, dynamisch mit MFC verknüpfte DLLs](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [Erweiterungs\-DLLs: Übersicht](../build/extension-dlls-overview.md)  
  
## Siehe auch  
 [DLLs in Visual C\+\+](../build/dlls-in-visual-cpp.md)