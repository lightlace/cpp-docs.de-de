---
title: ATL-Auflistungen und Enumerationen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- enumerator interfaces
- collections, ATL classes
- enumerators, ATL classes
- collection interfaces
ms.assetid: b2d37119-3ab2-4e0a-b65b-f377f07e4098
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6e70e744ca4eb9cfa4b84ac0cca58be2452a8e25
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43756950"
---
# <a name="atl-collections-and-enumerators"></a>ATL-Auflistungen und -Enumerationen

Ein `collection` ist eine COM-Objekt, das eine Schnittstelle bereitstellt, die Zugriff auf eine Gruppe von Datenelementen (unformatierte Daten oder andere Objekte) ermöglicht. Eine Schnittstelle, die den Standards entspricht, für den Zugriff auf eine Gruppe von Objekten als bekannt ist, eine *sammlungsschnittstelle*.

Mindestens Auflistungsschnittstellen bieten müssen eine `Count` Eigenschaft, die die Anzahl der Elemente in der Auflistung zurückgibt ein `Item` Eigenschaft, die ein Element aus der Auflistung, die auf Grundlage eines Indexes, zurückgibt und ein `_NewEnum` Eigenschaft, die zurückgibt ein Enumerator für die Auflistung. Optional können der Sammelschnittstellen angeben `Add` und `Remove` Methoden, um Elemente in eingefügt oder aus der Auflistung gelöscht werden und ein `Clear` Methode, um alle Elemente zu entfernen.

Ein `enumerator` ein COM-Objekt, das eine Schnittstelle zum Durchlaufen der Elemente in einer Auflistung bereitstellt. Enumeratorschnittstellen bieten seriellen Zugriff auf die Elemente einer Sammlung über vier Methoden für die erforderlichen: `Next`, `Skip`, `Reset`, und `Clone`.

Erfahren Sie mehr über Enumeratorschnittstellen lesen referenzinhalt wie z. B. [IEnumString](/windows/desktop/api/objidl/nn-objidl-ienumstring) Schnittstelle.

## <a name="in-this-section"></a>In diesem Abschnitt

[ATL-Auflistungen und -Enumeratorklassen](../atl/atl-collection-and-enumerator-classes.md)  
Beschreibt kurz, und bietet Links zu den ATL-Klassen, mit denen Sie Sammlungen und Enumeratoren implementiert.

[Designrichtlinien für Auflistungs- und Enumeratorschnittstellen](../atl/design-principles-for-collection-and-enumerator-interfaces.md)  
Erläutert, die verschiedene Entwurfsprinzipien für jede Art von Schnittstelle.

[Implementieren einer auf der C++-Standardbibliothek basierten Auflistung](../atl/implementing-an-stl-based-collection.md)  
Ein erweitertes Beispiel, das Sie durch die Implementierung einer C++-Standardbibliothek basierten Auflistung führt.

## <a name="related-sections"></a>Verwandte Abschnitte

[ATL](../atl/active-template-library-atl-concepts.md)  
Enthält Links zu konzeptionellen Themen über die Programmierung mit der Active Template Library.

[-Beispiel](../visual-cpp-samples.md)  
Ein Beispiel, das die Verwendung von veranschaulicht `ICollectionOnSTLImpl` und `CComEnumOnSTL`, und die Implementierung von benutzerdefinierten Kopierrichtlinienklassen.

## <a name="see-also"></a>Siehe auch

[Konzepte](../atl/active-template-library-atl-concepts.md)

