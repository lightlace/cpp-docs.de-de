---
title: "Lokalisierte Ressourcen in MFC-Anwendungen: Satelliten-DLLs | Microsoft Docs"
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
  - "DLLs [C++], Lokalisieren von MFC"
  - "Lokalisierung [C++], MFC-Ressourcen"
  - "Lokalisierte Ressourcen [C++]"
  - "MFC-DLLs [C++], Lokalisieren"
  - "Unterstützung mehrerer Sprachen [C++]"
  - "Nur-Ressourcen-DLLs [C++]"
  - "Nur-Ressourcen-DLLs [C++], MFC-Anwendungen"
  - "Ressourcen [MFC], Lokalisieren"
  - "Satelliten-DLLs [C++]"
ms.assetid: 3a1100ae-a9c8-47b5-adbd-cbedef5992ef
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Lokalisierte Ressourcen in MFC-Anwendungen: Satelliten-DLLs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC bietet ab Version 7.0 erweiterte Unterstützung für Satelliten\-DLLs, ein Feature, das den Entwickler bei der Erstellung von Anwendungen unterstützt, die für mehrere Sprachen lokalisiert sind.  Eine Satelliten\-DLL ist eine [reine Ressourcen\-DLL](../build/creating-a-resource-only-dll.md), die die für eine bestimmte Sprache lokalisierten Ressourcen einer Anwendung enthält.  Sobald die Anwendung ausgeführt wird, werden die lokalisierten, für die Umgebung am besten geeigneten Ressourcen automatisch von MFC geladen.  Angenommen, Sie verfügen über eine Anwendung mit englischen Sprachressourcen und zwei Satelliten\-DLLs, von denen eine die französische Übersetzung der Ressourcen und die andere eine deutsche Übersetzung enthält.  Wenn die Anwendung auf einem englischsprachigen System ausgeführt wird, werden die englischen Ressourcen verwendet.  Auf einem französischsprachigen System werden die französischen und auf einem deutschsprachigen die deutschen Ressourcen geladen.  
  
 Zur Unterstützung lokalisierter Ressourcen in einer MFC\-Anwendung versucht MFC, eine Satelliten\-DLL zu laden, deren Ressourcen in einer spezifischen Sprache lokalisiert wurden.  Satelliten\-DLLs sind nach dem Schema *AnwendungsnameXXX*.dll benannt, wobei *Anwendungsname* dem Namen der EXE\- oder DLL\-Datei entspricht, die MFC verwendet, und *XXX* den dreistelligen Code der Ressourcensprache darstellt, \(z. B. "ENU" oder "DEU"\).  
  
 MFC versucht, die Ressourcen\-DLL für jede der folgenden Sprachen in der angegebenen Reihenfolge zu laden. Wird eine Sprache gefunden, wird die Suche beendet:  
  
1.  \(Nur Windows 2000 oder höher\) Die standardmäßige Benutzeroberflächensprache des aktuellen Benutzers, wie von der Win32\-API **GetUserDefaultUILanguage\(\)** zurückgegeben.  
  
2.  \(Nur Windows 2000 oder höher\) Die standardmäßige Benutzeroberflächensprache des aktuellen Benutzers ohne spezifische Sprachvarianten \(d. h., "ENC" \[kanadisches Englisch\] wird zu "ENU"  \[US\-Englisch\]\).  
  
3.  Die standardmäßige Benutzeroberflächensprache des Systems.  Unter Windows 2000 oder höher wird sie durch die GetSystemDefaultUILanguage\(\)\-API zurückgegeben.  Auf anderen Plattformen entspricht sie der Betriebssystemsprache.  
  
4.  Die standardmäßige Benutzeroberflächensprache des Systems ohne spezifische Sprachvarianten.  
  
5.  Eine Pseudosprache mit dem dreistelligen Code LOC.  
  
 Falls keine Satelliten\-DLLs von MFC gefunden werden, werden die in der Anwendung selbst enthaltenen Ressourcen verwendet.  
  
 Beispiel: Angenommen, die Anwendung Sprachenbeispiel.exe verwendet MFC und wird auf einem Windows 2000\-Mehrbenutzersystem ausgeführt; die systemspezifische Benutzeroberflächensprache ist "ENU" \[US\-Englisch\],  und die Benutzeroberflächensprache des aktuellen Benutzers ist auf "FRC" \[kanadisches Französisch\] eingestellt.  Die folgenden DLLs werden von MFC in der angegebenen Reihenfolge gesucht:  
  
1.  **SprachenbeispielFRC.dll** \(Benutzeroberflächensprache des Benutzers\).  
  
2.  **SprachenbeispielFRA.dll** \(Benutzeroberflächensprache des Benutzers ohne Sprachvariante, in diesem Beispiel Französisch \(Frankreich\)\).  
  
3.  **SprachenbeispielENU.dll** \(Benutzeroberflächensprache des Systems\).  
  
4.  **SprachenbeispielLOC.dll**.  
  
 Wenn keine dieser DLLs gefunden wird, werden von MFC die Ressourcen in Sprachenbeispiel.exe verwendet.  
  
## Siehe auch  
 [DLLs in Visual C\+\+](../build/dlls-in-visual-cpp.md)   
 [TN057: Lokalisierung von MFC\-Komponenten](../mfc/tn057-localization-of-mfc-components.md)