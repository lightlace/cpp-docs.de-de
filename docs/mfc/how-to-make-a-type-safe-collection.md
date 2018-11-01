---
title: 'Gewusst wie: Erstellen einer typsicheren Auflistung'
ms.date: 11/04/2016
helpviewer_keywords:
- type-safe collections [MFC]
- serializing collection-class elements [MFC]
- collection classes [MFC], type safety
- SerializeElements function [MFC]
- collection classes [MFC], template-based
- serialization [MFC], collection classes
- collection classes [MFC], deriving from nontemplate
ms.assetid: 7230b2db-4283-4083-b098-eb231bf5b89e
ms.openlocfilehash: 12ecec7562a9241fab30b859727a22e467e6eeb0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50581791"
---
# <a name="how-to-make-a-type-safe-collection"></a>Gewusst wie: Erstellen einer typsicheren Auflistung

In diesem Artikel wird erläutert, wie Sie typsichere Auflistungen für Ihre eigenen Datentypen. Folgende Themen werden behandelt:

- [Vorlagenbasierte Klassen verwenden, typsicherheit](#_core_using_template.2d.based_classes_for_type_safety)

- [Implementieren Hilfsfunktionen](#_core_implementing_helper_functions)

- [Verwenden nicht auf Vorlagen basierende-Auflistungsklassen](#_core_using_nontemplate_collection_classes)

Die Microsoft Foundation Class-Bibliothek bietet vordefinierte typsichere Auflistungen, die basierend auf C++-Vorlagen. Da sie die Vorlagen sind, bieten diese Klassen typsicherheit und einfache Bedienung ohne die Typumwandlung und andere zusätzliche Arbeit, die die Verwendung einer nicht auf Vorlagen basierende Klasse zu diesem Zweck. Das MFC-Beispiel [sammeln](../visual-cpp-samples.md) veranschaulicht die Verwendung von vorlagenbasierte Auflistungsklassen in einer MFC-Anwendung. Verwenden Sie diese Klassen in der Regel jedes Mal, wenn Sie neue Sammlungen Code schreiben.

##  <a name="_core_using_template.2d.based_classes_for_type_safety"></a> Vorlagenbasierte Klassen verwenden, typsicherheit

#### <a name="to-use-template-based-classes"></a>Vorlagenbasierte Klassen

1. Deklarieren Sie eine Variable des Klassentyps Auflistung. Zum Beispiel:

   [!code-cpp[NVC_MFCCollections#7](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_1.cpp)]

1. Rufen Sie die Memberfunktionen des Auflistungsobjekts. Zum Beispiel:

   [!code-cpp[NVC_MFCCollections#8](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_2.cpp)]

1. Implementieren Sie bei Bedarf die [Hilfsfunktionen](../mfc/reference/collection-class-helpers.md) und [SerializeElements](../mfc/reference/collection-class-helpers.md#serializeelements). Weitere Informationen zur Implementierung dieser Funktionen finden Sie unter [Hilfsfunktionen implementieren](#_core_implementing_helper_functions).

Dieses Beispiel zeigt die Deklaration einer Liste von ganzen Zahlen. Der erste Parameter in Schritt 1 ist der Typ der Daten, die als Elemente der Liste gespeichert. Der zweite Parameter gibt an, wie die Daten zu übergeben und Memberfunktionen der Auflistungsklasse, z. B. Merry `Add` und `GetAt`.

##  <a name="_core_implementing_helper_functions"></a> Implementieren Hilfsfunktionen

Die vorlagenbasierte Auflistungsklassen `CArray`, `CList`, und `CMap` arbeiten mit fünf globale Hilfsfunktionen, die Sie für Ihre Klasse abgeleiteten Auflistung nach Bedarf anpassen können. Weitere Informationen zu diesen Hilfsfunktionen, finden Sie unter [Auflistungsklasse](../mfc/reference/collection-class-helpers.md) in die *MFC-Referenz*. Implementierung der Serialisierungsfunktion ist für die meisten Verwendungen der vorlagenbasierte Auflistungsklassen erforderlich.

###  <a name="_core_serializing_elements"></a> Serialisieren von Elementen

Die `CArray`, `CList`, und `CMap` Klassen Aufruf `SerializeElements` Elemente der Auflistung zu speichern oder Lesen Sie diese aus einem Archiv.

Die standardmäßige Implementierung der `SerializeElements` Hilfsfunktion ist eine bitweise Schreiben von Objekten in das Archiv oder eine bitweise aus dem Archiv gelesen werden, um die Objekte, abhängig davon, ob die Objekte in gespeichert werden oder aus dem Archiv abgerufen. Außer Kraft setzen `SerializeElements` Wenn diese Aktion nicht geeignet ist.

Wenn Ihre Sammlung abgeleitete Objekte speichert `CObject` , und Sie verwenden die `IMPLEMENT_SERIAL` Makro in der Implementierung der Auflistungsklasse-Element, profitieren Sie von integrierten Funktionen für die Serialisierung `CArchive` und `CObject`:

[!code-cpp[NVC_MFCCollections#9](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_3.cpp)]

Die überladenen Einfügeoperatoren für `CArchive` Aufrufen `CObject::Serialize` (oder eine Überschreibung der Funktion) für die einzelnen `CPerson` Objekt.

##  <a name="_core_using_nontemplate_collection_classes"></a> Verwenden nicht auf Vorlagen basierende-Auflistungsklassen

MFC unterstützt auch die Auflistungsklassen, die mit MFC, Version 1.0 eingeführt wurden. Diese Klassen basieren nicht auf Vorlagen. Sie können verwendet werden, um die unterstützten Datentypen enthalten `CObject*`, `UINT`, `DWORD`, und `CString`. Sie können diese vordefinierten Sammlungen verwenden (z. B. `CObList`) zum Speichern von Sammlungen von Objekten abgeleitet `CObject`. MFC bietet auch andere vordefinierte Sammlungen zum Speichern von primitiver Typen wie z. B. `UINT` und void-Zeiger (`void`*). Im Allgemeinen ist es jedoch oft nützlich, um Ihre eigenen typsicheren Sammlungen zum Speichern von Objekten von spezifischere Klassen und seine ableitungen definieren. Beachten Sie, dass auf diese Weise zusammen mit den Auflistungsklassen nicht auf Basis der Vorlagen mehr Arbeit als die Template-basierten Klassen verwenden.

Es gibt zwei Möglichkeiten, typsichere Auflistungen mit den nicht auf Vorlagen basierende Sammlungen zu erstellen:

1. Verwenden Sie die Auflistungen nicht auf Vorlagen basierende mit Typ umwandeln, falls erforderlich. Dies ist die einfachere Methode.

1. Abgeleitet, und erweitern Sie eine nicht auf Vorlagen basierende typsichere Auflistung.

#### <a name="to-use-the-nontemplate-collections-with-type-casting"></a>Verwenden Sie die nicht auf Vorlagen basierende Sammlungen mit Typumwandlung

1. Verwenden Sie eine der nicht auf Vorlagen basierende Klassen, z. B. `CWordArray`direkt.

   Sie können z. B. Erstellen einer `CWordArray` fügen Sie alle 32-Bit-Werte hinzu, und sie abrufen. Es gibt nichts weiter tun. Sie verwenden einfach die vordefinierten Funktionen.

   Sie können auch eine vordefinierte Sammlung verwenden, z. B. `CObList`, um alle Objekte, die von abgeleiteten enthalten `CObject`. Ein `CObList` Sammlung ist zum Speichern von Zeigern auf definiert `CObject`. Wenn Sie ein Objekt aus der Liste abrufen, müssen Sie möglicherweise das Ergebnis in den richtigen Typ seit Umwandeln der `CObList` Funktionen geben Verweise auf `CObject`. Angenommen, Sie speichern `CPerson` Objekte in einem `CObList` -Auflistung, Sie müssen einen Zeiger auf ein abgerufenes Element Umwandeln einer `CPerson` Objekt. Im folgenden Beispiel wird eine `CObList` Auflistung zum Speichern `CPerson` Objekte:

   [!code-cpp[NVC_MFCCollections#10](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_4.cpp)]

   Dieses Verfahren mithilfe von vordefinierten Auflistungstyp und Umwandlung bei Bedarf kann für viele Ihrer auflistungsanforderungen ausreichend sein. Wenn Sie weitere Funktionen oder weitere typsicherheit benötigen, verwenden Sie eine Template-basierten-Klasse, oder führen Sie die nächsten Schritte.

#### <a name="to-derive-and-extend-a-nontemplate-type-safe-collection"></a>Abgeleitet werden, und erweitern eine nicht auf Vorlagen basierende typsicheren Auflistung

1. Eine eigene Auflistungsklasse aus einer der vordefinierten nicht auf Vorlagen basierende Klassen ableiten.

   Wenn Sie Ihre Klasse ableiten, können Sie die typsicheren Wrapper-Funktionen, um eine typsichere Oberfläche zu vorhandenen Funktionen hinzufügen.

   Z. B., wenn Sie eine Liste von abgeleitet `CObList` zum Speichern `CPerson` Objekte aufweist, können Sie die Wrapperfunktionen hinzufügen `AddHeadPerson` und `GetHeadPerson`, wie unten dargestellt.

   [!code-cpp[NVC_MFCCollections#11](../mfc/codesnippet/cpp/how-to-make-a-type-safe-collection_5.h)]

   Diese Wrapperfunktionen stellen eine typsichere Methode zum Hinzufügen und Abrufen von `CPerson` Objekte aus der Liste der abgeleiteten. Sie sehen, dass für die `GetHeadPerson` -Funktion, Sie werden einfach die Typumwandlung kapseln.

   Sie können auch neue Funktionen hinzufügen, definieren neue Funktionen, die die Funktionen der Auflistung zu erweitern, anstatt vorhandene Funktionalität in typsicheren Wrapper umschließen. Z. B. Artikel [Löschen aller Objekte in einer CObject-Sammlung](../mfc/deleting-all-objects-in-a-cobject-collection.md) beschreibt eine Funktion zum Löschen aller Objekte, die in einer Liste enthalten. Diese Funktion konnte als Member-Funktion der abgeleiteten Klasse hinzugefügt werden.

## <a name="see-also"></a>Siehe auch

[Sammlungen](../mfc/collections.md)

