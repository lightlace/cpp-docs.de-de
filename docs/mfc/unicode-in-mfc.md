---
title: "Unicode in MFC | Microsoft Docs"
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
  - "Zeichenfolgen [C++], Unicode"
  - "Unicode [C++], Aktivieren"
  - "Unicode [C++], MFC"
  - "Breitzeichen, Codierung"
  - "Breitzeichen, Unicode"
ms.assetid: 1002004b-4113-4380-bf63-e1570934b793
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Unicode in MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC unterstützt den Unicode\-Standard für das Codieren von Breitzeichen auf Windows NT\-, Windows 2000 \- und Windows XP\-Plattformen.  Unicode\-Anwendungen können nicht auf Windows 98\-Plattformen ausgeführt werden.  
  
 Die Unicode\-Versionen der MFC\-Bibliotheken sind unten beschrieben:  
  
### Statische Libraries  
  
|Release|Debuggen|**Beschreibung**|  
|-------------|--------------|----------------------|  
|UAFXCW.lib, .pdb|UAFXCWD.lib, .pdb|Statische Static MFC von Unicode|  
  
### Dynamic Link Librarys  
  
|Release|Debuggen|**Beschreibung**|  
|-------------|--------------|----------------------|  
|MFC100U.lib, .dbg, def, .dll, .map, .pdb, .prf|MFC100UD.lib, .def, .dll, .map, .pdb|Importbibliothek des Unicode MFC \(siehe Hinweise nachstehenden Erläuterung von Dateierweiterungen\)|  
|MFCS100U.lib, .pdb|MFCS100UD.lib, .pdb|Importbibliothek des Unicode MFC, die Code enthält, der in einer Anwendung oder einer DLL statisch verknüpft werden muss|  
  
 **Dateitypen**  
  
-   Importbibliotheksdateien haben die Erweiterung \(.lib\).  
  
-   DLL\-Dateien haben die Erweiterung \(.dll\).  
  
-   Dateien der Moduldefinition \(.def\) sind Textdateien, die Anweisungen zum Definieren einer EXE\-Datei oder DLL\-Datei enthalten.  
  
-   Zuordnungsdateien \(.map\) sind Textdateien mit Informationen, die der Linker verwendet, wenn er ein Programm verknüpft.  
  
-   Bibliotheksdateien \(.lib\) werden in Verbindung mit den DLL\-Versionen von MFC verwendet.  Diese Dateien enthalten Code, der in der Anwendung oder der DLL statisch verknüpft werden muss.  
  
-   Programmdatenbankdateien \(.pdb\) enthalten Debuggen und seines Zustandsinformationen.  
  
-   Debugdateien \(.dbg\) enthalten Informationen \(COFF FPO und CodeView\), die der Visual C\+\+\-Debugger verwendet.  
  
 Ausführliche Informationen zu Namenskonventionen finden Sie unter [Bibliotheks\-Namenskonventionen](../mfc/library-naming-conventions.md).  
  
 Informationen über die Verwendung von Unicode mit MFC, finden Sie unter [Zeichenfolgen: Unicode\- und des Multibyte\-Zeichensatz\-\(MBCS\) Unterstützung](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md).  
  
## Siehe auch  
 [Konzepte](../mfc/mfc-concepts.md)   
 [Allgemeine MFC\-Themen](../mfc/general-mfc-topics.md)