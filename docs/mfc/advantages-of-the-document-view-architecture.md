---
title: Vorteile der Dokument-/ Ansichtarchitektur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- views [MFC], advantages
- document/view architecture [MFC], advantages of
ms.assetid: 0bc27071-e120-4889-939c-ce1e61fb9cb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 45065b38128a2e3239b1fd10ded490fdcbcb3eac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33340847"
---
# <a name="advantages-of-the-documentview-architecture"></a>Vorteile der Dokument-/Ansichtarchitektur
Der Hauptvorteil der MFC-Dokument-/ Ansichtarchitektur ist, dass die Architektur mehrere Ansichten des gleichen Dokuments besonders gut unterstützt. (Wenn ist nicht, wenn mehrere Ansichten erforderlich und kleine Mehraufwand Dokument-/Ansichtarchitektur übermäßige in Ihrer Anwendung ist, können Sie die Architektur vermeiden. [Alternativen zur Dokument-/Ansichtarchitektur](../mfc/alternatives-to-the-document-view-architecture.md).)  
  
 Angenommen Sie, Ihre Anwendung Benutzer, die numerische Daten in der Kalkulationstabelle oder als Diagramm anzeigen kann. Ein Benutzer möchte möglicherweise finden Sie unter gleichzeitig sowohl die Rohdaten, in der Kalkulationstabelle und ein Diagramm, die aus diesen Daten ergibt. Diese separaten Ansichten wird angezeigt, in separaten Rahmenfenster oder Splitter Bereiche in ein einziges Fenster. Jetzt angenommen, das der Benutzer die Daten im Arbeitsblatt und ausführliche Informationen finden Sie bearbeiten kann die Änderungen sofort im Diagramm dargestellten.  
  
 In MFC würde die Kalkulationstabelle anzeigen und die Diagrammansicht auf unterschiedliche von CView abgeleitete Klassen basieren. Beide Ansichten würde ein einzelnes Dokument-Objekt zugeordnet werden. Das Dokument speichert die Daten (oder erhält er möglicherweise aus einer Datenbank). Beide Ansichten Zugriff auf das Dokument und Anzeigen der Daten, die sie daraus abrufen.  
  
 Wenn ein Benutzer aktualisiert eine der Ansichten, die Aufrufe anzeigen `CDocument::UpdateAllViews`. Diese Funktion benachrichtigt alle Ansichten des Dokuments und jede Ansicht aktualisiert sich über die neuesten Daten aus dem Dokument. Die einzigen Aufruf `UpdateAllViews` die verschiedenen Ansichten synchronisiert.  
  
 Dieses Szenario wäre nur schwer zu Code ohne die Trennung von Daten aus der Ansicht, insbesondere, wenn die Ansichten der Daten selbst gespeichert. Dokument-/Ansicht ist es einfach. Das Framework ermöglicht die Koordinierung Arbeit größtenteils von für Sie.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Alternativen zur Dokument-/Ansichtarchitektur](../mfc/alternatives-to-the-document-view-architecture.md)  
  
-   [CDocument](../mfc/reference/cdocument-class.md)  
  
-   [CView](../mfc/reference/cview-class.md)  
  
-   [UpdateAllViews](../mfc/reference/cdocument-class.md#updateallviews)  
  
-   [CView::GetDocument](../mfc/reference/cview-class.md#getdocument)  
  
## <a name="see-also"></a>Siehe auch  
 [Dokument-/Ansichtsarchitektur](../mfc/document-view-architecture.md)

