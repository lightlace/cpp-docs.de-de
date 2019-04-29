---
title: Alternativen für die Dokument-/ Ansichtarchitektur
ms.date: 11/04/2016
helpviewer_keywords:
- documents [MFC], applications without
- CDocument class [MFC], space requirements
- views [MFC], applications without
ms.assetid: 2c22f352-a137-45ce-9971-c142173496fb
ms.openlocfilehash: 98bb4de2f6d1a43fc1958a0fcbaafa1ac0af82a3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394714"
---
# <a name="alternatives-to-the-documentview-architecture"></a>Alternativen zur Dokument-/Ansichtarchitektur

MFC-Anwendungen verwenden die Dokument-/Ansichtarchitektur normalerweise zum Verwalten von Informationen, Dateiformate und die visuelle Darstellung der Daten für Benutzer. Für die meisten desktopanwendungen ist die Dokument-/Ansichtarchitektur Anwendungsarchitektur mit entsprechenden und effizient. Diese Architektur unterteilt die Daten und der Anzeige und in den meisten Fällen, die Anwendung vereinfacht und reduziert redundanten Code.

Die Dokument-/Ansichtarchitektur ist jedoch nicht für Situationen geeignet. Betrachten Sie diese Beispiele:

- Wenn Sie eine in C# für Windows geschriebene Anwendung portieren, möchten Sie den Port abgeschlossen ist, bevor Sie Ihre Anwendung Dokument-/Ansicht-Unterstützung hinzugefügt.

- Wenn Sie ein einfaches Hilfsprogramm schreiben, werden Sie möglicherweise fest, dass Sie die Dokument-/Ansichtarchitektur verzichten können.

- Wenn Sie der ursprüngliche Code bereits die datenverwaltung mit Daten kombiniert ist angezeigt wird, Verschieben der Code für die Dokument-/Ansicht-Modell nicht der Mühe Wert, da die beiden zu trennen, müssen. Möglicherweise möchten Sie den Code unverändert lassen.

Deaktivieren Sie zum Erstellen einer Anwendung, die nicht die Dokument-/Ansichtarchitektur verwendet, die **Unterstützung für die Dokument-/Ansicht** in Schritt 1 des Assistenten für MFC-Anwendung das Kontrollkästchen. Finden Sie unter [MFS-Anwendungsassistenten](../mfc/reference/mfc-application-wizard.md) Details.

> [!NOTE]
>  Dialogfeld-basierten Anwendungen, die vom MFC-Anwendungs-Assistenten erzeugte verwenden Sie nicht die Dokument-/Ansichtarchitektur daher **Unterstützung für die Dokument-/Ansicht** Kontrollkästchen ist deaktiviert, wenn Sie den Dialogfeldtyp für die Anwendung auswählen.

Die Visual C++-Assistenten sowie die Quell- und Dialog-Editoren, arbeiten mit der generierten Anwendung genauso wie bei jeder anderen Assistenten generierte Anwendung. Die Anwendung unterstützen, Symbolleisten, Bildlaufleisten und eine Statusleiste und verfügt über eine **zu** Feld. Registrieren Ihrer Anwendung keine Dokumentvorlagen, und eine "Document"-Klasse nicht enthält.

Beachten Sie, dass Ihre Anwendung mit generierte Ansichtsklasse, `CChildView`, abgeleitet von `CWnd`. MFC erstellt und eine Instanz der Ansichtsklasse innerhalb der von Ihrer Anwendung erstellten Rahmenfenster positioniert. MFC erzwingt nach wie vor ein Ansichtsfenster, da sie vereinfacht die Positionierung und der Inhalt der Anwendung verwalten. Sie können Code zum Zeichnen von zum Hinzufügen der `OnPaint` Member dieser Klasse. Ihr Code sollte Bildlaufleisten für die Ansicht als zum Frame hinzufügen.

Da die Dokument-/Ansichtarchitektur von MFC bereitgestellten zur Implementierung zahlreicher grundlegenden Funktionen einer Anwendung verantwortlich ist, bedeutet die fehlende Methode in Ihrem Projekt, dass Sie für viele wichtige Features Ihrer Anwendung implementieren, sind:

