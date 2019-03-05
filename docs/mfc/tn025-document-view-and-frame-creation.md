---
title: 'TN025: Dokument, Ansicht und dem Frame-Erstellung'
ms.date: 11/04/2016
f1_keywords:
- vc.creation
helpviewer_keywords:
- documents [MFC], view and frame creation
- TN025
ms.assetid: 09254d72-6e1d-43db-80e9-693887dbeda2
ms.openlocfilehash: 4958e7c4ca2c3cf9eed6420d72d0399fa112098d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57284683"
---
# <a name="tn025-document-view-and-frame-creation"></a>TN025: Dokument, Ansicht und dem Frame-Erstellung

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.

Dieser Hinweis beschreibt die Erstellung und des Besitzes Probleme für WinApps, DocTemplates, Dokumente, Bilder und Ansichten.

## <a name="winapp"></a>WinApp

Es gibt ein `CWinApp` Objekt im System.

Wird statisch erstellt und initialisiert, indem interne Implementierung des Frameworks `WinMain`. Durch Ableiten von `CWinApp` um nichts nützliches tun (Ausnahme: MFC-Erweiterungs-DLLs sollten keine `CWinApp` Instanz – Initialisierung erfolgt in `DllMain` stattdessen).

Die `CWinApp` Objekt besitzt eine Liste von Dokumentvorlagen (eine `CPtrList`). Es gibt eine oder mehrere Dokumentvorlage pro Anwendung. DocTemplates werden in der Regel aus der Ressourcendatei (d. h. ein Zeichenfolgenarray) geladen, im `CWinApp::InitInstance`.

```
pTemplate = new CDocTemplate(IDR_MYDOCUMENT, ...);

AddDocTemplate(pTemplate);
```

Die `CWinApp` Objekt besitzt alle Rahmenfenster der Anwendung. Das Hauptrahmenfenster für die Anwendung gespeichert werden sollen, im `CWinApp::m_pMainWnd`; in der Regel legen Sie *M_pMainWnd* in die `InitInstance` Implementierung, wenn Sie AppWizard übernehmen das für Sie nicht können, haben. Für Einzeldokumentoberfläche (SDI) Dies ist eine `CFrameWnd` , die als das Rahmenfenster der Hauptthread der Anwendung als auch der einzige Dokumentrahmenfenster dient. Bei mehrfachen Dokumentschnittstelle (MDI) ist dies ein MDI-Frame (Klasse `CMDIFrameWnd`), die als das Hauptfenster der Anwendungsrahmenfenster, das das untergeordnete Element enthält dient `CFrameWnd`s. Jedes untergeordnete Fenster gehört der Klasse `CMDIChildWnd` (abgeleitet von `CFrameWnd`) und dient als eine der vielen Dokumentrahmenfenster.

## <a name="doctemplates"></a>DocTemplates

Die `CDocTemplate` der Ersteller und-Manager von Dokumenten. Er besitzt die Dokumenten, die erstellt wird. Wenn Ihre Anwendung den unten beschriebenen ressourcenbasierte-Ansatz verwendet, es müssen nicht für die Ableitung `CDocTemplate`.

Für eine SDI-Anwendung, die Klasse `CSingleDocTemplate` verfolgt des einem geöffneten Dokument. Für eine MDI-Anwendung, die Klasse `CMultiDocTemplate` behält eine Liste (ein `CPtrList`) aller geöffneten Dokumente aus dieser Vorlage erstellt wurde. `CDocTemplate::AddDocument` und `CDocTemplate::RemoveDocument` stellen die virtuellen Funktionen zum Hinzufügen oder entfernen ein Dokument aus der Vorlage. `CDocTemplate` ist ein Freund von `CDocument` daher können wir die geschützte festlegen `CDocument::m_pDocTemplate` Gegenzeiger auf wieder in die Doc-Vorlage zu verweisen, die das Dokument erstellt.

`CWinApp` Standardmäßig behandelt `OnFileOpen` -Implementierung, die wiederum alle Doc Vorlagen abfragt. Die Implementierung umfasst bereits geöffneten Dokumenten suchen und zu entscheiden, welches format, um neue Dokumente in zu öffnen.

`CDocTemplate` verwaltet die UI-Bindung für Dokumente und Bilder.

`CDocTemplate` zählt die Anzahl der unbenannten Dokumente.

## <a name="cdocument"></a>CDocument

Ein `CDocument` ist im Besitz einer `CDocTemplate`.

Dokumente enthält eine Liste der derzeit Ansichten öffnen (abgeleitet `CView`) anzeigen, die das Dokument (einem `CPtrList`).

Dokumente werden nicht erstellt/zerstört die Ansichten, aber sie sind miteinander angefügt, nachdem sie erstellt wurden. Wenn ein Dokument geschlossen ist (d. h. bis Datei/schließen), alle angefügten Ansichten werden geschlossen. Wenn die letzte Ansicht für ein Dokument geschlossen wird (d. h., Fenster/schließen), wird das Dokument geschlossen werden.

Die `CDocument::AddView`, `RemoveView` Schnittstelle wird verwendet, um die Sicht verwalten. `CDocument` ist ein Freund von `CView` daher legen wir fest, kann die `CView::m_pDocument` Gegenzeiger.

## <a name="cframewnd"></a>CFrameWnd

Ein `CFrameWnd` (auch bekannt als ein Frame) übernimmt die gleiche Rolle wie MFC 1.0, aber jetzt die `CFrameWnd` Klasse soll in vielen Fällen verwendet werden, ohne eine neue Klasse ableiten. Die abgeleiteten Klassen `CMDIFrameWnd` und `CMDIChildWnd` auch verbessert, damit viele Standardbefehle bereits implementiert werden.

Die `CFrameWnd` dient zum Erstellen von Fenstern im Clientbereich des Frames. Es ist normalerweise ein Hauptfenster der Clientbereich des Frames.

Für eine MDI-Rahmenfenster wird der Clientbereich mit dem MDICLIENT-Steuerelement gefüllt wiederum das übergeordnete Element der alle untergeordneten MDI-Rahmenfenster ist. Für eine SDI-Rahmenfensters oder eines untergeordneten MDI-Frame-Fensters, das den Clientbereich in der Regel mit gefüllt ist eine `CView`-Window-Objekt abgeleitet. Im Fall von `CSplitterWnd`, der Clientbereich der Ansicht wird gefüllt, mit der `CSplitterWnd` Window-Objekt, und die `CView`-abgeleiteten Fensterobjekten (einer pro Teilbereich) werden als untergeordnete Fenster eines erstellt die `CSplitterWnd`.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
