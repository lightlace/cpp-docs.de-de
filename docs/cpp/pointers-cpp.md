---
title: Zeiger (C++)
ms.date: 11/19/2019
description: Informationen zu unformatierten Zeigern und C++intelligenten Zeigern in Microsoft.
helpviewer_keywords:
- pointers (C++)
ms.assetid: 595387c5-8e58-4670-848f-344c7caf985e
ms.openlocfilehash: 21dcc55048e9e378f370f25254e1910b05e49d69
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246425"
---
# <a name="pointers-c"></a>Zeiger (C++)

Ein Zeiger ist eine Variable, in der die Speicheradresse eines Objekts gespeichert wird. Zeiger werden sowohl in C als auch C++ in drei Haupt Zwecken verwendet:

- um neue Objekte auf dem Heap zuzuordnen,
- So übergeben Sie Funktionen an andere Funktionen
- zum Iterieren von Elementen in Arrays oder anderen Datenstrukturen.

Bei der Programmierung im C-Stil werden unformatierte *Zeiger* für all diese Szenarien verwendet. Unformatierte Zeiger sind jedoch die Quelle vieler schwerwiegender Programmierfehler. Daher wird von der Verwendung dringend abgeraten, es sei denn, Sie bieten einen erheblichen Leistungsvorteil, und es gibt keine Mehrdeutigkeit, welche Zeiger der *besitzende Zeiger* ist, der für das Löschen des Objekts zuständig ist. Modern C++ stellt *intelligente Zeiger* zum Zuordnen von Objekten, *Iteratoren* zum Durchlaufen von Datenstrukturen und *Lambda-Ausdrücken* für das Übergeben von Funktionen bereit. Wenn Sie diese sprach-und Bibliotheksfunktionen anstelle von unformatierten Zeigern verwenden, machen Sie das Programm sicherer, einfacher zu Debuggen und leichter zu verstehen und zu warten. Weitere Informationen finden Sie unter [intelligente Zeiger](smart-pointers-modern-cpp.md), [Iteratoren](../standard-library/iterators.md)und [Lambda-Ausdrücke](lambda-expressions-in-cpp.md) .

## <a name="in-this-section"></a>In diesem Abschnitt

- [Unformatierte Zeiger](raw-pointers.md)
- [Konstante und flüchtige Zeiger](const-and-volatile-pointers.md)
- [New-und DELETE-Operatoren](new-and-delete-operators.md)
- [Intelligente Zeiger](smart-pointers-modern-cpp.md)
- [Vorgehensweise: Erstellen und Verwenden von unique_ptr Instanzen](how-to-create-and-use-unique-ptr-instances.md)
- [Vorgehensweise: Erstellen und Verwenden von shared_ptr Instanzen](how-to-create-and-use-shared-ptr-instances.md)
- [Vorgehensweise: Erstellen und Verwenden von weak_ptr Instanzen](how-to-create-and-use-weak-ptr-instances.md)
- [Vorgehensweise: Erstellen und Verwenden von CComPtr-und CComQIPtr-Instanzen](how-to-create-and-use-ccomptr-and-ccomqiptr-instances.md)

## <a name="see-also"></a>Siehe auch

[Iteratoren](../standard-library/iterators.md)</br>
[Lambda-Ausdrücke](lambda-expressions-in-cpp.md)
