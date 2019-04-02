---
title: 'Container: Erweiterte Funktionen'
ms.date: 11/04/2016
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
ms.openlocfilehash: 350431975a4335fc06e436237b7e0d3388faab64
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58769562"
---
# <a name="containers-advanced-features"></a>Container: Erweiterte Funktionen

Dieser Artikel beschreibt die erforderlichen Schritte zum Optionaler erweiterter Features in vorhandenen containeranwendungen zu integrieren. Diese Funktionen sind:

- [Eine Anwendung, die einen Container und einem Server befindet](#_core_creating_a_container_server_application)

- [Ein OLE-Links, um ein eingebettetes Objekt](#_core_links_to_embedded_objects)

##  <a name="_core_creating_a_container_server_application"></a> Erstellen einer Container/Server-Anwendung

Eine Container/Server-Anwendung ist eine Anwendung, die als Container und einem Server fungiert. Microsoft Word für Windows ist ein Beispiel hierfür. Sie können Word für Windows-Dokumente in anderen Anwendungen einbetten, und können auch das Einbetten von Elementen in Word für Windows-Dokumenten. Der Prozess zum Ändern Ihrer Anwendung mit Containern werden sowohl für einen Container als auch für einen vollständigen Server (die eine Kombination aus Container/Miniserver-Anwendung kann nicht erstellt werden) ähnelt der Vorgehensweise zum Erstellen eines vollständigen Servers.

Der Artikel [Server: Implementieren eines Servers](../mfc/servers-implementing-a-server.md) wird eine Reihe erforderlicher Aufgaben zum Implementieren einer Serveranwendung aufgeführt. Wenn Sie eine containeranwendung in einem Container/Server-Anwendung konvertieren, müssen Sie zum Ausführen einiger dieser Aufgaben, Hinzufügen von Code in den Container. Die folgende Liste enthält wichtige Aspekte berücksichtigen:

- Der Containercode, der bereits vom Anwendungs-Assistenten erstellte initialisiert die OLE-Subsystem an. Sie müssen nicht ändern oder Hinzufügen von nichts für, unterstützen.

- Ganz egal, wo die Basisklasse einer Klasse Dokument ist `COleDocument`, ändern Sie die Basisklasse zum `COleServerDoc`.

- Außer Kraft setzen `COleClientItem::CanActivate` um zu vermeiden, Elemente direkt bearbeiten, während der Server selbst zum direkten Bearbeiten verwendet wird.

   Beispielsweise die MFC-OLE-Beispiel [OCLIENT](../overview/visual-cpp-samples.md) ein Element, das von der Container/Server-Anwendung erstellt haben, sind eingebettet. Öffnen Sie die OCLIENT-Anwendung, und ein direktes Bearbeiten des Elements, die von der Container/Server-Anwendung erstellt. Während der Bearbeitung Ihrer Anwendung-Element, möchten, müssen Sie ein Element, das von der MFC-OLE-Beispiel erstellten einbetten möchten [HIERSVR](../overview/visual-cpp-samples.md). Zu diesem Zweck können Sie keine direkte Aktivierung. Sie müssen vollständig HIERSVR zum Aktivieren dieses Element öffnen. Da die Microsoft Foundation Class Library diese OLE-Funktion nicht unterstützt, überschreiben `COleClientItem::CanActivate` können Sie für diese Situation überprüfen und zu verhindern, dass einen möglichen zur Laufzeit Fehler in Ihrer Anwendung.

Wenn Sie eine neue Anwendung erstellen und diese als ein Container/Server-Anwendung verwendet werden soll, wählen Sie, dass die Option im Dialogfeld OLE-Optionen in der Anwendungs-Assistent und diese Unterstützung automatisch erstellt werden. Weitere Informationen finden Sie im Artikel [Übersicht: Erstellen eines ActiveX-Steuerelementcontainers](../mfc/reference/creating-an-mfc-activex-control-container.md). Informationen über MFC-Beispiele finden Sie in der MFC-Beispiele.

Beachten Sie, dass eine MDI-Anwendung kann nicht in sich selbst eingefügt. Eine Anwendung, die ein Container/Server kann nicht in sich selbst eingefügt werden, es sei denn, es einer SDI-Anwendung ist.

##  <a name="_core_links_to_embedded_objects"></a> Links zu eingebettete Objekte

Die Links, um eingebettete Objekte Feature ermöglicht Benutzern, ein Dokument mit einer OLE-Links, um ein eingebettetes Objekt innerhalb Ihrer Anwendung mit Containern zu erstellen. Erstellen Sie z. B. ein Dokument in einem Textverarbeitungsprogramm, die eine eingebettete Tabelle enthält. Wenn Ihre Anwendung Links zu eingebetteten Objekten unterstützt, konnte es einen Link zu der Tabelle, in das Textverarbeitungsprogramm Dokument enthaltenen eingefügt werden. Diese Funktion kann Ihre Anwendung verwenden Sie die Informationen in der Tabelle enthalten sind, ohne zu wissen, wo das Textverarbeitungsprogramm ursprünglich herkommt.

#### <a name="to-link-to-embedded-objects-in-your-application"></a>So verknüpfen Sie mit eingebetteten Objekten in Ihrer Anwendung

1. Leiten Sie die Dokumentklasse aus `COleLinkingDoc` anstelle von `COleDocument`.

1. Erstellen Sie eine OLE-Klassen-ID (**CLSID**) für Ihre Anwendung mithilfe der Klasse-ID-Generator in der OLE-Entwicklungstools enthalten.

1. Registrieren Sie die Anwendung, mit OLE.

1. Erstellen Sie eine `COleTemplateServer` -Objekt als Member der Anwendungsklasse.

1. In Ihrer Anwendungsklasse `InitInstance` Member funktioniert, gehen Sie folgendermaßen vor:

   - Verbinden Ihrer `COleTemplateServer` Objekt, das Ihren Dokumentvorlagen durch Aufrufen des Objekts `ConnectTemplate` Member-Funktion.

   - Rufen Sie die `COleTemplateServer::RegisterAll` Memberfunktion versucht, alle Objekte der Klasse mit dem OLE-System zu registrieren.

   - Rufen Sie `COleTemplateServer::UpdateRegistry` auf. Der einzige Parameter `UpdateRegistry` muss *OAT_CONTAINER* , wenn die Anwendung nicht mit dem Schalter "/ Embedded" gestartet wird. Dadurch wird die Anwendung als Container, der Links zu eingebetteten Objekten unterstützt werden registriert.

         If the application is launched with the "/Embedded" switch, it should not show its main window, similar to a server application.

Das MFC-OLE-Beispiel [OCLIENT](../overview/visual-cpp-samples.md) diese Funktion implementiert. Ein Beispiel dafür, wie dies funktioniert, finden Sie unter den `InitInstance` Funktion in der *OCLIENT. CPP* Datei dieser beispielanwendung.

## <a name="see-also"></a>Siehe auch

[Container](../mfc/containers.md)<br/>
[Server](../mfc/servers.md)
