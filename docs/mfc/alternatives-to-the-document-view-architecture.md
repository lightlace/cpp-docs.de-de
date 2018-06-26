---
title: Alternativen zur Dokument-/ Ansichtarchitektur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- documents [MFC], applications without
- CDocument class [MFC], space requirements
- views [MFC], applications without
ms.assetid: 2c22f352-a137-45ce-9971-c142173496fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b99d8fb82b014fc2221f1ec1c0e6ad08ee75b4c
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930286"
---
# <a name="alternatives-to-the-documentview-architecture"></a>Alternativen zur Dokument-/Ansichtarchitektur
MFC-Anwendungen verwenden die Dokument-/Ansichtarchitektur normalerweise Informationen, die Dateiformate und die visuelle Darstellung der Daten für Benutzer zu verwalten. Für die meisten desktopanwendungen ist die Dokument-/Ansichtarchitektur Anwendungsarchitektur mit entsprechenden und effizient. Diese Architektur unterteilt die Daten anzeigen und in den meisten Fällen, die Anwendung vereinfacht und redundanten Code reduziert.  
  
 Dokument-/Ansichtarchitektur ist jedoch nicht für Situationen geeignet. Betrachten Sie diese Beispiele:  
  
-   Wenn Sie eine Anwendung geschrieben in C# für Windows portieren, empfiehlt es sich um den Port abgeschlossen ist, bevor die Dokument-/Ansichtarchitektur der Anwendung hinzufügen.  
  
-   Wenn Sie eine einfache Hilfsprogramm schreiben, stellen Sie möglicherweise fest, dass Sie ohne die Dokument-/Ansichtarchitektur ausführen können.  
  
-   Wenn der ursprüngliche Code bereits datenverwaltung mit Daten enthält ist anzeigen, Verschieben der Code zum Dokument/ansichtsmodel nicht der Aufwand, da die beiden zu trennen. Möglicherweise bevorzugen Sie den Code unverändert zu lassen.  
  
 Deaktivieren Sie zum Erstellen einer Anwendung, die nicht die Dokument-/Ansichtarchitektur verwendet, die **Unterstützung der Dokument-/Ansichtarchitektur-Architektur** Kontrollkästchen in Schritt 1 des Assistenten die MFC-Anwendung. Finden Sie unter [MFC-Anwendung-Assistent](../mfc/reference/mfc-application-wizard.md) Details.  
  
> [!NOTE]
>  Dialogfeldern basierende Anwendungen, die vom MFC-Anwendungs-Assistenten erstellte verwenden die Dokument-/Ansichtarchitektur nicht das **Unterstützung der Dokument-/Ansichtarchitektur-Architektur** Kontrollkästchen ist deaktiviert, wenn Sie den Dialogfeldtyp für die Anwendung auswählen.  
  
 Visual C++-Assistenten als auch die Quelle und das Dialogfeld-Editoren, arbeiten mit der generierten Anwendung genauso wie jede andere Assistenten generierte Anwendung. Die Anwendung unterstützen können, Symbolleisten, Bildlaufleisten und eine Statusleiste und verfügt über eine **zu** Feld. Registrieren Ihrer Anwendung keine Dokumentvorlagen, und es wird keine Dokumentklasse enthalten.  
  
 Beachten Sie, dass die generierte Anwendung eine Ansichtsklasse `CChildView`, abgeleitet von `CWnd`. MFC erstellt ein und platziert eine Instanz der Ansichtsklasse innerhalb der Rahmenfenster, die von der Anwendung erstellt. MFC erzwingt nach wie vor im Fenster Orchestrierungsansicht, da er vereinfacht das Positionieren und Verwalten von Inhalt für die Anwendung. Können Sie Zeichnungscode zum Hinzufügen der `OnPaint` Member dieser Klasse. Code sollte Bildlaufleisten in der Sicht anstelle des Frames, hinzufügen.  
  
 Da die Dokument-/Ansichtarchitektur von MFC bereitgestellten zur Implementierung zahlreicher grundlegenden Funktionen einer Anwendung zuständig ist, bedeutet seine Abwesenheit im Projekt an, dass Sie zum Implementieren von viele wichtiger Funktionen Ihrer Anwendung verantwortlich sind:  
  
