---
title: 'Vorgehensweise: Implementieren der nachverfolgung in Ihrem Code | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CRectTracker class [MFC], implementing trackers
ms.assetid: baaeca2c-5114-485f-bf58-8807db1bc973
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dc21369dd8d241bd00da2a0a8005c977094c3abf
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36932093"
---
# <a name="how-to-implement-tracking-in-your-code"></a>Gewusst wie: Implementieren der Nachverfolgung im Code
Um ein OLE-Element nachzuverfolgen, müssen bestimmte Ereignisse im Zusammenhang mit der das Element, z. B. durch Klicken auf das Element, oder aktualisieren die Ansicht des Dokuments behandelt werden. In allen Fällen ist es ausreichend, deklarieren Sie einen temporären [CRectTracker](../mfc/reference/crecttracker-class.md) Objekt, und bearbeiten Sie das Element mithilfe dieses Objekts.  
  
 Wenn ein Benutzer ein Element wählt oder ein Objekt mit einem Menübefehl einfügt, müssen Sie der nachverfolgung mit den richtigen Formatvorlagen auf den Zustand des OLE-Elements darstellen initialisieren. In der folgenden Tabelle werden die OCLIENT-Beispiel verwendeten Konventionen beschrieben. Weitere Informationen zu diesen Formaten finden Sie unter `CRectTracker`.  
  
### <a name="container-styles-and-states-of-the-ole-item"></a>Container-Formatvorlagen und den Status von OLE-Element  
  
|Format angezeigt|Status des OLE-Element|  
|---------------------|-----------------------|  
|Gepunktete Rahmen|Element verknüpft ist|  
|Durchgezogene Linie|Element ist im Dokument eingebettet.|  
|Handles zum Ändern der Größe|Derzeit wird ein Element ausgewählt|  
|Schraffiert|Element ist derzeit in-Place aktiv|  
|Schraffur über dem Element|Server des Elements ist geöffnet.|  
  
 Sie können diese problemlos mithilfe einer Prozedur, die überprüft den Status der OLE-Element und legt die entsprechenden Stile Initialisierung behandeln. Die `SetupTracker` -Funktion in im OCLIENT-Beispiel veranschaulicht die Initialisierung. Die Parameter für diese Funktion sind die Adresse des Tracker *pTracker*; ein Zeiger auf das Clientelement, das mit der nachverfolgung zusammenhängt *pItem*; und ein Zeiger auf ein Rechteck *pTrueRect* . Ein ausführlicheres Beispiel dieser Funktion finden Sie im MFC-OLE-Beispiel [OCLIENT](../visual-cpp-samples.md).  
  
 Die **SetupTracker** Codebeispiel stellt eine einzelne Funktion; Zeilen der Funktion mit Erörterung der Funktion Funktionen kombiniert werden:  
  
 [!code-cpp[NVC_MFCOClient#1](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_1.cpp)]  
  
 Tracker wird initialisiert, indem die minimale Größe festlegen und den Stil der Tracker zu löschen.  
  
 [!code-cpp[NVC_MFCOClient#2](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_2.cpp)]  
  
 Die folgenden Zeilen überprüfen, ob das Element derzeit ausgewählt ist, und gibt an, ob das Element das Dokument verknüpft oder in den es eingebettet ist. Ziehpunkte befindet sich innerhalb des Rahmens werden hinzugefügt, den Stil, und gibt an, dass das Element derzeit ausgewählt ist. Wenn das Element mit dem Dokument verknüpft ist, wird die punktierte Rahmenart verwendet. Eine durchgezogene Linie wird verwendet, wenn das Element eingebettet werden.  
  
 [!code-cpp[NVC_MFCOClient#3](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_3.cpp)]  
  
 Der folgende Code überlagert das Element mit einer Schraffur, wenn das Element derzeit öffnen.  
  
 [!code-cpp[NVC_MFCOClient#4](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_4.cpp)]  
  
 Sie können dann diese Funktion aufrufen, wann immer der Rahmenstil angezeigt werden. Beispielsweise rufen Sie diese Funktion aus der `OnDraw` Funktion der Ansichtsklasse. Dadurch wird die Darstellung der nachverfolgung aktualisiert, wenn die Sicht neu gezeichnet wird. Ein vollständiges Beispiel finden Sie unter der `CMainView::OnDraw` Funktion des MFC-OLE-Beispiels [OCLIENT](../visual-cpp-samples.md).  
  
 In der Anwendung treten Ereignisse, die Tracker-Code, z. B. Größe, verschieben oder Treffer zu erkennen, erfordern. Diese Aktionen weisen normalerweise darauf hin, dass versucht wird ist, ziehen Sie oder das Element verschoben werden. In diesen Fällen müssen Sie entscheiden, welche erfassten wurde: einen Ziehpunkt oder einen Teil des Rahmens zwischen Handles zur Größenänderung. Die `OnLButtonDown` Message-Handler ist eine gute So testen Sie die Position der Maus in Bezug auf das Element. Rufen Sie `CRectTracker::HitTest`. Wenn der Test einen anderen Wert zurückgibt `CRectTracker::hitOutside`, wird das Element ist, geändert oder verschoben wird. Aus diesem Grund sollten Sie einen Aufruf, der `Track` Memberfunktion. Finden Sie unter der `CMainView::OnLButtonDown` Funktion befindet sich in der MFC-OLE-Beispiel [OCLIENT](../visual-cpp-samples.md) ein vollständiges Beispiel.  
  
 Die `CRectTracker` -Klasse stellt mehrere unterschiedliche Cursor Formen verwendet, um anzugeben, ob ein verschieben, ändern Sie die Größe, oder ziehen Sie Operation ausgeführt wird. Zum Behandeln dieses Ereignisses überprüfen Sie, ob das Element unter der Maus derzeit ausgewählt ist. Wenn dies der Fall, stellen Sie einen Aufruf von `CRectTracker::SetCursor`, oder rufen Sie die Standard-Handler. Das folgende Beispiel stammt aus dem MFC-OLE-Beispiel [OCLIENT](../visual-cpp-samples.md):  
  
 [!code-cpp[NVC_MFCOClient#5](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_5.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [Tracker: Implementieren von Trackern in einer OLE-Anwendung](../mfc/trackers-implementing-trackers-in-your-ole-application.md)

