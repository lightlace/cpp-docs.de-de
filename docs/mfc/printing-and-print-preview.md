---
title: Drucken und Druckvorschau | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- printing [MFC]
- previewing printing
- printing [MFC]
- print preview
- printing [MFC], print preview
ms.assetid: d15059cd-32de-4450-95f7-e73aece238f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9aad5c69f6466ea8803cb466c5e5529f3dce1340
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374450"
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
