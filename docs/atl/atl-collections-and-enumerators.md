---
title: ATL-Auflistungen und -Enumerationen
ms.date: 11/04/2016
helpviewer_keywords:
- enumerator interfaces
- collections, ATL classes
- enumerators, ATL classes
- collection interfaces
ms.assetid: b2d37119-3ab2-4e0a-b65b-f377f07e4098
ms.openlocfilehash: 502bedb1773dc2a6edbd6679d50e9c5946228283
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491903"
---
# <a name="atl-collections-and-enumerators"></a>ATL-Auflistungen und -Enumerationen

Ein `collection` ist ein COM-Objekt, das eine Schnittstelle bereitstellt, die den Zugriff auf eine Gruppe von Datenelementen ermöglicht (Rohdaten oder andere Objekte). Eine Schnittstelle, die den Standards zum Bereitstellen des Zugriffs auf eine Gruppe von Objekten folgt, wird als Auflistungs *Schnittstelle*bezeichnet.

Sammlungs Schnittstellen müssen mindestens eine `Count` Eigenschaft bereitstellen, die die Anzahl der Elemente in der Auflistung zurückgibt, eine `Item` Eigenschaft, die ein Element basierend auf einem Index aus der Auflistung zurückgibt, und eine `_NewEnum` Eigenschaft, die ein-Objekt zurückgibt. Enumerator für die Auflistung. Optional können Auflistungs Schnittstellen `Add` - `Remove` und-Methoden bereitstellen, um das Einfügen oder Löschen von Elementen in die Auflistung `Clear` zu ermöglichen, und eine Methode, um alle Elemente zu entfernen.

Ein `enumerator` ist ein COM-Objekt, das eine Schnittstelle zum Durchlaufen von Elementen in einer Auflistung bereitstellt. Enumeratorschnittstellen bieten seriellen Zugriff auf die Elemente einer Auflistung über vier erforderliche Methoden `Next`:, `Skip`, `Reset`und `Clone`.

Weitere Informationen zu Enumeratorschnittstellen finden Sie unter Lesen von Verweis Inhalten, z. b. der [IEnumString](/windows/win32/api/objidl/nn-objidl-ienumstring) -Schnittstelle.

## <a name="in-this-section"></a>In diesem Abschnitt

[ATL-Auflistungen und -Enumeratorklassen](../atl/atl-collection-and-enumerator-classes.md)<br/>
Beschreibt kurz und stellt Links zu den ATL-Klassen bereit, die Sie beim Implementieren von Auflistungen und Enumeratoren unterstützen.

[Designrichtlinien für Auflistungs- und Enumeratorschnittstellen](../atl/design-principles-for-collection-and-enumerator-interfaces.md)<br/>
Erläutert die verschiedenen Entwurfs Prinzipien hinter den einzelnen Schnittstellentypen.

[Implementieren einer auf der C++-Standardbibliothek basierten Auflistung](../atl/implementing-an-stl-based-collection.md)<br/>
Ein erweitertes Beispiel, das Sie durch die Implementierung einer C++ Standard Bibliotheks basierten Sammlung führt.

## <a name="related-sections"></a>Verwandte Abschnitte

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Enthält Links zu konzeptionellen Themen über die Programmierung mit der Active Template Library.

[Beispiel für ATLCollections](../overview/visual-cpp-samples.md)<br/>
Ein Beispiel, das die Verwendung von `ICollectionOnSTLImpl` und `CComEnumOnSTL`sowie die Implementierung von benutzerdefinierten Kopier Richtlinien Klassen veranschaulicht.

## <a name="see-also"></a>Siehe auch

[Konzepte](../atl/active-template-library-atl-concepts.md)
