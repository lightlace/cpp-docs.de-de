---
title: Active Documents für das Internet | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- active documents [MFC], creating
- application wizards [MFC], active documents
- active documents [MFC], programming steps
- application wizards [MFC]
- active documents [MFC], using application wizards
ms.assetid: a46bd8a0-e27a-4116-b1bf-dacdb7ae78d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43bb54f36f57702d43cf065604641124e38ed053
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33334885"
---
# <a name="active-documents-on-the-internet"></a>Active Documents für das Internet
Aktive Dokumente bieten eine Erweiterung für herkömmliche eingebettete Objekte. Aktive Dokumente möglicherweise mehrseitigen und werden in den gesamten Clientbereich angezeigt. Sie herkömmliche Menü-Aushandlung und direkte als auch in einem geöffneten Fenster in der Serveranwendung bearbeitet werden können. Anstatt als kleine Rechteck von einem schraffierten Rahmen umgeben sind aktive Dokumente vollständigen Frame und immer direkt aktiv.  
  
 Aktive Dokumente können in einem Container wie den Microsoft Office Binder, die eine Möglichkeit zum Erstellen eines zusammengesetzten Dokuments verschiedener Dokumenttypen wie Excel, Word, bestehend aus angezeigt werden, und Ihre benutzerdefinierten Dokumenttyp, von denen jeder sein kann bearbeitet vollständigen Frame. Aktive Dokumente können auch in einem Browser wie Microsoft Internet Explorer angezeigt werden, die einen Active Document-Container ist.  
  
 **Aktives Dokument bietet folgende Vorteile:**  
  
-   Dokumente können angezeigt werden, vollständigen Frame, in der gesamten Client-Fenster.  
  
-   Dokumente können in einem separaten Anwendungsfenster geöffnet werden.  
  
     Für das Dokument zu öffnen das Hilfsprogramm muss vorhanden sein, auf dem Client oder einzeln heruntergeladen werden, bevor die Anwendung ausgeführt werden kann. Eingeschränkten Funktionalität (Word, PowerPoint und Excel Viewer für ihre Dokumente bereitstellen) bieten möglicherweise ein Viewer geschrieben werden. Die vollständige Version der Anwendung bieten vollständige Unterstützung für das Bearbeiten.  
  
-   Dokumente sind immer in-Place aktiv.  
  
-   Befehle im Menü aufgerufen wird, aus dem Container können in Ihr Dokument weitergeleitet werden.  
  
-   Dokumente können in einem Webbrowser angezeigt werden. Dies bietet eine nahtlose Integration zwischen Dokumenten und anderen Webseiten.  
  
     Ein Benutzer kann eine HTML-Webseite, eine Excel-Kalkulationstabelle, durchsuchen und zu einem Dokument, das Sie geschrieben haben, verwenden von MFC unterstützen für aktive Dokumente. Der Benutzer kann mithilfe der vertrauten Weboberfläche, wie die Browser-Switches nahtlos zwischen den Menüs und Ansichten der HTML-Seite, Excel und Ihre Anwendung Dokument navigieren.  
  
-   Alle Anwendungen werden in einem allgemeinen Frame angezeigt.  
  
## <a name="requirements-for-active-documents"></a>Anforderungen für aktive Dokumente  
 Die in der folgenden Tabelle aufgelisteten Schnittstellen gehören Schnittstellen, die bereits für eingebettete Server erforderlich sind und mehrere neue Schnittstellen, die spezifisch für aktive Dokumente. MFC stellt standardimplementierungen für die meisten dieser Schnittstellen in den [COleServerDoc](../mfc/reference/coleserverdoc-class.md) Klasse.  
  
|Ein Dokument...|Implementiert diese Schnittstellen|  
|-------------------------|---------------------------------|  
|Verwendet Verbunddateien als Speichermechanismus.|`IPersistStorage`|  
|Unterstützt die grundlegenden Einbetten von Funktionen für aktive Dokumente, einschließlich aus Datei erstellen.|`IPersistFile`, `IOleObject` und `IDataObject`.|  
|Unterstützt direkte Aktivierung.|`IOleInPlaceObject` und `IOleInPlaceActiveObject` (unter Verwendung des Containers `IOleInPlaceSite` und **IOleInPlaceFrame** Schnittstellen).|  
|Unterstützt das aktive Dokument-Erweiterungen, die diese neuen Schnittstellen einschließen. Einige Schnittstellen sind optional.|`IOleDocument`, `IOleDocumentView`, `IOleCommandTarget` und `IPrint`.|  
  
 MFC bietet Unterstützung für die vorhandenen eingebetteten Serversupport, um aktive Dokumente zu erweitern.  
  
## <a name="add-active-document-support-to-a-new-application"></a>Active Document-Unterstützung in eine neue Anwendung hinzufügen  
 So erstellen Sie eine neue Anwendung mit Active Document-Unterstützung: In der MFC-Anwendung-Assistent auf die **zusammengesetzten Dokument unterstützen** Seite, wählen Sie unter "Select Verbunddokumente" **Vollserver** oder  **Container/Vollserver**, und wählen Sie unter "Weitere Optionen auswählen" das Kontrollkästchen für **Active Document-Server**.  
  
##  <a name="_core_convert_an_existing_mfc_in.2d.process_server_to_an_activex_document_server"></a> Konvertieren einer vorhandenen MFC-In-Process-Servers mit einem aktiven Dokument-Server  
 Wenn Ihre Anwendung mit einer Version von Visual C++ vor Version 4.2 erstellt wurde, und es bereits ein in-Process-Server ist, können Sie Active Document-Unterstützung hinzufügen, indem Sie Änderungen in der folgenden Klassen:  
  
|Klassentyp|Früher abgeleitet wurde.|Ableiten von|  
|----------------|---------------------------|---------------------------|  
|In-Place-Frame|`COleIPFrameWnd`|**COleDocIPFrameWnd**|  
|Element|`COleServerItem`|`CDocObjectServerItem`|  
  
 Sie werden auch ändern, wie Informationen in der Registrierung eingegeben wird und mehrere andere Änderungen vornehmen. Wenn die Anwendung derzeit keine Unterstützung der COM-Komponenten verfügt, können Sie Server-Unterstützung durch Ausführen des Assistenten für die Anwendung und die Integration des COM-Komponente-spezifische Codes in der vorhandenen Anwendung hinzufügen.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Internetprogrammierungsaufgaben](../mfc/mfc-internet-programming-tasks.md)   
 [Grundlagen der MFC-Internetprogrammierung](../mfc/mfc-internet-programming-basics.md)