- Vom MFC-Anwendungs-Assistenten bereitgestellt wird, enthält das Menü für Ihre Anwendung nur **neu** und **beenden** von Befehlen auf die **Datei** Menü. (Die **neu** -Befehl wird nur für MDI-Anwendungen unterstützt, nicht SDI-Anwendungen ohne Dokumente und Ansichten zu unterstützen.) Die generierte Menüressource wird eine Liste der zuletzt verwendeten Objekte (die zuletzt verwendet) nicht unterstützt.

- Müssen Sie Ereignishandler-Funktionen und Implementierungen für alle Befehle, die Ihre Anwendung unterstützen, einschließlich, hinzufügen **öffnen** und **speichern** auf die **Datei** Menü. MFC enthält normalerweise Code, um diese Funktionen unterstützen, aber diese Unterstützung eng an die Dokument-/Ansichtarchitektur gebunden ist.

- Die Symbolleiste für Ihre Anwendung, werden Wenn Sie angefordert haben, minimal sein.

Es wird dringend empfohlen, dass MFC-Anwendung des Assistenten zum Erstellen von Anwendungen ohne die Dokument-/Ansichtarchitektur, Verwendung da der Assistent eine korrekte MFC-befehlsarchitektur gewährleistet ist. Wenn Sie vermeiden müssen, mit dem Assistenten, gibt hier jedoch mehrere Ansätze zur Umgehung der Dokument-/Ansichtarchitektur in Ihrem Code:

- Behandeln Sie das Dokument als eine nicht verwendete Erweiterung, und implementieren Sie Datenverwaltungscode, in der Ansichtsklasse, wie oben. Mehraufwand für das Dokument ist relativ niedrig. Ein einzelnes [CDocument](../mfc/reference/cdocument-class.md) Objekt verursacht ein geringes Maß an Mehraufwand selbst sowie den kleinen Mehraufwand `CDocument`der Basisklassen [CCmdTarget](../mfc/reference/ccmdtarget-class.md) und [CObject](../mfc/reference/cobject-class.md). Beide Klassen sind klein.

   Deklariert `CDocument`:

  - Zwei `CString` Objekte.

  - Drei **"bool"** s.

  - Eine `CDocTemplate` Zeiger.

  - Eine `CPtrList` -Objekt, das eine Liste der Ansichten des Dokuments enthält.

  Außerdem erfordert das Dokument die Zeitspanne, um das Document-Objekt, dessen Objekte anzeigen, ein Rahmenfenster und ein Dokumentobjekt für die Vorlage zu erstellen.

- Behandeln Sie das Dokument und die Ansicht als nicht verwendete Anhänge an. Fügen Sie Ihr die datenverwaltung und den Code zum Zeichnen in der Ansicht, anstatt das Rahmenfenster. Dieser Ansatz ist näher an der Programmiersprache C-Programmiermodell.

- Überschreiben Sie die Teile des MFC-Frameworks, die das Dokument und Ansicht, um zu vermeiden, erstellen sie überhaupt zu erstellen. Der Dokument-Erstellungsprozess beginnt mit einem Aufruf von `CWinApp::AddDocTemplate`. Entfernen Sie diesen Aufruf aus Ihrer Anwendungsklasse `InitInstance` Member Funktion, und erstellen Sie stattdessen ein Rahmenfenster in `InitInstance` selbst. Fügen Sie Ihren Data Management-Code in Ihr Rahmenfenster (Klasse) ein. Der Erstellungsvorgang für Dokumente und Ansichten wird im veranschaulicht [Dokument-/Ansicht-Erstellung](../mfc/document-view-creation.md). Dies ist mehr Arbeit, und erfordert ein tieferes Verständnis von Framework, aber Sie vollständig aus der Aufwand für die Dokument-/Ansicht freigegeben.

Der Artikel [MFC: Verwenden von Datenbankklassen ohne Dokumente und Ansichten](../data/mfc-using-database-classes-without-documents-and-views.md) konkreter Beispiele von Dokument/Ansicht alternativen im Kontext von datenbankanwendungen.

## <a name="see-also"></a>Siehe auch

[Dokument-/Ansichtsarchitektur](../mfc/document-view-architecture.md)
