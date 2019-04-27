---
title: Eigenschaften und Eigenschaftenseitenklassen (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- property pages, classes
- properties [ATL], classes
- properties [ATL]
ms.assetid: 31616f98-69f8-48b2-8d58-b8e7d1c2b2d8
ms.openlocfilehash: 05c3a67e278389bb2ab1b07e9d6cf63cbe347c63
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62249625"
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
