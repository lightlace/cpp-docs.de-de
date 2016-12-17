---
title: "Zwischenablage: Verwenden der Windows-Zwischenablage"
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
  - "Zwischenablage [C++], Befehle"
  - "Zwischenablage [C++], Windows-Zwischenablage-API"
  - "Zwischenablagebefehle"
  - "Zwischenablagebefehle, Implementieren"
  - "Befehle [C++], Bearbeiten implementieren"
  - "Ausschneiden/Kopieren und Einfügen-Befehlshandlerfunktionen"
  - "Handlerfunktionen, Ausschneiden/Kopieren und Einfügen-Befehle"
  - "Windows-Zwischenablage [C++]"
ms.assetid: 24415b42-9301-4a70-b69a-44c97918319f
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Zwischenablage: Verwenden der Windows-Zwischenablage
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird beschrieben, wie die Standard\-Windows\-Zwischenablage API in der MFC\-Anwendung verwendet.  
  
 Die meisten Anwendungen für Windows unterstützen Ausschnitt oder Kopieren von Daten zur Zwischenablage und das Einfügen von Daten aus der Zwischenablage.  Die Zwischenablagedatenformate variieren in Anwendungen.  Das Framework unterstützt nur eine begrenzte Anzahl Zwischenablageformate für eine begrenzte Anzahl Klassen.  Sie implementieren die Zwischenablage\-verknüpften normalerweise Befehle \- schneiden Sie aus, Kopieren und fügen Sie ein \- im Menü Bearbeiten für die Ansicht.  Die Klassenbibliothek definiert die Befehls\-IDs für diese Befehle: **ID\_EDIT\_CUT**, **ID\_EDIT\_COPY** und **ID\_EDIT\_PASTE**.  die MeldungZeileneingabeaufforderungen werden ebenfalls definiert.  
  
 [Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md) erläutert, wie Menübefehle in der Anwendung behandelt, indem dem Menübefehl zu eine Handlerfunktion zuordnet.  Solange die Anwendung nicht Handlerfunktionen für die Zwischenablage Befehle im Menü Bearbeiten definiert, sie verbleiben deaktiviert.  Um Handlerfunktionen für über die Befehle Ausschneiden und Kopierbefehle schreiben, implementieren Sie die Auswahl in der Anwendung.  Um eine Handlerfunktion für den Befehl Einfügen zu schreiben, fragen Sie die Zwischenablage ab um festzustellen ob die Daten in einem Format enthält, das die Anwendung aufnehmen kann.  Um beispielsweise den Kopierbefehl zu aktivieren, können z Sie Handler in etwa Folgendes:  
  
 [!CODE [NVC_MFCListView#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCListView#2)]  
  
 Die Schnitt\-, Kopieren und Einfügen sind in bestimmten Kontexten nur sinnvoll.  Die Schnitt\- und Kopierbefehle sollten aktiviert werden nur wenn etwas ausgewählt ist, und der Befehl Einfügen, wenn etwas in der Zwischenablage sind.  Sie können dieses Verhalten im Definieren von Aktualisierungshandlerfunktionen bereitstellen, die diese Befehle in Abhängigkeit vom Kontext aktivieren oder deaktivieren.  Weitere Informationen finden Sie unter [Erstellen Benutzeroberfläche\-Objekte aktualisiert](../mfc/how-to-update-user-interface-objects.md).  
  
 Die Microsoft Foundation Class\-Bibliothek bietet Unterstützung der Zwischenablage für Textausgabe mit den `CEdit` und `CEditView`\-Klassen.  Die OLE\-Klassen vereinfachen außerdem das Implementieren von Zwischenablagevorgängen, die OLE\-Elemente einschließen.  Weitere Informationen über die OLE\-Klassen, finden Sie unter [Zwischenablage: Verwenden des OLE\-Zwischenablage\-Mechanismus](../mfc/clipboard-using-the-ole-clipboard-mechanism.md).  
  
 Andere Bearbeitungsmenübefehle, wie implementiert, rückgängig machen \(**ID\_EDIT\_UNDO**\) und überprüfen Sie \(**ID\_EDIT\_REDO**\) ist, verlassen Sie auch.  Wenn die Anwendung diese Befehle nicht unterstützt, können Sie diese von der Ressourcendatei mit Visual C\+\+\-Ressourcen\-Editoren leicht löschen.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Kopieren und Einfügen von Daten](../mfc/clipboard-copying-and-pasting-data.md)  
  
-   [Verwenden des OLE\-Zwischenablagemechanismus](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)  
  
## Siehe auch  
 [Zwischenablage](../mfc/clipboard.md)