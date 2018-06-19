---
title: Vorlagenbasierte Klassen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 68d44a66f328465f2c59fb361f9bb6b2a76efa82
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385470"
---
# <a name="template-based-classes"></a>Vorlagenbasierte Klassen
In diesem Artikel wird erläutert, die als typsicherer vorlagenbasierte Auflistungsklassen in MFC, Version 3.0 und höher. Mithilfe von Vorlagen zum Erstellen von Sammlungen typsicher ist einfacher und bietet typsicherheit effizienter als die Verwendung der Auflistungsklassen, die nicht auf Vorlagen basieren.  
  
 MFC verfügt über vordefinierte zwei Kategorien von vorlagenbasierte Auflistungen aus:  
  
-   [Einfache Zuordnungsklassen für Arrays, Liste und](#_core_using_simple_array.2c_.list.2c_.and_map_templates)  
  
     `CArray`, `CList`, `CMap`  
  
-   [Arrays, Listen und Zuordnungen von typisierter Zeiger](#_core_using_typed.2d.pointer_collection_templates)  
  
     `CTypedPtrArray`, `CTypedPtrList`, `CTypedPtrMap`  
  
 Die einfache Auflistungsklassen werden alle stammen aus der Klasse `CObject`, sodass sie die Serialisierung, die dynamische Erstellung und andere Eigenschaften des erben `CObject`. Der typisierte zeigerauflistungsklassen erfordern, dass Sie die Klasse geben Sie abgeleitet – die muss eine der vordefinierten von MFC, wie z. B. nicht auf Vorlagen basierende Zeiger Auflistungen `CPtrList` oder `CPtrArray`. Die neue Auflistungsklasse erbt von der angegebenen Basisklasse und Memberfunktionen für die neue Klasse mit der typsicherheit erzwingen gekapselten Aufrufe an die Member der Basisklasse.  
  
 Weitere Informationen zu C++-Vorlagen finden Sie unter [Vorlagen](../cpp/templates-cpp.md) in der *C++-Sprachreferenz*.  
  
##  <a name="_core_using_simple_array.2c_.list.2c_.and_map_templates"></a> Verwenden von einfachen Array, Liste und Zuordnung Vorlagen  
 Um die einfache Auflistung Vorlagen verwenden zu können, müssen Sie wissen, welche Art von Daten in diesen Sammlungen gespeichert werden können und welche Parameter in der Auflistung Deklarationen verwendet.  
  
###  <a name="_core_simple_array_and_list_usage"></a> Einfaches Array und Verwendung  
 Die einfachen Array und Listenklassen, [CArray](../mfc/reference/carray-class.md) und [CList](../mfc/reference/clist-class.md), nehmen zwei Parameter: *Typ* und `ARG_TYPE`. Diese Klassen können einen beliebigen Datentyp aufweisen, die Sie, in angeben speichern die *Typ* Parameter:  
  
-   Grundlegende C++-Datentypen, wie z. B. `int`, `char`, und **"float"**  
  
-   C++-Strukturen und Klassen  
  
-   Andere Typen, die Sie definieren  
  
 Zur Vereinfachung und Effizienz, können Sie die `ARG_TYPE` Parameter zur Angabe von Funktionsargumenten. Geben Sie in der Regel `ARG_TYPE` als Verweis auf den Typ mit dem Namen in der *Typ* Parameter. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCCollections#1](../mfc/codesnippet/cpp/template-based-classes_1.cpp)]  
  
 Im erste Beispiel deklariert eine Arrayauflistung `myArray`, enthält `int`s. Im zweite Beispiel deklariert eine listenauflistung `myList`, zur Speicherung der `CPerson` Objekte. Bestimmte Memberfunktionen der Auflistungsklassen Argumente, deren Typ, indem angegeben wird, die `ARG_TYPE` Template-Parameter. Z. B. die **hinzufügen** Memberfunktion der Klasse `CArray` akzeptiert ein `ARG_TYPE` Argument:  
  
 [!code-cpp[NVC_MFCCollections#2](../mfc/codesnippet/cpp/template-based-classes_2.cpp)]  
  
###  <a name="_core_simple_map_usage"></a> Verwendung von einfachen Zuordnung  
 Die einfache Zuordnungsklasse [CMap](../mfc/reference/cmap-class.md), nimmt vier Parameter: *Schlüssel*, `ARG_KEY`, *Wert*, und `ARG_VALUE`. Die Zuordnungsklassen können einen beliebigen Datentyp aufweisen speichern, wie den Array- und Klassen. Im Gegensatz zu Arrays und Listen, die index und die Reihenfolge der Daten, die sie speichern, Maps zuordnen, Schlüssel und Werte: Sie Zugriff auf einen Wert in einer Zuordnung durch Angabe des Werts zugeordneten Schlüssel gespeichert. Die *Schlüssel* Parameter gibt den Datentyp der Schlüssel verwendet, um in der Zuordnung gespeicherten Daten zuzugreifen. Wenn der Typ des *Schlüssel* ist eine Struktur oder Klasse, die `ARG_KEY` Parameter ist in der Regel einen Verweis auf die im angegebenen Typ *Schlüssel*. Die *Wert* Parameter gibt den Typ der Elemente in der Zuordnung gespeichert. Wenn der Typ des `ARG_VALUE` ist eine Struktur oder Klasse, die `ARG_VALUE` Parameter ist in der Regel einen Verweis auf die im angegebenen Typ *Wert*. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCCollections#3](../mfc/codesnippet/cpp/template-based-classes_3.cpp)]  
  
 Das erste Beispiel speichert `MY_STRUCT` -Werten, greift auf diese nach `int` Schlüssel und gibt zugegriffen `MY_STRUCT` Elemente als Verweis. Das zweite Beispiel speichert `CPerson` -Werten, greift auf diese nach `CString` Taste, und gibt Sie Verweise auf Elemente zugegriffen. In diesem Beispiel könnte ein einfache Adressbuch darstellen, in dem Sie Personen, die nach dem Nachnamen zu suchen.  
  
 Da die *Schlüssel* Parameter ist vom Typ `CString` und *KEY_TYPE* Parameter ist vom Typ `LPCSTR`, der Schlüssel in der Zuordnung gespeichert werden, als Elemente des Typs `CString` jedoch in verwiesen wird Funktionen wie `SetAt` über Zeiger vom Typ `LPCSTR`. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCCollections#4](../mfc/codesnippet/cpp/template-based-classes_4.cpp)]  
  
##  <a name="_core_using_typed.2d.pointer_collection_templates"></a> Mithilfe von Vorlagen Auflistung typisierter Zeiger  
 Um die typisierten zeigerauflistung Vorlagen verwenden zu können, müssen Sie wissen, welche Arten von Daten in diesen Sammlungen gespeichert werden können und welche Parameter in der Auflistung Deklarationen verwendet.  
  
###  <a name="_core_typed.2d.pointer_array_and_list_usage"></a> Typisierter Zeiger Array und Verwendung  
 Typisierter Zeiger Array und Listenklassen, [CTypedPtrArray](../mfc/reference/ctypedptrarray-class.md) und [CTypedPtrList](../mfc/reference/ctypedptrlist-class.md), nehmen zwei Parameter: `BASE_CLASS` und *Typ*. Diese Klassen können einen beliebigen Datentyp aufweisen, die Sie, in angeben speichern die *Typ* Parameter. Sie abgeleitet sind aus einem der Auflistungsklassen, die Zeiger gespeichert; Geben Sie diese Basisklasse in `BASE_CLASS`. Für Arrays, verwenden Sie entweder `CObArray` oder `CPtrArray`. Für Listen, verwenden Sie entweder `CObList` oder `CPtrList`.  
  
 Wenn Sie eine Sammlung auf Basis deklarieren, sagen `CObList`, die neue Klasse erbt nicht nur die Member der Basisklasse, aber es auch eine Anzahl von zusätzlichen als typsicherer Member deklariert, Funktionen und Operatoren, mit deren Hilfe die typsicherheit durch kapseln die Member der Basisklasse aufrufen. Diese Encapsulations verwalten Sie alle erforderlichen typkonvertierung. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCCollections#5](../mfc/codesnippet/cpp/template-based-classes_5.cpp)]  
  
 Im erste Beispiel deklariert einen Array typisierter Zeiger `myArray`, abgeleitet von `CObArray`. Das Array speichert und gibt Sie Zeiger auf `CPerson` Objekte (, in denen `CPerson` ist eine abgeleitete Klasse `CObject`). Rufen Sie eine `CObArray` Memberfunktion ist, oder Sie können die neue typsichere Aufrufen `GetAt` und `ElementAt` fungiert, oder verwenden Sie die typsichere **[]** Operator.  
  
 Im zweite Beispiel wird eine Liste typisierter Zeiger deklariert `myList`, abgeleitet von `CPtrList`. Die Liste speichert und gibt Sie Zeiger auf `MY_STRUCT` Objekte. Eine Klasse, basierend auf `CPtrList` dient zum Speichern von Zeigern auf Objekte, die nicht von abgeleiteten `CObject`. `CTypedPtrList` bietet eine Reihe von Memberfunktionen als typsicherer: `GetHead`, `GetTail`, `RemoveHead`, `RemoveTail`, `GetNext`, `GetPrev`, und `GetAt`.  
  
###  <a name="_core_typed.2d.pointer_map_usage"></a> Typisierter Zeiger Map-Verwendung  
 Typisierter Zeiger Zuordnungsklasse [CTypedPtrMap](../mfc/reference/ctypedptrmap-class.md), übernimmt drei Parameter: `BASE_CLASS`, *Schlüssel*, und *Wert*. Die `BASE_CLASS` Parameter gibt die Klasse aus der die neue Klasse abgeleitet werden soll: `CMapPtrToWord`, `CMapPtrToPtr`, `CMapStringToPtr`, `CMapWordToPtr`, `CMapStringToOb`und so weiter. *Schlüssel* ist analog zu *Schlüssel* in `CMap`: Es gibt den Typ des Schlüssels, der für Suchvorgänge verwendet. *Wert* ist analog zu *Wert* in `CMap`: Es gibt den Typ des Objekts in der Zuordnung gespeichert. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCCollections#6](../mfc/codesnippet/cpp/template-based-classes_6.cpp)]  
  
 Im erste Beispiel wird eine Zuordnung basierend auf **CMapPtrToPt**R – verwendet `CString` Schlüssel zugeordnet wird, auf die Zeiger auf `MY_STRUCT`. Sie können einem gespeicherten Zeiger durch Aufrufen einen typsicheren Nachschlagen `Lookup` Memberfunktion. Sie können die **[]** Operator, um die Suche nach einem gespeicherten Zeiger und fügen es nicht gefunden. Und Sie können die Zuordnung unter Verwendung der typsichere durchlaufen `GetNextAssoc` Funktion. Sie können auch andere Memberfunktionen Aufrufen der Klasse `CMapPtrToPtr`.  
  
 Im zweite Beispiel wird eine Zuordnung basierend auf **CMapStringToO**b – verwendet Zeichenfolgenschlüssel gespeicherten Zeiger auf zugeordnet `CMyObject` Objekte. Können Sie dieselben im vorherigen Absatz beschrieben als typsicherer Member, oder Sie können die Member der Klasse aufrufen `CMapStringToOb`.  
  
> [!NOTE]
>  Bei Angabe einer **Klasse** oder `struct` Geben Sie für die *Wert* Parameter, anstatt einen Zeiger oder Verweis auf den Typ, der Klasse oder Struktur einen Kopierkonstruktor benötigen.  
  
 Weitere Informationen finden Sie unter [Gewusst wie: Erstellen einer typsicheren Auflistung](../mfc/how-to-make-a-type-safe-collection.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Sammlungen](../mfc/collections.md)

