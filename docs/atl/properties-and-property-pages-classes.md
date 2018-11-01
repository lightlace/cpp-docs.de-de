---
title: Eigenschaften und Eigenschaftenseitenklassen (ATL)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vc.atl.properties
helpviewer_keywords:
- property pages, classes
- properties [ATL], classes
- properties [ATL]
ms.assetid: 31616f98-69f8-48b2-8d58-b8e7d1c2b2d8
ms.openlocfilehash: 9c56638c72328a59223f3323d55f4dcc6ced2609
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50474060"
---
# <a name="properties-and-property-pages-classes"></a>Eigenschaften und Eigenschaftenseitenklassen

Die folgenden Klassen unterstützen Eigenschaften und Eigenschaftenseiten:

- [CComDispatchDriver](../atl/reference/atl-typedefs.md#ccomdispatchdriver) Ruft ab oder legt die Eigenschaften eines Objekts über eine `IDispatch` Zeiger.

- [CStockPropImpl](../atl/reference/cstockpropimpl-class.md) implementiert die Basiseigenschaften, ATL unterstützt

- [IPerPropertyBrowsingImpl](../atl/reference/iperpropertybrowsingimpl-class.md) greift auf die Informationen in den Eigenschaftenseiten eines Objekts.

- [IPersistPropertyBagImpl](../atl/reference/ipersistpropertybagimpl-class.md) speichert die Eigenschaften eines Objekts in einem Client bereitgestellte Eigenschaftenbehälter.

- [IPropertyPageImpl](../atl/reference/ipropertypageimpl-class.md) eine bestimmten Eigenschaftenseite in einem Eigenschaftenblatt verwaltet.

- [IPropertyPage2Impl](../atl/reference/ipropertypage2impl-class.md) ähnlich wie `IPropertyPageImpl`, sondern auch einen Client eine bestimmte Eigenschaft auf einer Eigenschaftenseite auszuwählen.

- [ISpecifyPropertyPagesImpl](../atl/reference/ispecifypropertypagesimpl-class.md) CLSIDs für die Eigenschaftenseiten, die von einem Objekt unterstützten erhält.

## <a name="related-articles"></a>Verwandte Artikel

[ATL-Lernprogramm](../atl/active-template-library-atl-tutorial.md)

[ATL COM-Eigenschaftenseiten](../atl/atl-com-property-pages.md)

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../atl/atl-class-overview.md)<br/>
[Eigenschaftenzuordnungs-Makros](../atl/reference/property-map-macros.md)

