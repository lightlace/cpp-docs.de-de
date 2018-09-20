---
title: Beziehungen zwischen MFC-Objekten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, relationships between key objects
- objects [MFC], relationships
- relationships, MFC objects
- MFC object relationships
ms.assetid: 6e8f3b51-e80f-4d88-94c8-4c1e4ee163ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d2f42f754157a4fc2e3f3e1aa40f38477b982e16
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372482"
---
# <a name="relationships-among-mfc-objects"></a>Beziehungen zwischen MFC-Objekten

Damit der Erstellungsvorgang für Dokumente und Ansichten in der Sicht eingefügt werden, sollten Sie in einem laufenden Programm: ein Dokument, das Rahmenfenster verwendet, um die Ansicht zu speichern und die Ansicht, die dem Dokument zugeordnet.

- Ein Dokument behält eine Liste der Ansichten des Dokuments und einen Zeiger auf die Dokumentvorlage, die das Dokument erstellt.

- Eine Sicht führt einen Zeiger auf sein Dokument und ist ein untergeordnetes Element des übergeordneten Fensters Frame.

- Einem Dokumentrahmenfenster führt einen Zeiger auf die derzeit aktive Ansicht an.

- Eine Dokumentvorlage behält es sich um eine Liste der geöffneten Dokumente.

- Die Anwendung behält eine Liste ihrer Dokumentvorlagen.

- Windows behält den Überblick über alle offenen Fenster, damit sie Nachrichten senden kann.

Diese Beziehungen werden während der Erstellung der Dokument-/Ansicht eingerichtet. Die folgende Tabelle zeigt, wie Objekte in einem laufenden Programm auf andere Objekte zugreifen können. Jedes Objekt kann einen Zeiger auf das Anwendungsobjekt erhalten, durch Aufrufen der globalen Funktion [AfxGetApp](../mfc/reference/application-information-and-management.md#afxgetapp).

### <a name="gaining-access-to-other-objects-in-your-application"></a>Zugriff auf andere Objekte in Ihrer Anwendung

|Vom Objekt|Gewusst wie: Zugriff auf andere Objekte|
|-----------------|---------------------------------|
|Dokument|Verwendung [Sie GetFirstViewPosition](../mfc/reference/cdocument-class.md#getfirstviewposition) und [GetNextView](../mfc/reference/cdocument-class.md#getnextview) Ansichtsliste des Dokuments auf.<br /><br /> Rufen Sie [Sie GetDocTemplate](../mfc/reference/cdocument-class.md#getdoctemplate) um die Dokumentvorlage zu erhalten.|
|Ansicht|Rufen Sie [GetDocument](../mfc/reference/cview-class.md#getdocument) um das Dokument zu erhalten.<br /><br /> Rufen Sie [GetParentFrame](../mfc/reference/cwnd-class.md#getparentframe) um das Rahmenfenster zu erhalten.|
|Dokumentrahmenfenster|Rufen Sie [GetActiveView](../mfc/reference/cframewnd-class.md#getactiveview) zum Abrufen der aktuellen Ansicht.<br /><br /> Rufen Sie [Sie GetActiveDocument](../mfc/reference/cframewnd-class.md#getactivedocument) zum Abrufen der aktuellen Ansicht angefügten Dokuments.|
|MDI-Rahmenfenster|Rufen Sie [Sie MDIGetActive](../mfc/reference/cmdiframewnd-class.md#mdigetactive) abzurufenden das aktuell aktive [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md).|

In der Regel ein Rahmenfenster hat eine Sicht, aber in einigen Fällen enthält das gleiche Rahmenfenster wie Splitterfenster, mehrere Ansichten. Das Rahmenfenster führt einen Zeiger auf die derzeit aktive Ansicht; der Zeiger wird jedes Mal aktualisiert, die eine andere Ansicht aktiviert ist.

> [!NOTE]
>  Ein Zeiger auf das Hauptrahmenfenster befindet sich in der [M_pMainWnd](../mfc/reference/cwinthread-class.md#m_pmainwnd) Membervariable des Anwendungsobjekts. Einen Aufruf von `OnFileNew` in der Überschreibung der der `InitInstance` Memberfunktion `CWinApp` legt *M_pMainWnd* für Sie. Wenn Sie nicht aufrufen `OnFileNew`, legen Sie den Wert der Variablen in `InitInstance` selbst. (SDI-COM-Komponente (Server)-Anwendungen möglicherweise nicht die Variable festgelegt, wenn ' / Embedding ' in der Befehlszeile angegeben ist.) Beachten Sie, dass *M_pMainWnd* ist jetzt ein Member der Klasse `CWinThread` statt `CWinApp`.

## <a name="see-also"></a>Siehe auch

[Dokumentvorlagen und der Erstellungsvorgang für Dokumente und Ansichten](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[Erstellen von Dokumentvorlagen](../mfc/document-template-creation.md)<br/>
[Erstellen von Dokument/Ansicht](../mfc/document-view-creation.md)<br/>
[Erstellen neuer Dokumente, Fenster und Ansichten](../mfc/creating-new-documents-windows-and-views.md)

