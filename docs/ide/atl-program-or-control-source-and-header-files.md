---
title: "ATL-Programm oder Steuern von Quell- und Headerdateien | Microsoft Docs"
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
  - "Dateitypen [C++], ATL-Quelle und -Header"
ms.assetid: cb65372f-4880-4007-b582-a52eaa568fd1
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# ATL-Programm oder Steuern von Quell- und Headerdateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Abhängig von den Optionen, die Sie für das erstellte Projekt auswählen, werden bei der Erstellung eines ATL\-Projekts in Visual Studio die folgenden Dateien generiert.  
  
 Alle diese Dateien sind im Verzeichnis Projname und im Projektmappen\-Explorer entweder im Ordner **Headerdateien** \(H\-Dateien\) oder im Ordner **Quelldateien** \(CPP\-Dateien\) enthalten.  
  
|Dateiname|Beschreibung|  
|---------------|------------------|  
|*Projname*.h|Die Hauptincludedatei mit den C\+\+\-Schnittstellendefinitionen und GUID\-Deklarationen der in ATLSample.idl definierten Elemente.  Sie wird während der Kompilierung von MIDL neu erstellt.|  
|*Projname*.cpp|Zentrale Programmquelldatei.  Sie enthält bei einem prozessinternen Server die Implementierung der DLL\-Exporte und bei einem lokalen Server die Implementierung von `WinMain`.  Bei einem Dienst werden durch diese Datei automatisch auch alle Dienstverwaltungsfunktionen implementiert.|  
|Resource.h|Die Headerdatei für die Ressourcendatei.|  
|StdAfx.cpp|Enthält die Dateien **StdAfx.h** und **Atlimpl.cpp**.|  
|StdAfx.h|Enthält die ATL\-Headerdateien.|  
  
## Siehe auch  
 [Für Visual C\+\+\-Projekte erstellte Dateitypen](../ide/file-types-created-for-visual-cpp-projects.md)   
 [MFC\-Programm oder Steuern von Quell\- und Headerdateien](../ide/mfc-program-or-control-source-and-header-files.md)   
 [CLR\-Projekte](../ide/files-created-for-clr-projects.md)