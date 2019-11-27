---
title: 'Vorgehensweise: Erstellen und Verwenden von unique_ptr Instanzen'
ms.custom: how-to
ms.date: 11/19/2018
ms.topic: conceptual
ms.assetid: 9a373030-e587-452f-b9a5-c5f9d58b7673
ms.openlocfilehash: 4b3362f71d1ccab0efb03d7e8705c6b3f25f9780
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246521"
---
# <a name="how-to-create-and-use-unique_ptr-instances"></a>Vorgehensweise: Erstellen und Verwenden von unique_ptr Instanzen

Ein [unique_ptr](../standard-library/unique-ptr-class.md) hat seinen Zeiger nicht gemeinsam. Sie kann nicht in eine andere `unique_ptr`kopiert, als Wert an eine Funktion übermittelt oder in einem C++ Standard Bibliotheks Algorithmus verwendet werden, für den Kopien erforderlich sind. Ein `unique_ptr`-Objekt kann nur verschoben werden. Dies bedeutet, dass der Besitz der Arbeitsspeicherressource einem anderen `unique_ptr`-Objekt übertragen wird und das ursprüngliche `unique_ptr`-Objekt diese Ressource nicht mehr besitzt. Es empfiehlt sich, ein Objekt auf einen Besitzer zu beschränken, da mehrere Besitzer die Komplexität der Programmlogik erhöhen. Wenn Sie daher einen intelligenten Zeiger für ein einfaches C++ Objekt benötigen, verwenden Sie `unique_ptr`, und verwenden Sie beim Erstellen einer `unique_ptr`die [make_unique](../standard-library/memory-functions.md#make_unique) Helper-Funktion.

Das folgende Diagramm veranschaulicht die Eigentumsübertragung zwischen zwei `unique_ptr`-Instanzen.

![Verschieben des Besitzes eines eindeutigen&#95;PTR](media/unique_ptr.png "Verschieben des Besitzes eines eindeutigen&#95;PTR")

`unique_ptr` ist im `<memory>`-Header in der C++ Standard Bibliothek definiert. Es ist ebenso effizient wie ein rohzeiger und kann in C++ Standard Bibliotheks Containern verwendet werden. Das Hinzufügen von `unique_ptr` Instanzen C++ zu Standard Bibliotheks Containern ist effizient, da der bewegungskonstruktor des `unique_ptr` den Bedarf an einem Kopiervorgang entfällt.

## <a name="example-1"></a>Beispiel 1

Das folgende Beispiel zeigt, wie `unique_ptr`-Instanzen erstellt und zwischen Funktionen übergeben werden.

[!code-cpp[stl_smart_pointers#210](codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_1.cpp)]

Diese Beispiele zeigen diese grundlegende Eigenschaft des `unique_ptr`-Objekts: Es kann verschoben, jedoch nicht kopiert werden. "Wird verschoben" überträgt den Besitz einem neuen `unique_ptr`-Objekt und setzt das alte `unique_ptr`-Objekt zurück.

## <a name="example-2"></a>Beispiel 2

Im folgenden Beispiel wird die Erstellung von `unique_ptr`-Instanzen und ihre Verwendung in einem Vektor dargestellt.

[!code-cpp[stl_smart_pointers#211](codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_2.cpp)]

Im Bereich der for-Schleife wird das `unique_ptr`-Objekt durch einen Verweis übergeben. Wenn Sie versuchen, das Objekt als Wert zu übergeben, löst der Compiler einen Fehler aus, da der `unique_ptr`-Kopierkonstruktor gelöscht wurde.

## <a name="example-3"></a>Beispiel 3

Das folgende Beispiel zeigt, wie ein `unique_ptr`-Objekt initialisiert wird, das ein Klassenmember ist.

[!code-cpp[stl_smart_pointers#212](codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_3.cpp)]

## <a name="example-4"></a>Beispiel 4

Sie können [make_unique](../standard-library/memory-functions.md#make_unique) verwenden, um eine `unique_ptr` für ein Array zu erstellen, aber Sie können `make_unique` nicht verwenden, um die Array Elemente zu initialisieren.

[!code-cpp[stl_smart_pointers#213](codesnippet/CPP/how-to-create-and-use-unique-ptr-instances_4.cpp)]

Weitere Beispiele finden Sie unter [make_unique](../standard-library/memory-functions.md#make_unique).

## <a name="see-also"></a>Siehe auch

[Intelligente Zeiger (Modern C++)](smart-pointers-modern-cpp.md)<br/>
[make_unique](../standard-library/memory-functions.md#make_unique)
