---
title: Drucken und Druckvorschau
ms.date: 11/04/2016
helpviewer_keywords:
- printing [MFC]
- previewing printing
- printing [MFC]
- print preview
- printing [MFC], print preview
ms.assetid: d15059cd-32de-4450-95f7-e73aece238f6
ms.openlocfilehash: 70740922ec7f2030d14eebee72144a373550aacc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62218715"
---
# <a name="printing-and-print-preview"></a>Drucken und Druckvorschau

MFC unterstützt drucken und Druckvorschau für Ihres Programms Dokumente über eine Klasse [CView](../mfc/reference/cview-class.md). Zum einfachen Drucken und Druckvorschau, einfach zu Ihrer Ansichtsklasse überschreiben [OnDraw](../mfc/reference/cview-class.md#ondraw) Memberfunktion, die Sie trotzdem ausführen müssen. Diese Funktion kann an die Ansicht auf dem Bildschirm für einen Drucker-Gerätekontext für einen Drucker, gezeichnet oder für einen Gerätekontext, die Ihr Drucker auf dem Bildschirm simuliert.

Sie können auch Code zum Drucken von mehrseitige Dokumenten und für Ihre gedruckte Dokumente die Paginierung und Hinzufügen von Kopf- und Fußzeilen auf diese Vorschau verwalten hinzufügen.

In dieser Artikelreihe wird erläutert, wie das Drucken in der Microsoft Foundation Class-Bibliothek (MFC) implementiert wird und zum Nutzen der Druckarchitektur, die bereits in das Framework integriert. Die Artikel wird auch erläutert, wie die einfache Implementierung von Seitenansichtsfunktionen in MFC unterstützt und wie Sie verwenden können, und ändern diese Funktion.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Drucken](../mfc/printing.md)

- [Druckvorschauarchitektur](../mfc/print-preview-architecture.md)

- [Beispiel](../overview/visual-cpp-samples.md)

## <a name="see-also"></a>Siehe auch

[Elemente der Benutzeroberfläche](../mfc/user-interface-elements-mfc.md)
