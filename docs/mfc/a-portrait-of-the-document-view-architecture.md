---
title: Ein Portrait der Dokument-/ Ansichtarchitektur | Microsoft Docs
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
ms.openlocfilehash: d903d183675ae4b79d4610fe4413cfd8bf0e704c
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928943"
---
# <a name="a-portrait-of-the-documentview-architecture"></a>Ein Portrait der Dokument-/Ansichtarchitektur
Dokumente und Ansichten werden in einer normalen MFC-Anwendung zugeordnet. Daten werden im Dokument gespeichert, aber die Ansicht verfügt über privilegierte Zugriff auf die Daten. Die Trennung des Dokuments aus der Ansicht trennt der Speicherung und Verwaltung von Daten aus der Anzeige.  
  
## <a name="gaining-access-to-document-data-from-the-view"></a>Zugriff auf Daten aus der Ansicht zu dokumentieren.  
 Die Sicht greift auf Daten des Dokuments entweder mit der [GetDocument](../mfc/reference/cview-class.md#getdocument) -Funktion, womit einen Zeiger auf das Dokument oder die Sicht eine C++-Klasse erstellen `friend` der Dokumentklasse. Die Sicht verwendet den Zugriff auf die Daten dann zum Abrufen der Daten, wenn zum Zeichnen oder ändern sie andernfalls bereit ist.  
  
 Beispielsweise aus der Ansicht [OnDraw](../mfc/reference/cview-class.md#ondraw) Memberfunktion, die Sicht verwendet `GetDocument` um einen Zeiger Dokument abzurufen. Anschließend wird dieser Zeiger auf eine `CString` -Datenmember in das Dokument. Die Ansicht übergeben, die Zeichenfolge, die die `TextOut` Funktion. Der Code für dieses Beispiel finden Sie unter [Zeichnen in einer Ansicht](../mfc/drawing-in-a-view.md).  
  
## <a name="user-input-to-the-view"></a>Benutzereingaben in der Ansicht  
 Die Sicht kann auch einen Mausklick innerhalb des Workflows als Auswahl oder Bearbeitung der Daten interpretiert werden. Auf ähnliche Weise kann als Dateneingabe oder Bearbeiten von Tastatureingaben interpretiert werden. Angenommen Sie, vom Benutzer eingegebenen Zeichenfolge in einer Ansicht, die Text verwaltet. Die Ansicht erhält einen Zeiger auf das Dokument und den Zeiger verwendet, um die neuen Daten an das Dokument übergeben, die in einer Datenstruktur gespeichert.  
  
## <a name="updating-multiple-views-of-the-same-document"></a>Aktualisieren von mehreren Sichten des gleichen Dokuments  
 In einer Anwendung mit mehreren Sichten des gleichen Dokuments – z. B. ein unterteiltes Fenster in einem Text-Editor-Ansicht übergibt die neuen Daten zuerst auf das Dokument. Anschließend des Dokuments ruft [UpdateAllViews](../mfc/reference/cdocument-class.md#updateallviews) Memberfunktion, die mitteilt, alle Ansichten des Dokuments, das sich selbst, reflektieren die neuen Daten aktualisieren. Dies synchronisiert die Sichten.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Vorteile der Dokument-/Ansichtarchitektur](../mfc/advantages-of-the-document-view-architecture.md)  
  
-   [Alternativen zur Dokument-/Ansichtarchitektur](../mfc/alternatives-to-the-document-view-architecture.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Dokument-/Ansichtsarchitektur](../mfc/document-view-architecture.md)

