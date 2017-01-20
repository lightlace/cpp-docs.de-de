---
title: "Implizites Verkn&#252;pfen"
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
  - "Implizite Verknüpfung [C++]"
  - "Ladezeit für dynamische Bindung [C++]"
  - "Statisches Laden bzw. Verknüpfen [C++]"
ms.assetid: 3ea4c316-4e70-4111-9944-c1b4ad00c605
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Implizites Verkn&#252;pfen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Für die implizite Verknüpfung mit einer DLL benötigen ausführbare Dateien die folgenden Elemente vom Ersteller der DLL:  
  
-   Eine Headerdatei \(.h\-Datei\) mit Deklarationen der exportierten Funktionen und\/oder C\+\+\-Klassen.  Die Klassen, Funktionen und Daten sollten alle über `__declspec(dllimport)` verfügen. Weitere Informationen finden Sie unter [dllexport, dllimport](../cpp/dllexport-dllimport.md).  
  
-   Eine Importbibliothek \([LIB\-Dateien](../build/reference/dot-lib-files-as-linker-input.md)\) zur Verknüpfung. \(Die Importbibliothek wird vom Linker erstellt, nachdem die DLL erstellt wurde.\)  
  
-   Die DLL selbst \(DLL\-Datei\).  
  
 Ausführbare Dateien, die die DLL verwenden, müssen die Headerdatei umfassen, die die exportierten Funktionen \(oder C\+\+\-Klassen\) der einzelnen Quelldateien enthält, in denen Aufrufe der exportierten Funktionen gespeichert sind.  Hinsichtlich der Codierung unterscheiden sich die Funktionsaufrufe für exportierte Funktionen nicht von anderen Funktionsaufrufen.  
  
 Um die aufrufende ausführbare Datei zu erstellen, stellen Sie eine Verknüpfung mit der Importbibliothek her.  Wenn Sie ein externes Makefile verwenden, legen Sie den Dateinamen der Importbibliothek fest, in der Sie andere Objektdateien \(.obj\) oder Bibliotheken auflisten, mit denen eine Verknüpfung hergestellt wird.  
  
 Das Betriebssystem muss in der Lage sein, die DLL\-Datei beim Laden der aufrufenden ausführbaren Datei zu lokalisieren.  
  
## Was möchten Sie tun?  
  
-   [Explizite Verknüpfungen verwenden](../build/linking-explicitly.md)  
  
-   [Festlegen, welche Verknüpfungsmethode verwendet werden soll](../build/determining-which-linking-method-to-use.md)  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Arbeiten mit Importbibliotheken und Exportdateien](../build/reference/working-with-import-libraries-and-export-files.md)  
  
-   [Von Windows verwendeter Suchpfad zum Auffinden einer DLL](../build/search-path-used-by-windows-to-locate-a-dll.md)  
  
## Siehe auch  
 [Verknüpfen einer ausführbaren Datei mit einer DLL](../build/linking-an-executable-to-a-dll.md)