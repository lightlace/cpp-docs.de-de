---
title: 'Vorgehensweise: Implementieren der nachverfolgung im Code'
ms.date: 11/04/2016
helpviewer_keywords:
- CRectTracker class [MFC], implementing trackers
ms.assetid: baaeca2c-5114-485f-bf58-8807db1bc973
ms.openlocfilehash: 0f037480e83b8ca1ba12af56904afe25a33e4d6c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160301"
---
# <a name="how-to-implement-tracking-in-your-code"></a>Vorgehensweise: Implementieren der nachverfolgung im Code

Um ein OLE-Element nachzuverfolgen, müssen Sie bestimmte Ereignisse im Zusammenhang mit der das Element, z. B. durch Klicken auf das Element oder das Aktualisieren des Dokuments behandeln. In allen Fällen genügt es, deklarieren Sie einen temporären [CRectTracker](../mfc/reference/crecttracker-class.md) Objekt aus, und bearbeiten Sie das Element mithilfe dieses Objekts.

Wenn ein Benutzer ein Element wählt oder ein Objekt mit einem Menübefehl fügt, müssen Sie die nachverfolgung mit den richtigen Formaten auf den Zustand des OLE-Elements darstellen initialisieren. In der folgende Tabelle wird beschrieben, die Konventionen, die von der OCLIENT-Beispiel verwendet wird. Weitere Informationen zu diesen Formaten finden Sie unter `CRectTracker`.

### <a name="container-styles-and-states-of-the-ole-item"></a>Container-Formate und den Status von der OLE-Element

|Stil angezeigt|Status der OLE-Element|
|---------------------|-----------------------|
|Gepunkteter Rahmen|Element verknüpft ist|
|Solid border|Element wird in das Dokument eingebettet.|
|Handles zum Ändern der Größe|Derzeit ist ein Element ausgewählt|
|Schraffierten Rahmen|Element ist derzeit direkt aktiv|
|Schraffur über dem Element|Server des Elements ist geöffnet.|

Sie können diese ganz einfach mithilfe einer Prozedur, die überprüft den Status des OLE-Elements und legt die entsprechenden Stile Initialisierung behandeln. Die `SetupTracker` Funktion finden Sie im OCLIENT Beispiel veranschaulicht die Initialisierung. Die Parameter für diese Funktion sind die Adresse des Tracker *pTracker*; ein Zeiger auf das Clientelement, das mit der nachverfolgung, zusammenhängt *pItem*; und einen Zeiger auf ein Rechteck, *pTrueRect* . Ein vollständigeres Beispiel dieser Funktion, finden Sie im MFC-OLE-Beispiel [OCLIENT](../overview/visual-cpp-samples.md).

Die **SetupTracker** Codebeispiel stellt eine einzelne Funktion, die Beschreibung der Funktionen von der Funktion werden Zeilen der Funktion enthält:

[!code-cpp[NVC_MFCOClient#1](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_1.cpp)]

Die nachverfolgung wird durch die minimale Größe festlegen und das Löschen von der nachverfolgung initialisiert.

[!code-cpp[NVC_MFCOClient#2](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_2.cpp)]

Die folgenden Zeilen überprüfen, ob das Element derzeit ausgewählt ist, und gibt an, ob das Element mit dem Dokument verknüpft oder in den es eingebettet ist. Handles zur Größenänderung befindet sich innerhalb des Rahmens werden hinzugefügt, um den Stil, der angibt, dass das Element derzeit ausgewählt ist. Wenn das Element zu Ihrem Dokument verknüpft ist, wird die gepunktete Rahmenart verwendet. Eine durchgezogene Linie wird verwendet, wenn das Element eingebettet ist.

[!code-cpp[NVC_MFCOClient#3](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_3.cpp)]

Der folgende Code überlagert das Element mit einer Schraffur, wenn das Element derzeit öffnen.

[!code-cpp[NVC_MFCOClient#4](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_4.cpp)]

Sie können dann diese Funktion aufrufen, wenn die nachverfolgung aufweist, die angezeigt werden. Beispielsweise rufen Sie diese Funktion aus der `OnDraw` Funktion der Ansichtsklasse. Dadurch wird die nachverfolgung des Darstellung aktualisiert, wenn die Sicht neu gezeichnet wird. Ein vollständiges Beispiel finden Sie unter den `CMainView::OnDraw` Funktion des MFC-OLE-Beispiels [OCLIENT](../overview/visual-cpp-samples.md).

In der Anwendung treten Ereignisse, die Tracker-Code, z. B. die Größenänderung von Fenstern annimmt, verschieben oder Treffer zu erkennen, erfordern. Diese Aktionen weisen normalerweise darauf hin, dass ein Versuch gestellt wird, ziehen Sie aus, oder verschieben Sie das Element. In diesen Fällen müssen Sie entscheiden, welche Anwendung war: eine Ziehpunkt zum Ändern oder einen Teil des Rahmens zwischen Handles zur Größenänderung. Die `OnLButtonDown` Message-Handler ist ein guter Ausgangspunkt, um die Position des Mauszeigers in Bezug auf das Element zu testen. Rufen Sie `CRectTracker::HitTest`. Wenn der Test einen anderen Wert zurückgibt `CRectTracker::hitOutside`, wird das Element ist, geändert oder verschoben. Aus diesem Grund sollten Sie einen Aufruf, der `Track` Member-Funktion. Finden Sie unter den `CMainView::OnLButtonDown` Funktion befindet sich in der MFC-OLE-Beispiel [OCLIENT](../overview/visual-cpp-samples.md) ein vollständiges Beispiel.

Die `CRectTracker` Klasse stellt mehrere unterschiedliche Cursor Formen verwendet, um anzugeben, ob eine Verschiebung, die Größe ändern, oder ziehen Sie Operation ausgeführt wird. Überprüfen Sie zum Behandeln dieses Ereignisses, um festzustellen, ob das Element unter der Maus derzeit ausgewählt ist. Wenn es sich handelt, stellen Sie einen Aufruf von `CRectTracker::SetCursor`, oder rufen Sie die Standard-Handler. Das folgende Beispiel stammt aus dem MFC-OLE-Beispiel [OCLIENT](../overview/visual-cpp-samples.md):

[!code-cpp[NVC_MFCOClient#5](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_5.cpp)]

## <a name="see-also"></a>Siehe auch

[Tracker: Implementieren von Trackern in einer OLE-Anwendung](../mfc/trackers-implementing-trackers-in-your-ole-application.md)
