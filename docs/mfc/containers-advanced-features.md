---
title: "Container: Erweiterte Funktionen | Microsoft Docs"
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
  - "Container/Server-Anwendungen [C++]"
  - "Container [C++], Erweiterte Features"
  - "Container [C++], Containeranwendungen"
  - "Container [C++], Links zu eingebetteten OLE-Objekten"
  - "Eingebettete Objekte [C++]"
  - "Links [C++], zu eingebetteten OLE-Objekten"
  - "OLE-Container, Erweiterte Features"
  - "OLE-Steuerelemente, Container"
  - "Server/Container-Anwendungen"
ms.assetid: 221fd99c-b138-40fa-ad6a-974e3b3ad1f8
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Container: Erweiterte Funktionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt die Schritte, die erforderlich sind, optionale erweiterte Funktionen in vorhandene Containeranwendungen zu enthalten.  Diese Funktionen sind:  
  
-   [Eine Anwendung, die ein Container und Server ist ein](#_core_creating_a_container.2f.server_application)  
  
-   [Ein OLE\-Link zu einem eingebetteten Objekt](#_core_links_to_embedded_objects)  
  
##  <a name="_core_creating_a_container.2f.server_application"></a> Erstellen einer bin\/Server\-Anwendung  
 Eine bin\/Server\-Anwendung ist eine Anwendung, die als Container und ein Server auftritt.  Microsoft Word für Windows ist ein entsprechendes Beispiel.  Sie können Word für Windows\-Dokumente in anderen Anwendungen einbetten, und Sie können Elemente in Word für Windows\-Dokumente auch einbetten.  Der Prozess zum Ändern der Containeranwendung, Container und Server ein vollständiger \(Sie können eine Kombination Bin\/miniserver\-Anwendung nicht erstellen\), sind ist mit dem Prozess zum Erstellen eines vollständigen Servers ähnlich.  
  
 Der Artikel [Server: Implementieren eines Servers](../mfc/servers-implementing-a-server.md) werden Aufgaben auf, die erforderlich sind, eine Serveranwendung zu implementieren.  Wenn Sie eine Containeranwendung keiner bin\/Server\-Anwendung konvertieren, müssen Sie einige dieser gleichen Aufgaben ausführen und Code zum Container hinzu.  Im Folgenden sind die Datengenerierung unbedingt auf, um zu beachten:  
  
-   Der Containercode, der initialisiert vom Anwendungs\-Assistenten erstellt wird, das bereits OLE\-Subsystem.  Sie müssen nichts, um für diese Unterstützung zu ändern oder hinzuzufügen.  
  
-   Unabhängig wo ist die Basisklasse einer Dokumentklasse `COleDocument`, ändern die Basisklasse für `COleServerDoc`.  
  
-   Überschreiben Sie `COleClientItem::CanActivate`, um Elemente, bearbeiten zu vermeiden, direkt während der Server selbst verwendet wird, um direkt zu bearbeiten.  
  
     Beispielsweise ist das Beispiel [OCLIENT](../top/visual-cpp-samples.md) MFC\-OLE ein Element eingebettet, auf das die Container\/Server\-Anwendung erstellt wird.  Öffnen Sie die OCLIENT\-Anwendung und die direkte Bearbeitung, die das Element von der Container\/Server\-Anwendung erstellt hat.  Beim Bearbeiten des Elements der Anwendung, entscheiden Sie möchten ein Element einbetten, die durch das Beispiel [HIERSVR](../top/visual-cpp-samples.md) MFC\-OLE erstellt wird.  Um dies zu erreichen, können Sie direkte Aktivierung nicht verwenden.  müssen Sie HIERSVR vollständig öffnen, um das Element zu aktivieren.  Da die Microsoft Foundation Class\-Bibliothek nicht unterstützt, können diese OLE\-Funktion das Überschreiben von `COleClientItem::CanActivate` Sie zur Überprüfung diese Situation auf und verhindert ein potenzieller Laufzeitfehler in der Anwendung.  
  
 Wenn Sie eine neue Anwendung erstellen und als Container\/Server\-Anwendung funktionieren soll, wählen Sie aus, dass Option im OLE\-Optionsdialogfeld im Anwendungs\-Assistenten und in dieser Unterstützung automatisch erstellt wird.  Weitere Informationen finden Sie im Artikel [Übersicht: Erstellen eines ActiveX\-Steuerelementcontainers zum Anzeigen](../mfc/reference/creating-an-mfc-activex-control-container.md).  Informationen zum MFC\-Beispiele, finden Sie MFC\-Beispiele.  
  
 Beachten Sie, dass Sie sich in eine MDI\-Anwendung nicht einfügen können.  Eine Anwendung, die ein Container\/Server ist, kann nicht in sich eingefügt werden, es sei denn, es ist eine SDI\-Anwendung ist.  
  
##  <a name="_core_links_to_embedded_objects"></a> Links in eingebettete Objekte  
 Die Links zur Funktion der eingebetteten Objekte aktiviert einen Benutzer, ein Dokument mit einem OLE\-Link einem eingebetteten Objekts innerhalb der Containeranwendung zu erstellen.  Beispielsweise erstellen Sie ein Dokument in einem Textverarbeitungsprogramm, das ein eingebettetes Arbeitsblatt enthält.  Wenn die AnwendungsHalterungsstangen zu eingebetteten Objekten, ein Link zum Arbeitsblatt einfügen können, das im Dokument Textverarbeitungsprogramms enthalten war.  Diese Funktion kann eine Anwendung, die Informationen verwendet, die im Arbeitsblatt enthalten sind, ohne zu wissen, wo das Textverarbeitungsprogramm es ursprünglich abgerufen wird.  
  
#### Weitere zu eingebetteten Objekten in der Anwendung verknüpft  
  
1.  Leiten Sie die Dokumentklasse von `COleLinkingDoc` anstelle von `COleDocument`.  
  
2.  Erstellen Sie eine OLE\-Klassen\-ID \(**CLSID**\) für die Anwendung, indem Sie den Klassen\-ID\-Generator verwenden, der mit den OLE\-Entwicklungswerkzeugen enthalten ist.  
  
3.  Registrieren Sie die Anwendung mit OLE.  
  
4.  Erstellen Sie ein `COleTemplateServer`\-Objekt als Member der Anwendungsklasse.  
  
5.  In `InitInstance`\-Memberfunktion der Anwendungsklasse sind folgende:  
  
    -   Schließen Sie das `COleTemplateServer`\-Objekt zu Dokumentvorlagen den an, indem Sie die Memberfunktion `ConnectTemplate` des Objekts aufrufen.  
  
    -   Rufen Sie die **COleTemplateServer::RegisterAll**\-Memberfunktion auf, um alle Klassenobjekte mit dem OLE\-System zu registrieren.  
  
    -   Rufen Sie `COleTemplateServer::UpdateRegistry` auf.  Der einzige Parameter in `UpdateRegistry` sollte `OAT_CONTAINER` sein, wenn die Anwendung nicht mit dem "\- Schalter \/Embedded" gestartet wird.  Dies registriert die Anwendung als Container, der Links zu eingebetteten Objekten kann.  
  
         Wenn die Anwendung mit dem "\- Schalter \/Embedded" gestartet wird, sollte sie das Hauptfenster nicht anzeigen, das einer Serveranwendung ähnelt.  
  
 Das [OCLIENT](../top/visual-cpp-samples.md) MFC\-OLE implementiert diese Funktion.  Ein Beispiel, wie dies durchgeführt wird, finden Sie die Funktion `InitInstance` in der OCLIENT.CPP\-Datei dieser Beispielanwendung.  
  
## Siehe auch  
 [Container](../mfc/containers.md)   
 [Server](../mfc/servers.md)