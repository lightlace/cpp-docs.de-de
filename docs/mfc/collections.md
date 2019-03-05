---
title: Auflistungen
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, collections
- arrays [MFC], classes
- MFC collection classes
- shapes, collection
- collection classes [MFC], MFC
- collections, about collections
- array templates [MFC]
- collection classes [MFC], template-based
- collection classes [MFC], about collection classes
- collection classes [MFC], maps
- collection classes [MFC], arrays
- shapes
- collection classes [MFC], lists
- collection classes [MFC], shapes
ms.assetid: 02586e4c-851d-41d0-a722-feb11c17c74c
ms.openlocfilehash: 5b74ee8a779ad2fffa801749d9818f985bc8c352
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57273308"
---
# <a name="collections"></a>Auflistungen

Die Microsoft Foundation Class-Bibliothek enthält Auflistungsklassen, um Gruppen von Objekten zu verwalten. Diese Klassen sind zwei Typen:

- [Auflistungsklassen, die aus den C++-Vorlagen erstellt wurde](#_core_the_template_based_collection_classes)

- [Auflistungsklassen, die nicht aus Vorlagen erstellt.](#_core_the_collection_classes_not_based_on_templates)

> [!NOTE]
>  Wenn Ihr Code bereits Auflistungsklassen verwendet wird, können Sie weiterhin ihre Verwendung. Wenn Sie neue typsicheren Auflistungsklasse für Ihre eigenen Datentypen schreiben, empfehlen wir, dass neuere Vorlagen basierende Klassen verwendet werden.

##  <a name="_core_collection_shapes"></a> Auflistungsformen

Eine Auflistungsklasse ist die "Form" und von den Typen seiner Elemente gekennzeichnet. Die Form bezieht sich auf die Möglichkeit, die Objekte organisiert und von der Sammlung gespeichert werden. MFC bietet drei grundlegende Auflistungsformen: Listet, arrays und Zuordnungen (auch bekannt als Wörterbücher). Sie können die Form "Auflistung" auswählen, die sich am besten für Ihre bestimmte Programmierproblem ist.

Jede der drei bereitgestellten Auflistungsformen wird kurz weiter unten in diesem Thema beschrieben. Um vergleichen die Funktionen der Formen können Sie entscheiden, was für Ihr Programm am besten geeignet ist, finden Sie unter [Empfehlungen für die Auswahl einer Sammlungsklasse](../mfc/recommendations-for-choosing-a-collection-class.md).

- Liste

   Die List-Klasse bietet es sich um eine geordnete, nicht indizierte Liste von Elementen, die als eine doppelt verknüpfte Liste implementiert. Eine Liste verfügt über eine "Head" und ein "Tail" und hinzufügen oder Entfernen von Elementen in der Head oder Tail, einfügen oder Löschen von Elementen in der Mitte ist sehr schnell.

- Array

   Die Array-Klasse stellt eine dynamisch angepasst, bestellt und Integer indizierte Array von Objekten bereit.

- Karte (auch bekannt als Wörterbuch)

   Eine Zuordnung ist eine Auflistung, die ein Wertobjekt ein-Objekt zuordnet.

##  <a name="_core_the_template_based_collection_classes"></a> Die vorlagenbasierte Auflistungsklassen

Die einfachste Möglichkeit zum Implementieren von einer typsicheren Auflistung, die Objekte eines beliebigen Typs enthält, ist die MFC-Template-basierten Klassen verwenden. Beispiele dieser Klassen finden Sie in der MFC-Beispiel [sammeln](../visual-cpp-samples.md).

Die folgende Tabelle enthält die MFC-vorlagenbasierte Auflistungsklassen.

### <a name="collection-template-classes"></a>Vorlage-Auflistungsklassen

|Inhalt der Auflistung|Arrays|Listen|Karten|
|-------------------------|------------|-----------|----------|
|Auflistungen von Objekten eines beliebigen Typs|`CArray`|`CList`|`CMap`|
|Sammlungen von Zeigern auf Objekte eines beliebigen Typs|`CTypedPtrArray`|`CTypedPtrList`|`CTypedPtrMap`|

##  <a name="_core_the_collection_classes_not_based_on_templates"></a> Die Auflistungsklassen, die nicht auf Vorlagen basierende

Wenn Ihre Anwendung noch nicht auf Vorlagen basierende MFC-Klassen verwendet, können Sie weiterhin ihre Verwendung. Für neue Sammlungen empfehlen wir jedoch, dass Sie die Template-basierten Klassen verwenden. Die folgende Tabelle enthält die MFC-Auflistungsklassen, die nicht auf Vorlagen basieren.

### <a name="nontemplate-collection-classes"></a>Auflistungsklassen

|Arrays|Listen|Karten|
|------------|-----------|----------|
|`CObArray`|`CObList`|`CMapPtrToWord`|
|`CByteArray`|`CPtrList`|`CMapPtrToPtr`|
|`CDWordArray`|`CStringList`|`CMapStringToOb`|
|`CPtrArray`||`CMapStringToPtr`|
|`CStringArray`||`CMapStringToString`|
|`CWordArray`||`CMapWordToOb`|
|`CUIntArray`||`CMapWordToPtr`|

Die Merkmale von MFC-Auflistungsklassen Tabelle [Empfehlungen für die Auswahl einer Sammlungsklasse](../mfc/recommendations-for-choosing-a-collection-class.md) wird beschrieben, die MFC-Auflistungsklassen im Hinblick auf diese Eigenschaften (mit Ausnahme von Form):

- ob die Klasse C++-Vorlagen verwendet

- ob die in der Auflistung gespeicherten Elemente serialisiert werden können

- ob die in der Auflistung gespeicherten Elemente zur Diagnose gesichert werden können

- ob die Auflistung typsicher ist

### <a name="what-do-you-want-to-do"></a>Was möchten Sie tun

#### <a name="general-collection-class-tasks"></a>Auflistungsklassen, allgemeine Aufgaben

- [Empfehlungen für die Auswahl einer Sammlungsklasse](../mfc/recommendations-for-choosing-a-collection-class.md)

- [Vorgehensweise: Erstellen einer typsicheren Auflistung](../mfc/how-to-make-a-type-safe-collection.md)

- [Erstellen von Stapel- und Warteschlangenauflistungen](../mfc/creating-stack-and-queue-collections.md)

- [CArray::Add](../mfc/reference/carray-class.md#add)

#### <a name="template-based-collection-class-tasks"></a>Vorlagenbasierte Auflistungsklassen, Aufgaben

- [Vorlagenbasierte Klassen](../mfc/template-based-classes.md)

#### <a name="accessing-the-members-of-a-collection-template-based-or-not"></a>Zugriff auf die Member einer Auflistung (Template-basierten oder nicht)

- [Zugreifen auf alle Elemente einer Auflistung](../mfc/accessing-all-members-of-a-collection.md)

- [Löschen aller Objekte in einer CObject-Sammlung](../mfc/deleting-all-objects-in-a-cobject-collection.md)

## <a name="see-also"></a>Siehe auch

[Konzepte](../mfc/mfc-concepts.md)<br/>
[Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)
