---
title: 'Container: Erweiterte Funktionen | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- links [MFC], to embedded OLE objects
- containers [MFC], links to embedded OLE objects
- containers [MFC], advanced features
- container/server applications [MFC]
- embedded objects [MFC]
- OLE controls [MFC], containers
- OLE containers [MFC], advanced features
- server/container applications [MFC]
- containers [MFC], container applications
ms.assetid: 221fd99c-b138-40fa-ad6a-974e3b3ad1f8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4e79b1c88996e835a907129fa5810d4c4dca0770
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="containers-advanced-features"></a>Container: Erweiterte Funktionen
Dieser Artikel beschreibt die erforderlichen Schritte zum optionale erweiterte Funktionen in vorhandenen Container-Anwendungen zu integrieren. Diese Funktionen sind:  
  
-   [Eine Anwendung, einen Container und einem server](#_core_creating_a_container_server_application)  
  
-   [Eine OLE-Verknüpfung, um ein eingebettetes Objekt](#_core_links_to_embedded_objects)  
  
##  <a name="_core_creating_a_container_server_application"></a>Erstellen einer Container/Server-Anwendung  
 Eine Container/Server-Anwendung ist eine Anwendung, die als Container und Server fungiert. Microsoft Word für Windows ist ein Beispiel hierfür. Sie können für Windows Word-Dokumente in anderen Anwendungen einbetten, und Sie können Elemente auch in Word für Windows-Dokumente einbetten. Der Prozess zum Ändern Ihrer Steuerelementcontainer-anwendungskennworts ist ein Container und einen vollständigen Server (die eine Kombination aus Container/Miniserver-Anwendung kann nicht erstellt werden) ähnelt der Erstellungsprozess für einen vollständigen Server.  
  
 Der Artikel [Server: Implementieren eines Servers](../mfc/servers-implementing-a-server.md) führt eine Reihe von Aufgaben zum Implementieren einer Serveranwendung erforderlich sind. Wenn Sie eine Steuerelementcontainer-Anwendung auf einen Container/Server-Anwendung konvertieren, müssen Sie einige dieser Aufgaben ausführen Hinzufügen von Code für den Container. Die folgende Liste enthält wichtige folgende Aspekte berücksichtigen:  
  
-   Der Containercode, der bereits vom Anwendungs-Assistenten erstellte initialisiert die OLE-Subsystem. Sie müssen nicht ändern oder Hinzufügen von weiteren, unterstützen.  
  
-   Die Basisklasse einer Dokumentklasse wo ist `COleDocument`, ändern Sie die Basisklasse um `COleServerDoc`.  
  
-   Überschreiben Sie `COleClientItem::CanActivate` , vermeiden Sie Elemente direkt bearbeiten, während der Server selbst zum direkten Bearbeiten verwendet wird.  
  
     Angenommen, die MFC-OLE-Beispiel [OCLIENT](../visual-cpp-samples.md) verfügt über ein Element erstellt, indem die Container/Server-Anwendung eingebettet. Öffnen Sie die OCLIENT-Anwendung, und direkte Bearbeiten des Elements, das von der Container/Server-Anwendung erstellt. Beim Bearbeiten Ihrer Anwendung Element können Sie entscheiden, Sie ein MFC-OLE-Beispiel erstellte Element einbetten möchten [HIERSVR](../visual-cpp-samples.md). Zu diesem Zweck können Sie keine direkte Aktivierung. Sie müssen vollständig HIERSVR aktivieren Sie dieses Element öffnen. Da die Microsoft Foundation Class Library dieses OLE-Feature nicht unterstützt wird, überschreiben `COleClientItem::CanActivate` können Sie in dieser Situation überprüfen und zu verhindern, dass einen möglichen zur Laufzeit Fehler in der Anwendung.  
  
 Wenn Sie eine neue Anwendung erstellen und als einen Container/Server-Anwendung verwendet werden soll, wählen Sie die Option im Dialogfeld OLE-Optionen in der Anwendungs-Assistent und diese Unterstützung wird automatisch erstellt. Weitere Informationen finden Sie im Artikel [Übersicht: Erstellen eines ActiveX-Steuerelementcontainers](../mfc/reference/creating-an-mfc-activex-control-container.md). Informationen über MFC-Beispiele finden Sie unter MFC-Beispiele.  
  
 Beachten Sie, dass Sie eine MDI-Anwendung in sich selbst einfügen können. Eine Anwendung, einem Container/Server kann nicht in sich selbst eingefügt werden, wenn sie eine SDI-Anwendung ist.  
  
##  <a name="_core_links_to_embedded_objects"></a>Links zu eingebetteten Objekten  
 Die Links, um eingebettete Objekte Feature ermöglicht einem Benutzer zum Erstellen eines Dokuments mit einer OLE-Link auf ein eingebettetes Objekt in Ihre containeranwendung. Erstellen Sie z. B. ein Dokument in ein Textverarbeitungsprogramm, das eine eingebettete Tabelle enthält. Wenn Ihre Anwendung Links zu eingebetteten Objekten unterstützt, konnte einen Link in der Kalkulationstabelle in das Textverarbeitungsprogramm Dokument enthaltenen eingefügt werden. Diese Funktion ermöglicht die Anwendung verwendet die Informationen in der Tabelle enthalten sind, ohne zu wissen, wo das Textverarbeitungsprogramm ursprünglich wurde erreicht.  
  
#### <a name="to-link-to-embedded-objects-in-your-application"></a>Verknüpfen mit eingebetteten Objekten in der Anwendung  
  
1.  Leiten Sie eine Dokumentklasse aus `COleLinkingDoc` anstelle von `COleDocument`.  
  
2.  Erstellen Sie eine OLE-Klassen-ID (**CLSID**) für die Anwendung unter Verwendung der Klasse-ID-Generator in der OLE-Entwicklungstools enthalten.  
  
3.  Registrieren Sie die Anwendung mit OLE an.  
  
4.  Erstellen einer `COleTemplateServer` Objekt als Mitglied der Anwendungsserver-Klasse.  
  
5.  In der Anwendungsklasse `InitInstance` Member-Funktion, gehen Sie folgendermaßen vor:  
  
    -   Verbinden der `COleTemplateServer` Objekt, das die Dokumentvorlagen durch Aufrufen des Objekts `ConnectTemplate` Memberfunktion.  
  
    -   Rufen Sie die **COleTemplateServer::RegisterAll** Memberfunktion versucht, alle Objekte der Klasse mit dem OLE-System zu registrieren.  
  
    -   Rufen Sie `COleTemplateServer::UpdateRegistry` auf. Der einzige Parameter `UpdateRegistry` muss `OAT_CONTAINER` , wenn die Anwendung nicht mit dem Schalter "/ eingebettete" gestartet wird. Dies registriert die Anwendung als Container, der Links auf eingebettete Objekte unterstützen kann.  
  
         Wenn die Anwendung mit dem Schalter "/ eingebettete" gestartet wird, sollte nicht das Hauptfenster ähnelt einer Serveranwendung angezeigt werden.  
  
 Das MFC-OLE-Beispiel [OCLIENT](../visual-cpp-samples.md) dieser Funktion implementiert. Ein Beispiel dafür, wie dies funktioniert, finden Sie unter der `InitInstance` -Funktion in der OCLIENT. Diese beispielanwendung CPP-Datei.  
  
## <a name="see-also"></a>Siehe auch  
 [Containers](../mfc/containers.md)   
 [Server](../mfc/servers.md)

