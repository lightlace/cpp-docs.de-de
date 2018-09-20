---
title: Array-Liste und Zuordnungsklassen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.mfc
dev_langs:
- C++
helpviewer_keywords:
- arrays [MFC], classes
- list classes [MFC]
- collection classes [MFC], maps
- map classes [MFC]
- collection classes [MFC], lists
ms.assetid: 81a13a7f-0c2c-4efd-b6bb-b4e624a0743d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a8d044f8844fdf46969342d1b4fc5cf2f007c041
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46436337"
---
# <a name="array-list-and-map-classes"></a>Klassen für Arrays, Listen und Zuordnungen

Zum Verarbeiten von Aggregaten von Daten, die Klassenbibliothek enthält eine Gruppe von Auflistungsklassen: arrays, Listen und Zuordnungen –, die eine Vielzahl von Objekt und die vordefinierten Typen aufnehmen kann. Die Auflistungen sind dynamisch angepasst. Diese Klassen können in jedem Programm, verwendet werden, ob für die Windows geschrieben werden sollen oder nicht. Allerdings sind sie besonders hilfreich für die Implementierung der Datenstrukturen, die Ihre Document-Klassen in das Framework definieren. Sie können leicht spezielle Auflistungsklassen ableiten, aus diesen oder können Sie sie basierend auf der Vorlagenklassen erstellen. Weitere Informationen über diese Ansätze finden Sie im Artikel [Sammlungen](../mfc/collections.md). Eine Liste der Vorlagen-Auflistungsklassen, finden Sie im Artikel [Vorlagenklassen für Arrays, Listen und Zuordnungen](../mfc/template-classes-for-arrays-lists-and-maps.md).

Arrays sind eindimensionale-Datenstrukturen, die im Arbeitsspeicher zusammenhängend gespeichert werden. Sehr schnellen zufälligen Zugriff unterstützt, da die Speicheradresse eines bestimmten Elements berechnet werden kann, indem der Index des Elements mit der Größe eines Elements multipliziert und das Ergebnis an die Basisadresse des Arrays hinzugefügt. Aber Arrays sind sehr teuer, wenn Sie Elemente in das Array eingefügt haben, seit das gesamte Array letzten das eingefügte Element muss verschoben werden, um Platz für das Element eingefügt werden soll. Arrays können wachsen und schrumpfen nach Bedarf.

Listen, Arrays ähneln jedoch sehr unterschiedlich gespeichert werden. Jedes Element in einer Liste enthält auch einen Zeiger auf die vorherige und kommende Elemente, die somit einer doppelt verknüpften Liste. Es ist sehr schnell hinzufügen oder löschen Elemente aus, da dies nur beinhaltet einige Verweise ändern. Suche in einer Liste kann sich jedoch teuer sein, da alle suchen, zum Starten eines der Enden für die in der Liste müssen.

Zuordnungen werden einen Schlüsselwert an einen Datenwert beziehen. Der Schlüssel einer Zuordnung möglicherweise z. B. eine Zeichenfolge und die Daten einen Zeiger zu einer Liste. Bitten Sie die Zuordnung erhalten Sie den Zeiger, der einer bestimmten Zeichenfolge zugeordnet. Map-Lookups sind schnell, da Zuordnungen Hashtabellen für schlüsselsuchen verwendet. Hinzufügen und Löschen von Elementen ist auch schnell. Zuordnungen werden als zusätzliche Indizes oft mit anderen Datenstrukturen verwendet. MFC verwendet eine besondere Art von Zuordnung wird aufgerufen, eine [meldungszuordnung](../mfc/mapping-messages.md) , Windows-Nachrichten in einen Zeiger auf die Handlerfunktion für diese Nachricht zuzuordnen.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)

