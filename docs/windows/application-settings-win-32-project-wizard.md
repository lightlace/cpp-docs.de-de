---
title: "Anwendungseinstellungen, Win32-Projekt-Assistent"
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
  - "vc.appwiz.win32.appset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Anwendungseinstellungen [C++]"
  - "Win32-Projekt-Assistent, Anwendungseinstellungen"
ms.assetid: d6b818f0-9b23-4793-a6c5-df1c8c594bad
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Anwendungseinstellungen, Win32-Projekt-Assistent
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Auf dieser Seite des Assistenten können Sie Optionen für das Win32\-Projekt festlegen.  
  
 **Anwendungstyp**  
 Erstellt den angegebenen Anwendungstyp.  
  
|Option|**Beschreibung**|  
|------------|----------------------|  
|**Konsolenanwendung**|Erstellt eine Konsolenanwendung.  Konsolenprogramme werden mit [Konsolenfunktionen](https://msdn.microsoft.com/en-us/library/ms813137.aspx) entwickelt, die in Konsolenfenstern Zeichenmodusunterstützung bieten.  Außerdem unterstützen die [Laufzeitbibliotheken](../c-runtime-library/c-run-time-library-reference.md) von Visual C\+\+ über Standard\-E\/A\-Funktionen, wie **printf\_s\(\)** und **scanf\_s\(\)**, die Ausgabe und Eingabe in Konsolenfenstern.  Eine Konsolenanwendung hat keine grafische Benutzeroberfläche.  Sie kompiliert Code in einer EXE\-Datei und kann als eigenständige Anwendung von der Befehlszeile ausgeführt werden.<br /><br /> Sie können einer Konsolenanwendung MFC\- und ATL\-Unterstützung hinzufügen.|  
|**Windows\-Anwendung**|Erstellt ein Win32\-Programm.  Ein Win32\-Programm ist eine ausführbare Anwendung \(EXE\), die in C oder C\+\+ geschrieben ist und über Aufrufe der Win32\-API eine grafische Benutzeroberfläche erstellt.<br /><br /> Sie können einer Windows\-Anwendung keine MFC\- oder ATL\-Unterstützung hinzufügen.|  
|**DLL**|Erstellt eine Win32\-Dynamic Link Library \(DLL\).  Eine Win32\-DLL ist eine in C oder C\+\+ geschriebene Binärdatei, die anstelle von MFC\-Klassenaufrufen Win32\-API\-Aufrufe verwendet. Sie fungiert als gemeinsam genutzte Funktionsbibliothek, die von mehreren Anwendungen gleichzeitig eingesetzt werden kann.<br /><br /> Sie können einer DLL\-Anwendung keine MFC\- oder ATL\-Unterstützung hinzufügen.  Sie können angeben, dass von der DLL Symbole exportiert werden.|  
|**Statische Bibliothek**|Erstellt eine statische Bibliothek.  Eine statische Bibliothek ist eine Datei, die Objekte sowie zugehörige Funktionen und Daten enthält, die bei der Erstellung der ausführbaren Datei mit dem Programm verknüpft werden.  Unter diesem Thema wird die Erstellung von Startdateien und [Projekteigenschaften](../ide/property-pages-visual-cpp.md) für eine statische Bibliothek erläutert.  Eine statische Bibliothek bietet die folgenden Vorteile:<br /><br /> -   Eine statische Win32\-Bibliothek ist hilfreich, wenn die erstellte Anwendung Aufrufe an die Win32\-API und nicht an MFC\-Klassen sendet.<br />-   Unabhängig davon, ob der Rest der Windows\-Anwendung in C oder in C\+\+ geschrieben wird, ist der Verknüpfungsvorgang immer identisch.<br />-   Sie können eine statische Bibliothek mit einem MFC\-basierten Programm oder einem MFC\-fremden Programm verknüpfen.|  
  
 **Zusätzliche Optionen**  
 Definiert abhängig vom Anwendungstyp die Unterstützung sowie Optionen für die Anwendung.  
  
|Option|**Beschreibung**|  
|------------|----------------------|  
|**Leeres Projekt**|Legt fest, dass die Projektdateien leer sind.  Wenn Sie über eine Gruppe von Quellcodedateien \(z. B. CPP\-Dateien, Headerdateien, Symbole, Symbolleisten, Dialogfelder usw.\) verfügen und in der Visual C\+\+\-Entwicklungsumgebung ein Projekt erstellen möchten, müssen Sie zunächst ein leeres Projekt anlegen und die Dateien dem Projekt dann hinzufügen.<br /><br /> Diese Option ist für statische Bibliotheksprojekte nicht verfügbar.|  
|**Symbole exportieren**|Legt fest, dass vom DLL\-Projekt Symbole exportiert werden.|  
|**Vorkompilierter Header**|Legt fest, dass das statische Bibliotheksprojekt einen vorkompilierten Header verwendet.|  
|Security Development Lifecycle \(SDL\)\-Prüfungen|Weitere Informationen über SDL finden Sie unter [Microsoft Security Development Lifecycle \(SDL\)  Process Guidance](84aed186-1d75-4366-8e61-8d258746bopq).|  
  
 **Unterstützung hinzufügen für**  
 Fügen Sie Unterstützung für eine der in Visual C\+\+ enthaltenen Bibliotheken hinzu.  
  
|Option|**Beschreibung**|  
|------------|----------------------|  
|**ATL**|Wird in die Projektunterstützung für Klassen in ATL \(Active Template Library\) integriert.  Nur für Win32\-Konsolenanwendungen.<br /><br /> **Hinweis** Diese Option bietet keine Unterstützung für das Hinzufügen von ATL\-Objekten mit den ATL\-Code\-Assistenten.  Sie können ATL\-Objekte nur zu ATL\- oder MFC\-Projekten mit ATL\-Unterstützung hinzufügen.|  
|**MFC**|Wird in die Projektunterstützung für die MFC \(Microsoft Foundation Class\)\-Bibliothek integriert.  Nur für Win32\-Konsolenanwendungen und statische Bibliotheken.|  
  
## Siehe auch  
 [Win32\-Anwendungs\-Assistent](../windows/win32-application-wizard.md)   
 [Gewusst wie: Erstellen einer Windows\-Desktopanwendung](../Topic/How%20to:%20Create%20a%20Windows%20Desktop%20Application.md)