-   Vom MFC-Anwendungs-Assistenten bereitgestellt wird, enthält das Menü für Ihre Anwendung nur **neu** und **beenden** Befehle auf den **Datei** Menü. (Die **neu** -Befehl wird nur für MDI-Anwendungen unterstützt, nicht SDI-Anwendungen ohne Dokument-/Ansichtarchitektur unterstützt.) Die generierten Menüressource wird eine Liste der zuletzt verwendeten Objekte (die zuletzt verwendet) nicht unterstützt.  
  
-   Sie müssen Handlerfunktionen und Implementierungen für alle Befehle, die die Anwendung unterstützt wird, einschließlich hinzufügen **öffnen** und **speichern** auf die **Datei** im Menü. MFC enthält normalerweise Code, um diese Funktionen unterstützen, aber diese Unterstützung eng an die Dokument-/Ansichtarchitektur gebunden ist.  
  
-   Die Symbolleiste für Ihre Anwendung, wird Wenn Sie angefordert minimiert werden.  
  
 Es wird dringend empfohlen, dass MFC-Anwendung des Assistenten zum Erstellen von Anwendungen ohne die Dokument-/Ansichtarchitektur, Verwendung da der Assistent eine korrekte MFC-Architektur sicherstellt. Wenn Sie vermeiden müssen, mit dem Assistenten gibt hier jedoch mehrere Ansätze zur Umgehung der Dokument-/Ansichtarchitektur in Ihrem Code:  
  
-   Behandeln Sie das Dokument als eine nicht verwendete Erweiterung, und implementieren Sie Ihre Datenverwaltungscode in Ansichtsklasse, wie oben beschrieben. Mehraufwand für das Dokument ist relativ niedrig. Ein einzelnes [CDocument](../mfc/reference/cdocument-class.md) Objekt verursacht eine kleine Menge an Mehraufwand selbst sowie kleine Mehraufwand `CDocument`des Basisklassen, [CCmdTarget](../mfc/reference/ccmdtarget-class.md) und [CObject](../mfc/reference/cobject-class.md). Beide Klassen sind klein.  
  
     Deklariert `CDocument`:  
  
    -   Zwei `CString` Objekte.  
  
    -   Drei **BOOL**s.  
  
    -   Eine `CDocTemplate` Zeiger.  
  
    -   Ein `CPtrList` Objekt, das eine Liste der Ansichten für das Dokument enthält.  
  
     Außerdem erfordert das Dokument die Zeitspanne, um das Document-Objekt, dessen Sichtobjekte eines Rahmenfensters und ein Dokumentobjekt für die Vorlage zu erstellen.  
  
-   Behandeln Sie das Dokument und die Ansicht als nicht verwendete Anhänge an. Fügen Sie Ihrer datenverwaltungs- und Code zum Zeichnen in der Ansicht, anstatt das Rahmenfenster. Dieser Ansatz ist näher an der Programmiersprache C-Programmiermodell.  
  
-   Überschreiben Sie die Teile des MFC-Frameworks, die das Dokument und die Ansicht, um zu vermeiden, erstellen sie überhaupt zu erstellen. Der Erstellungsvorgang für Dokument beginnt mit einem Aufruf von `CWinApp::AddDocTemplate`. Entfernen Sie diesen Aufruf aus Ihrer Anwendungsklasse `InitInstance` Member-Funktion, und erstellen Sie stattdessen in einem Rahmenfenster `InitInstance` selbst. Fügen Sie Ihrer Datenverwaltungscode in Ihre Rahmenfenster (Klasse). Wird der Erstellungsvorgang für Dokumente und Ansichten im veranschaulicht [Dokument-/Ansichtarchitektur Erstellung](../mfc/document-view-creation.md). Dies ist mehr Arbeit, und ein tieferes Verständnis über das Framework erfordert, aber Sie vollständig aus der Dokument-/Ansichtarchitektur Aufwand freigegeben.  
  
 Der Artikel [MFC: Verwenden von Datenbankklassen ohne Dokumente und Ansichten](../data/mfc-using-database-classes-without-documents-and-views.md) enthält mehr als eine konkrete Beispiele für Dokument-/Ansichtarchitektur alternativen im Kontext von datenbankanwendungen.  
  
## <a name="see-also"></a>Siehe auch  
 [Dokument-/Ansichtsarchitektur](../mfc/document-view-architecture.md)

