---
title: "F&#252;r CLR-Projekte erstellte Dateien"
ms.custom: na
ms.date: "12/14/2016"
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
  - ".NET-Anwendungen, C++"
  - "Visual C++-Projekte, CLR-Programmierung"
ms.assetid: 59ae9020-5f26-4ad0-bbdd-97c2e2023a20
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# F&#252;r CLR-Projekte erstellte Dateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie Projekte auf der Grundlage von Visual C\+\+\-Vorlagen erstellen, werden je nach verwendeter Vorlage mehrere Dateien erstellt.  In der folgenden Tabelle sind alle Dateien enthalten, die durch Projektvorlagen für .NET Framework\-Projekte erstellt werden.  
  
|Dateiname|Dateibeschreibung|  
|---------------|-----------------------|  
|AssemblyInfo.cpp|Datei mit Informationen \(z. B. Attributen, Dateien, Ressourcen, Typen, Versionsinformationen, Signaturinformationen usw.\), durch die Assemblymetadaten des Projekts geändert werden.  Weitere Informationen finden Sie unter [Assemblykonzepte](../Topic/Assembly%20Contents.md).|  
|*projname*.asmx|Textdatei mit Verweisen auf verwaltete Klassen, in denen die Funktionen des XML\-Webdienstes eingeschlossen sind.|  
|*projname*.cpp|Hauptquelldatei und Einstiegspunkt in die Anwendung, die von Visual Studio für Sie erstellt wurde.  Diese Datei identifiziert die DLL\-Datei und den Namespace des Projekts.  Fügen Sie eigenen Code in diese Datei ein.|  
|*projname*.vsdisco|XML\-Bereitstellungsdatei mit Links zu anderen Ressourcen, die den XML\-Webdienst beschreiben.|  
|*projname*.h|Hauptincludedatei für das Projekt, die alle Deklarationen, globalen Symbole und `#include`\-Direktiven für andere Headerdateien enthält.|  
|*projname*.sln|In der Entwicklungsumgebung verwendete Projektmappendatei, durch die alle Elemente eines Projekts innerhalb einer Projektmappe verwaltet werden.|  
|*projname*.suo|Die in der Entwicklungsumgebung verwendete Projektmappen\-Optionsdatei.|  
|*projname.vcxproj*|In der Entwicklungsumgebung verwendete Projektdatei, in der projektspezifische Informationen gespeichert sind.|  
|ReadMe.txt|Datei mit einer Beschreibung der einzelnen, in einem Projekt enthaltenen Dateien. Dabei werden die tatsächlichen, von der Vorlage erstellten Dateinamen verwendet.|