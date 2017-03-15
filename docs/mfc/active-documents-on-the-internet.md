---
title: "Active Documents f&#252;r das Internet | Microsoft Docs"
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
  - "Aktive Dokumente [C++], Erstellen"
  - "Aktive Dokumente [C++], Programmierschritte"
  - "Aktive Dokumente [C++], Verwenden von Anwendungs-Assistenten"
  - "Anwendungsassistenten [C++]"
  - "Anwendungsassistenten [C++], Aktive Dokumente"
ms.assetid: a46bd8a0-e27a-4116-b1bf-dacdb7ae78d1
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Active Documents f&#252;r das Internet
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Active Documents stellen eine Erweiterung zu den herkömmlichen eingebetteten Objekten.  Die aktiven Dokumenten können und werden im gesamten Clientbereich mehrseitig.  Hierzu herkömmliche Menüaushandlung und können einem geöffneten Fenster in der Serveranwendung bearbeitetes direktes sowie in sein.  Anstatt, als kleines Rechteck angezeigt, das durch einen schraffierten Rahmen umgeben ist, aktive Dokumente vollständige Frames und immer direkt aktiv.  
  
 Aktive Dokumente kann in einem Container wie das Microsoft Office\-Binder angezeigt werden, der eine Methode bereitstellt, ein Verbunddokument erstellen, das aus verschiedenen Dokumenttypen wie Excel besteht, abfassen und der benutzerdefinierte Dokumenttyp, die beide bearbeitete vollständige Frames sein kann.  Active Documents können im Browser wie Microsoft Internet Explorer auch angezeigt werden, der ein Active Document\-Container ist.  
  
 **Aktives Dokumentvorteilseinschließung:**  
  
-   Dokumente können angezeigte vollständige Frames, im gesamten Clientfenster sein.  
  
-   Dokumente können in einem separaten Anwendungsfenster geöffnet sein.  
  
     Damit das Dokument, das Hilfsprogramm muss vom Client vorhanden ist oder heruntergeladen einzeln geöffnet wird, bevor die Anwendung ausgeführt werden kann.  Ein Viewer wird so geschrieben werden, um nur Funktionen bereitzustellen \(Word, Excel und PowerPoint stellen Viewer für ihre Dokumente bereit\).  Die Vollversion der Anwendung kann vollständige Bearbeitungsunterstützung bieten.  
  
-   Dokumente sind immer direkt aktiv.  
  
-   Die Menübefehle, die vom Container aufgerufen werden, können dem Dokument weitergeleitet werden.  
  
-   Dokumente können in einem Webbrowser angezeigt werden.  Dies bietet eine nahtlose Integration zwischen Dokumenten und anderen Webseiten.  
  
     Ein Benutzer kann eine HTML\-Webseite, dann ein Excel\-Arbeitsblatt und dann zu einem Dokument navigieren, das Sie mit MFC\-Unterstützung für Active Documents geschrieben haben.  Der Benutzer kann mit der vertrauten Weboberfläche navigieren, wie die Browserschalter nahtlos zwischen Menüs und den Ansichten einer HTML\-Seite, Excel und das Dokument der Anwendung.  
  
-   Alle Anwendungen werden in allgemeinen Frame angezeigt.  
  
## Anforderungen für aktive Dokumente  
 Die Schnittstellen aufgeführt in der Tabelle unter der Einschließungsschnittstellen bereits erforderlich für eingebettete Server und mehrerer neuer Schnittstellen bestimmt zu aktiven Dokumenten.  MFC stellt Standardimplementierungen für die meisten dieser Schnittstellen in der [COleServerDoc](../mfc/reference/coleserverdoc-class.md)\-Klasse bereit.  
  
|Ein Dokument das...|Implementiert diese Schnittstellen|  
|-------------------------|----------------------------------------|  
|Wird Verbunddateien als Speichermechanismus.|`IPersistStorage`.|  
|Unterstützt die grundlegenden Einbettungsfunktionen von aktiven Dokumenten, einschließlich Erstellen der Datei.|`IPersistFile`, `IOleObject` und `IDataObject`.|  
|Unterstützt direkte Aktivierung.|`IOleInPlaceObject` und `IOleInPlaceActiveObject` \(mithilfe des Containers `IOleInPlaceSite` und der **IOleInPlaceFrame**\-Schnittstellen\).|  
|Unterstützt die aktiven Dokumenterweiterungen, die diese neuen Schnittstellen enthalten.  Einige Schnittstellen sind optional.|`IOleDocument`, `IOleDocumentView`, `IOleCommandTarget` und `IPrint`.|  
  
 MFC bietet Unterstützung für das Erweitern vorhandener eingebetteten Serverunterstützung aktiven Dokumenten.  
  
## Fügen Sie Active Document\-Unterstützung einer neuen Anwendung hinzu  
 Um eine neue Anwendung mit Active Document\-Unterstützung erstellen: Im MFC\-Anwendungs\-Assistenten auf der Seite **Verbunddokumente**, unter "ausgewählt Verbunddokumentunterstützung" die Option **Vollserver** oder **Container\/Vollserver** aus, und unter "ausgewählten Optionen" aktivieren Sie das Kontrollkästchen für **Active Document\-Server** aus.  
  
##  <a name="_core_convert_an_existing_mfc_in.2d.process_server_to_an_activex_document_server"></a> Konvertieren eines vorhandenen prozessinternen Server MFC\-Programm zu einem Active Document\-Server  
 Wenn die Anwendung mit einer Version von Visual C\+\+ vor Version 4.2 erstellt wurde und bereits ein prozessinterner Server ist, können Sie Active Document\-Unterstützung hinzufügen, indem Sie die folgenden Klassen vornehmen:  
  
|Klassentyp|Früher abgeleitet von|Ändern Sie, um von abgeleitet|  
|----------------|---------------------------|-----------------------------------|  
|Direkte Frames|`COleIPFrameWnd`|**COleDocIPFrameWnd**|  
|Element|`COleServerItem`|`CDocObjectServerItem`|  
  
 Außerdem ändern Sie, wie Informationen, in die Registrierung eingetragen werden, und nehmen einige andere Änderungen vor.  Wenn die Anwendung derzeit keine COM\-Komponenten Unterstützung hat, können Sie Serverunterstützung hinzufügen, mit dem Anwendungs\-Assistenten ausführen und den COM\-Komponentebesonderecode mit der vorhandenen Anwendung integrieren.  
  
## Siehe auch  
 [MFC\-Internetprogrammierungsaufgaben](../mfc/mfc-internet-programming-tasks.md)   
 [Grundlagen der MFC\-Internetprogrammierung](../mfc/mfc-internet-programming-basics.md)