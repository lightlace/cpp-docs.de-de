---
title: Ein- und zweistufige Konstruktion von Objekten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- objects [MFC], creating graphic objects
- object creation [MFC], graphic objects
- objects [MFC], graphic objects
- one-stage and two-stage construction of objects [MFC]
ms.assetid: 5a1c410c-4a4b-4dd9-a2ec-ced831aa7f21
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a6454e34830591eccb2b696948d02f74ad8cebfd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426574"
---
# <a name="one-stage-and-two-stage-construction-of-objects"></a>Ein- oder zweistufige Erstellung von Objekten

Sie haben die Wahl zwischen zwei Techniken für die grafische Objekte, z. B. Stifte und Pinsel erstellen:

- *1-Stage-Konstruktion*: Erstellen und Initialisieren des Objekts in einem Schritt ausgeführt, mit dem Konstruktor.

- *Zweistufige Konstruktion*: Erstellen und initialisieren Sie das Objekt in zwei separaten Phasen. Der Konstruktor erstellt das Objekt, und keine Initialisierungsfunktion initialisiert.

Erstellung in zwei Schritten ist immer sicherer. Bei Erstellung der ein-kann der Konstruktor eine Ausnahme ausgelöst, wenn Sie die falsche Argumente angeben oder die speicherbelegung fehlschlägt. Dieses Problem ist aufgrund der zweistufige Konstruktion vermieden werden, müssen Sie für den Fehler zu überprüfen. In beiden Fällen ist das Zerstören des-Objekts den gleichen Prozess aus.

> [!NOTE]
>  Diese Verfahren gelten für die Erstellung beliebiger Objekte, die nicht nur Grafikobjekte.

## <a name="example-of-both-construction-techniques"></a>Beispiel für beide Verfahren für die Konstruktion

Das folgende kurze Beispiel zeigt beide Methoden zum Erstellen ein Pen-Objekt:

[!code-cpp[NVC_MFCDocViewSDI#6](../mfc/codesnippet/cpp/one-stage-and-two-stage-construction-of-objects_1.cpp)]

### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Grafikobjekte](../mfc/graphic-objects.md)

- [Auswählen eines Grafikobjekts für einen Gerätekontext](../mfc/selecting-a-graphic-object-into-a-device-context.md)

- [Gerätekontexte](../mfc/device-contexts.md)

- [Zeichnen in einer Ansicht](../mfc/drawing-in-a-view.md)

## <a name="see-also"></a>Siehe auch

[Grafikobjekte](../mfc/graphic-objects.md)

