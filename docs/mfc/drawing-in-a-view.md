---
title: Zeichnen in einer Ansicht | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- drawing [MFC], in views
- views [MFC], printing
- views [MFC], updating
- printing [MFC], views
- views [MFC], rendering
- printing views [MFC]
- paint messages in view class [MFC]
- device contexts, screen drawings
ms.assetid: e3761db6-0f19-4482-a4cd-ac38ef7c4d3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bc716800c35aa922f7912f586d6e5b8429593615
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346164"
---
# <a name="drawing-in-a-view"></a>Zeichnen in einer Ansicht
Fast alle Zeichnen in Ihrer Anwendung tritt in der Ansicht `OnDraw` Memberfunktion, die Sie in Ihrer Ansichtsklasse überschreiben müssen. (Die Ausnahme ist die Maus zeichnen, die in beschriebenen [Interpretieren von Benutzereingaben mit einer Benutzeransicht](../mfc/interpreting-user-input-through-a-view.md).) Ihre `OnDraw` außer Kraft setzen:  
  
1.  Ruft Daten ab, durch den Aufruf des Dokuments Memberfunktionen, die Sie bereitstellen.  
  
2.  Zeigt die Daten durch Aufrufen von Memberfunktionen eines Gerätekontext Objekts, das an das Framework übergibt `OnDraw`.  
  
 Wenn Daten eines Dokuments in irgendeiner Weise geändert wird, muss die Sicht neu gezeichnet wird, um die Änderungen wiederzugeben. Dies geschieht normalerweise, wenn der Benutzer eine Änderung durch eine Sicht auf das Dokument ermöglicht. In diesem Fall ruft die Ansicht des Dokuments [UpdateAllViews](../mfc/reference/cdocument-class.md#updateallviews) Memberfunktion versucht, alle Ansichten des gleichen Dokuments selbst aktualisieren zu benachrichtigen. `UpdateAllViews` Ruft jede Ansicht [OnUpdate](../mfc/reference/cview-class.md#onupdate) Memberfunktion. Die standardmäßige Implementierung des `OnUpdate` wird die Ansicht des gesamten Clientbereich ungültig. Sie können überschreiben, um nur diejenigen Regionen der Clientbereich für ungültig zu erklären, die die geänderten Teile des Dokuments zugeordnet werden soll.  
  
 Die `UpdateAllViews` Memberfunktion der Klasse **CDocument** und `OnUpdate` Memberfunktion der Klasse `CView` können Sie die Informationen, die beschreiben, welche Teile des Dokuments geändert wurden übergeben. Dieser Hinweismechanismus "" können Sie den Bereich einschränken, den die Sicht neu gezeichnet werden muss. `OnUpdate` übernimmt zwei Hinweisargumente für "". Die erste `lHint`, des Typs **LPARAM**, können Sie alle Daten, die Ihnen, während der zweite gefällt übergeben `pHint`, des Typs `CObject`*, ermöglicht die Übergabe ein Zeigers auf ein beliebiges Objekt abgeleitet wurde. `CObject`.  
  
 Wenn eine Sicht ungültig wird, sendet Windows eine `WM_PAINT` Nachricht. Der Ansicht [OnPaint](../mfc/reference/cwnd-class.md#onpaint) Handlerfunktion beantwortet die Nachricht durch das Erstellen einer Gerätekontext Objekt der Klasse [CPaintDC](../mfc/reference/cpaintdc-class.md) und ruft der Ansicht `OnDraw` Memberfunktion. Sie normalerweise keine Schreiben einer überschreiben `OnPaint` Handlerfunktion.  
  
 Ein [Gerätekontext](../mfc/device-contexts.md) ist eine Windows-Datenstruktur, die Informationen zu den zeichnen Attributen von einem Gerät wie einer Bildschirmanzeige oder einen Drucker enthält. Alle zeichnen-Aufrufe erfolgen über einen Gerätekontext Objekt. Für das Zeichnen auf dem Bildschirm `OnDraw` übergeben ein `CPaintDC` Objekt. Für das Zeichnen auf einem Drucker, übergeben einer [CDC](../mfc/reference/cdc-class.md) Objekt für den aktuellen Drucker einrichten.  
  
 Code zum Zeichnen in der Ansicht zunächst Ruft einen Zeiger auf das Dokument, und zeichnen-Aufrufe über den Gerätekontext. Im folgenden einfachen `OnDraw` Beispiel veranschaulicht den Prozess:  
  
 [!code-cpp[NVC_MFCDocView#1](../mfc/codesnippet/cpp/drawing-in-a-view_1.cpp)]  
  
 In diesem Beispiel definieren Sie die `GetData` als Member der abgeleiteten Dokumentklasse-Funktion.  
  
 Das Beispiel gibt die Zeichenfolge ein, aus dem Dokument, in der Ansicht zentriert herankommt. Wenn die `OnDraw` Aufruf wird zum Zeichnen des Bildschirms, der `CDC` übergebene Objekt `pDC` ist ein `CPaintDC` , dessen Konstruktor wurde bereits aufgerufen `BeginPaint`. Funktionen zum Zeichnen über den Zeiger über das Gerätekontext Aufrufe. Informationen über Gerätekontexte und zeichnen-Aufrufe finden Sie in der Klasse [CDC](../mfc/reference/cdc-class.md) in der *MFC-Referenz* und [arbeiten mit Fensterobjekten](../mfc/working-with-window-objects.md).  
  
 Weitere Beispiele zum Schreiben von `OnDraw`, finden Sie unter der [MFC-Beispiele](../visual-cpp-samples.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Ansichten](../mfc/using-views.md)

