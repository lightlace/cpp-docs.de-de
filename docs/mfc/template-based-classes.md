---
title: Vorlagenbasierte Klassen
ms.date: 11/04/2016
helpviewer_keywords:
- type-safe collections
- CTypedPtrList class [MFC], template-based classes
- arrays [MFC], classes
- arrays [MFC], pointers
- typed pointers, collections of
- arrays [MFC], template-based
- CArray class [MFC], template-based classes
- simple template-based collections
- simple array collection classes [MFC]
- typed pointers
- collections, typed-pointer
- CList class [MFC], template-based classes
- collection classes [MFC], template-based
- CTypedPtrMap class [MFC], template-based classes
- pointers, collections of typed
- CTypedPtrArray class [MFC], template-based classes
- MFC collection classes [MFC], template-based
- template-based collection classes [MFC]
- simple list collection classes [MFC]
ms.assetid: c69fc95b-c8f6-4a99-abed-517c9898ef0c
ms.openlocfilehash: 40633c8b2b09d27e97443364ed3ce711ee217e18
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57284657"
---
# <a name="template-based-classes"></a>Vorlagenbasierte Klassen

In diesem Artikel wird erläutert, die als typsicherer vorlagenbasierte Auflistungsklassen im MFC-Version 3.0 und höher. Mithilfe von Vorlagen zum Erstellen von typsicheren Sammlungen ist einfacher und effizienter als die Verwendung der Auflistungsklassen, die nicht auf Vorlagen basierende hilft bei der Bereitstellung typsicherheit.

MFC verfügt über vordefinierte zwei Kategorien von vorlagenbasierte Auflistungen aus:

