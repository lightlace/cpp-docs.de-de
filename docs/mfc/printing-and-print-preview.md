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
ms.openlocfilehash: 73aae3391f07ba5ba2fe54e2c45179fe4b347a0b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629293"
---
# <a name="printing-and-print-preview"></a>Drucken und Druckvorschau

MFC unterstützt drucken und Druckvorschau für Ihres Programms Dokumente über eine Klasse [CView](../mfc/reference/cview-class.md). Zum einfachen Drucken und Druckvorschau, einfach zu Ihrer Ansichtsklasse überschreiben [OnDraw](../mfc/reference/cview-class.md#ondraw) Memberfunktion, die Sie trotzdem ausführen müssen. Diese Funktion kann an die Ansicht auf dem Bildschirm für einen Drucker-Gerätekontext für einen Drucker, gezeichnet oder für einen Gerätekontext, die Ihr Drucker auf dem Bildschirm simuliert.

Sie können auch Code zum Drucken von mehrseitige Dokumenten und für Ihre gedruckte Dokumente die Paginierung und Hinzufügen von Kopf- und Fußzeilen auf diese Vorschau verwalten hinzufügen.

In dieser Artikelreihe wird erläutert, wie das Drucken in der Microsoft Foundation Class-Bibliothek (MFC) implementiert wird und zum Nutzen der Druckarchitektur, die bereits in das Framework integriert. Die Artikel wird auch erläutert, wie die einfache Implementierung von Seitenansichtsfunktionen in MFC unterstützt und wie Sie verwenden können, und ändern diese Funktion.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Drucken](../mfc/printing.md)

- [Druckvorschauarchitektur](../mfc/print-preview-architecture.md)

- [Beispiel](../visual-cpp-samples.md)

## <a name="see-also"></a>Siehe auch

[Elemente der Benutzeroberfläche](../mfc/user-interface-elements-mfc.md)
