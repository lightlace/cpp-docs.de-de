---
title: Ein Portrait der Dokument-/ Ansichtarchitektur die | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- documents [MFC], views
- multiple views [MFC], updating from document
- document/view architecture [MFC]
- views [MFC], and user input
- documents [MFC], accessing data from view
- views [MFC], updating
- input [MFC], view class
- documents [MFC], multiple views
- document/view architecture [MFC], accessing data from view
- document/view architecture [MFC], about document/view architecture
- views [MFC], accessing document data from
ms.assetid: 4e7f65dc-b166-45d8-bcd5-9bb0d399b946
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4bd07bf521e1dcfc59b1d3f213f513b1d361b8a6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409518"
---
# <a name="a-portrait-of-the-documentview-architecture"></a>Ein Portrait der Dokument-/Ansichtarchitektur

Dokumente und Ansichten werden in einer typischen MFC-Anwendung zugeordnet. Daten werden in das Dokument gespeichert, aber die Ansicht verfügt über privilegierte Zugriff auf die Daten. Die Trennung von Ansicht des Dokuments trennt die Speicherung und Wartung von Daten aus der Anzeige.

## <a name="gaining-access-to-document-data-from-the-view"></a>Zugriff auf Daten aus der Sicht zu dokumentieren.

Die Ansicht greift auf Daten eines Dokuments mit der [GetDocument](../mfc/reference/cview-class.md#getdocument) ordnungsgemäß verwendet werden, die einen Zeiger zurückgibt, auf das Dokument oder durch die Sicht eine C++-Klasse `friend` der Document-Klasse. Die Ansicht verwendet dann den Zugriff auf die Daten, um die Daten abzurufen, wenn er gezeichnet werden soll, oder in anderer Weise bearbeitet er bereit ist.

Z. B. von der Ansicht [OnDraw](../mfc/reference/cview-class.md#ondraw) Memberfunktion wird die Sicht verwendet `GetDocument` einen Zeiger Dokument abrufen. Anschließend er diesen Zeiger, verwendet den Zugriff auf eine `CString` Datenmember in das Dokument. Die Ansicht übergibt die Zeichenfolge, die die `TextOut` Funktion. Der Code für dieses Beispiel finden Sie unter [Zeichnen in einer Ansicht](../mfc/drawing-in-a-view.md).

## <a name="user-input-to-the-view"></a>Benutzereingaben in der Ansicht

Die Sicht kann auch einen Mausklick innerhalb des Workflows als Auswahl oder Bearbeiten der Daten interpretiert werden. Auf ähnliche Weise können sie Tastatureingaben als Dateneingabe oder bearbeiten interpretiert. Nehmen Sie eine Zeichenfolge der Benutzereingabe in einer Ansicht, die Text verwaltet an. Die Ansicht erhält einen Zeiger auf das Dokument und verwendet den Zeiger auf die neuen Daten auf das Dokument, übergeben Sie die in eine Datenstruktur gespeichert.

## <a name="updating-multiple-views-of-the-same-document"></a>Aktualisieren mehrerer Ansichten des gleichen Dokuments

In einer Anwendung mit mehreren Ansichten des gleichen Dokuments – z. B. ein Teilungsfenster in einem Text-Editor – die Ansicht übergibt die neuen Daten zuerst auf das Dokument. Anschließend ruft Sie des Dokuments [UpdateAllViews](../mfc/reference/cdocument-class.md#updateallviews) Memberfunktion, der allen Ansichten des Dokuments, das selbst aktualisieren, damit die neuen Daten darüber informiert werden. Diese synchronisiert die Sichten.

### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Vorteile der Dokument-/Ansichtarchitektur](../mfc/advantages-of-the-document-view-architecture.md)

- [Alternativen zur Dokument-/Ansichtarchitektur](../mfc/alternatives-to-the-document-view-architecture.md)

## <a name="see-also"></a>Siehe auch

[Dokument-/Ansichtsarchitektur](../mfc/document-view-architecture.md)