- [Einfache Zuordnungsklassen für Arrays, Liste und](#_core_using_simple_array.2c_.list.2c_.and_map_templates)

   `CArray`, `CList`, `CMap`

- [Arrays, Listen und Zuordnungen von typisierter Zeiger](#_core_using_typed.2d.pointer_collection_templates)

   `CTypedPtrArray`, `CTypedPtrList`, `CTypedPtrMap`

Einfache Auflistung werden alle von abgeleiteten Klassen Klasse `CObject`, sodass sie die Serialisierung, die dynamische Erstellung und andere Eigenschaften des erben `CObject`. Der typisierte zeigerauflistungsklassen müssen Sie die Klasse an, Sie abgeleitet, die einer der vordefinierten von MFC, wie z. B. Zeiger nicht auf Vorlagen basierende Sammlungen sein muss `CPtrList` oder `CPtrArray`. Die neue Sammlung-Klasse erbt die angegebene Klasse aus, und der neuen Klasse-Memberfunktionen verwenden gekapselten Aufrufe an die Member der Basisklasse, um die typsicherheit zu erzwingen.

Weitere Informationen zu C++-Vorlagen finden Sie unter [Vorlagen](../cpp/templates-cpp.md) in die *C++-Sprachreferenz*.

##  <a name="_core_using_simple_array.2c_.list.2c_.and_map_templates"></a> Mithilfe von einfachen Array, Liste und Zuordnung von Vorlagen

Um die einfache Auflistung Vorlagen verwenden zu können, müssen Sie wissen, welche Art von Daten in diesen Auflistungen gespeichert werden können und welche Parameter in Ihrer Sammlung-Deklarationen verwendet.

###  <a name="_core_simple_array_and_list_usage"></a> Einfaches Array und Verwendung auflisten

Die einfachen Array und Listenklassen [CArray](../mfc/reference/carray-class.md) und [CList](../mfc/reference/clist-class.md), zwei Parameter annehmen: *Typ* und `ARG_TYPE`. Diese Klassen können einen beliebigen Datentyp aufweisen, die Sie, in angeben speichern die *Typ* Parameter:

- Grundlegende C++-Data-Typen, z. B. **Int**, **Char**, und **"float"**

- C++-Strukturen und Klassen

- Andere Typen, die Sie definieren

Der Einfachheit halber und Effizienz zu erzielen, können Sie die *ARG_TYPE* Parameter, um den Typ der Argumente der Funktion anzugeben. Geben Sie in der Regel *ARG_TYPE* als Verweis auf den Typ mit dem Namen in der *Typ* Parameter. Zum Beispiel:

[!code-cpp[NVC_MFCCollections#1](../mfc/codesnippet/cpp/template-based-classes_1.cpp)]

Im erste Beispiel deklariert eine Arrayauflistung `myArray`, enthält **Int**s. Im zweite Beispiel deklariert eine listensammlung `myList`, speichert `CPerson` Objekte. Bestimmte Memberfunktionen der Auflistungsklassen akzeptieren Argumente, deren Typ, indem angegeben wird, die *ARG_TYPE* Template-Parameter. Z. B. die `Add` Memberfunktion der Klasse `CArray` nimmt eine *ARG_TYPE* Argument:

[!code-cpp[NVC_MFCCollections#2](../mfc/codesnippet/cpp/template-based-classes_2.cpp)]

###  <a name="_core_simple_map_usage"></a> Einfaches Kartogramm Nutzung

Einfache Map-Klasse, [CMap](../mfc/reference/cmap-class.md), benötigt vier Parameter: *Schlüssel*, *ARG_KEY*, *Wert*, und *ARG_VALUE*. Die Map-Klassen können einen beliebigen Datentyp aufweisen speichern, wie die Klassen-Array und Liste. Im Gegensatz zu Arrays und Listen, die index, und die Daten, die sie speichern, ordnen Sie Zuordnungen, Schlüssel und Werte: Sie Zugriff auf einen Wert in einer Zuordnung gespeichert wird, durch die Angabe des Werts zugeordneten Schlüssels. Die *Schlüssel* Parameter gibt den Datentyp, der für den Zugriff auf Daten, die in der Zuordnung gespeicherten Schlüssel. Wenn der Typ des *Schlüssel* ist eine Struktur oder Klasse, die *ARG_KEY* Parameter ist in der Regel einen Verweis auf den Typ im angegebenen *Schlüssel*. Die *Wert* Parameter gibt den Typ der Elemente in der Zuordnung gespeichert. Wenn der Typ des *ARG_VALUE* ist eine Struktur oder Klasse, die *ARG_VALUE* Parameter ist in der Regel einen Verweis auf den Typ im angegebenen *Wert*. Zum Beispiel:

[!code-cpp[NVC_MFCCollections#3](../mfc/codesnippet/cpp/template-based-classes_3.cpp)]

Das erste Beispiel speichert `MY_STRUCT` Werte, greift auf, indem sie **Int** Schlüssel und gibt, die Zugriff auf `MY_STRUCT` Elemente als Verweis. Das zweite Beispiel speichert `CPerson` Werte, greift auf, indem sie `CString` Schlüssel und gibt die Verweise auf verwendete Elemente zurück. In diesem Beispiel kann ein einfache Adressbuch darstellen, in dem Sie Personen nach Nachnamen nachschlagen.

Da die *Schlüssel* Parameter ist vom Typ `CString` und *KEY_TYPE* Parameter ist vom Typ `LPCSTR`, der Schlüssel in der Zuordnung gespeichert werden, als Elemente des Typs `CString` jedoch in verwiesen wird Funktionen wie `SetAt` durch Zeiger vom Typ `LPCSTR`. Zum Beispiel:

[!code-cpp[NVC_MFCCollections#4](../mfc/codesnippet/cpp/template-based-classes_4.cpp)]

##  <a name="_core_using_typed.2d.pointer_collection_templates"></a> Mithilfe von typisierten Zeigerauflistung-Vorlagen

Um die typisierten zeigerauflistung-Vorlagen verwenden zu können, müssen Sie wissen, welche Arten von Daten in diesen Auflistungen gespeichert werden können und welche Parameter in Ihrer Sammlung-Deklarationen verwendet.

###  <a name="_core_typed.2d.pointer_array_and_list_usage"></a> Typisierte Zeigerarray und Verwendung auflisten

Die typisierte Zeigerarray und Klassen für Listen, [CTypedPtrArray](../mfc/reference/ctypedptrarray-class.md) und [CTypedPtrList](../mfc/reference/ctypedptrlist-class.md), zwei Parameter annehmen: *BASE_CLASS* und *Typ*. Diese Klassen können einen beliebigen Datentyp aufweisen, die Sie, in angeben speichern die *Typ* Parameter. Sie werden von einer der Auflistungsklassen, der Zeiger speichert abgeleitet; Sie geben diese Basisklasse in *BASE_CLASS*. Für Arrays, verwenden Sie entweder `CObArray` oder `CPtrArray`. Für Listen, verwenden Sie entweder `CObList` oder `CPtrList`.

Wenn Sie eine Sammlung auf Basis deklarieren, aktiviert ist, z. B. `CObList`, die neue Klasse erbt nicht nur die Member der Basisklasse, aber es auch eine Anzahl von zusätzlichen typsichere Member deklariert, Funktionen und Operatoren, mit deren Hilfe die typsicherheit durch kapseln Aufrufe von der Member der Basisklasse. Diese kapselungen verwalten Sie alle erforderlichen typkonvertierung. Zum Beispiel:

[!code-cpp[NVC_MFCCollections#5](../mfc/codesnippet/cpp/template-based-classes_5.cpp)]

Im ersten Beispiel wird ein Array-Zeiger, `myArray`, abgeleitet von `CObArray`. Das Array speichert, und gibt die Verweise auf `CPerson` Objekte (, in denen `CPerson` ist eine abgeleitete Klasse `CObject`). Rufen Sie alle `CObArray` Member-Funktion, oder Sie rufen die neue typsichere `GetAt` und `ElementAt` fungiert, oder verwenden Sie die typsichere **[]** Operator.

Im zweite Beispiel deklariert eine Liste-Zeiger, `myList`, abgeleitet von `CPtrList`. Die Liste Zeiger gespeichert und auf `MY_STRUCT` Objekte. Eine Klasse, basierend auf `CPtrList` dient zum Speichern von Zeigern auf Objekte, die nicht von abgeleiteten `CObject`. `CTypedPtrList` bietet eine Reihe von typsicheren Memberfunktionen: `GetHead`, `GetTail`, `RemoveHead`, `RemoveTail`, `GetNext`, `GetPrev`, und `GetAt`.

###  <a name="_core_typed.2d.pointer_map_usage"></a> -Zeiger-Map-Nutzung

-Zeiger-Map-Klasse, [CTypedPtrMap](../mfc/reference/ctypedptrmap-class.md), nimmt drei Parameter: *BASE_CLASS*, *Schlüssel*, und *Wert*. Die *BASE_CLASS* Parameter gibt an, die Klasse aus der die neue Klasse abgeleitet werden soll: `CMapPtrToWord`, `CMapPtrToPtr`, `CMapStringToPtr`, `CMapWordToPtr`, `CMapStringToOb`und so weiter. *Schlüssel* ist analog zu *Schlüssel* in `CMap`: Es gibt den Typ des Schlüssels für Suchvorgänge verwendet. *Wert* ist analog zu *Wert* in `CMap`: Es gibt den Typ des Objekts in der Zuordnung gespeichert. Zum Beispiel:

[!code-cpp[NVC_MFCCollections#6](../mfc/codesnippet/cpp/template-based-classes_6.cpp)]

Im erste Beispiel ist eine Zuordnung, die basierend auf `CMapPtrToPtr` – er verwendet `CString` Schlüssel zugeordnet wird, auf die Zeiger auf `MY_STRUCT`. Sehen Sie nach einem gespeicherten Zeiger durch einen typsicheren Aufrufen `Lookup` Member-Funktion. Sie können die **[]** Operator, um das Suchen nach einem gespeicherten Zeiger und fügen sie falls nicht gefunden. Und Sie können die Zuordnung, die über die typsichere durchlaufen `GetNextAssoc` Funktion. Sie können auch andere Memberfunktionen Aufrufen der Klasse `CMapPtrToPtr`.

Im zweite Beispiel ist eine Zuordnung, die basierend auf `CMapStringToOb` – zugeordnet, der gespeicherte Zeiger auf "String"-Schlüssel verwendet `CMyObject` Objekte. Können Sie die gleichen typsicher-Elemente, die im vorherigen Absatz beschrieben, oder Sie können die Member der Klasse aufrufen `CMapStringToOb`.

> [!NOTE]
>  Bei Angabe einer **Klasse** oder **Struktur** Geben Sie für die *Wert* -Parameter, anstatt einen Zeiger oder Verweis auf den Typ, der Klasse oder Struktur einen Kopierkonstruktor benötigen.

Weitere Informationen finden Sie unter [wie eine typsichere Auflistung](../mfc/how-to-make-a-type-safe-collection.md).

## <a name="see-also"></a>Siehe auch

[Sammlungen](../mfc/collections.md)
