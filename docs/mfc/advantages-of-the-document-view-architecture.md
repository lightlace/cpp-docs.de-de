---
title: Vorteile der Dokument-/ Ansichtarchitektur
ms.date: 11/04/2016
helpviewer_keywords:
- views [MFC], advantages
- document/view architecture [MFC], advantages of
ms.assetid: 0bc27071-e120-4889-939c-ce1e61fb9cb3
ms.openlocfilehash: e250630bf3c9714fc01ff66b66fba3ac0d5b1cc1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394727"
---
# <a name="advantages-of-the-documentview-architecture"></a>Vorteile der Dokument-/Ansichtarchitektur

Der Hauptvorteil der MFC Dokument-/Ansichtarchitektur ist, dass die Architektur mehrere Ansichten des gleichen Dokuments besonders gut unterstützt. (Wenn mehrere Ansichten ist nicht erforderlich, und der kleinen Mehraufwand für Dokumente und Ansichten in Ihrer Anwendung eine übermäßige ist, können Sie die Architektur vermeiden. [Alternativen zur Dokument-/Ansichtarchitektur](../mfc/alternatives-to-the-document-view-architecture.md).)

Nehmen wir an, dass Ihre Anwendung Benutzer, die numerische Daten im Arbeitsblatt-Format oder im Diagramm anzeigen kann. Benutzer sollten finden Sie unter gleichzeitig sowohl die unformatierten Daten in der Kalkulationstabelle und ein Diagramm, die sich aus den Daten ergibt. Diese separaten Ansichten können Sie in separaten Rahmenfenstern oder Splitter Bereiche in einem einzelnen Fenster angezeigt. Jetzt nehmen die Benutzer die Daten in die Tabelle und bearbeiten können die Änderungen sofort im Diagramm dargestellten.

In MFC würde die Arbeitsblatt-Ansicht und der Diagrammansicht auf anderen Klassen abgeleitet von CView basiert. Beide Ansichten würde mit einem einzelnen Dokument-Objekt zugeordnet werden. Das Dokument speichert die Daten (oder vielleicht aus einer Datenbank erhält). Beide Ansichten auf das Dokument zugreifen, und zeigen die Daten, die sie daraus abrufen.

Wenn ein Benutzer aktualisiert eine der Ansichten, die Aufrufe anzeigen `CDocument::UpdateAllViews`. Die Funktion benachrichtigt alle Ansichten des Dokuments, und jeder Ansicht mit den neuesten Daten aus dem Dokument aktualisiert. Ein einziger Aufruf an `UpdateAllViews` synchronisiert die verschiedenen Ansichten.

Dieses Szenario wäre schwierig, Code ohne die Trennung von Daten aus der Ansicht, insbesondere dann, wenn die Ansichten der Daten selbst gespeichert. Dokument/Ansicht ist es einfach. Das Framework ermöglicht die meiste Arbeit Koordination für Sie.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Alternativen zur Dokument-/Ansicht](../mfc/alternatives-to-the-document-view-architecture.md)

- [CDocument](../mfc/reference/cdocument-class.md)

- [CView](../mfc/reference/cview-class.md)

- [CDocument::UpdateAllViews](../mfc/reference/cdocument-class.md#updateallviews)

- [CView::GetDocument](../mfc/reference/cview-class.md#getdocument)

## <a name="see-also"></a>Siehe auch

[Dokument-/Ansichtsarchitektur](../mfc/document-view-architecture.md)
