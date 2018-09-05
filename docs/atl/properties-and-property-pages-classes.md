---
title: Klassen (ATL) Eigenschaften und -Eigenschaft von Seiten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.atl.properties
dev_langs:
- C++
helpviewer_keywords:
- property pages, classes
- properties [ATL], classes
- properties [ATL]
ms.assetid: 31616f98-69f8-48b2-8d58-b8e7d1c2b2d8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c71ca9412c9db86421c586c0602eb8e6548df622
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43766752"
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

[Übersicht über die Klasse](../atl/atl-class-overview.md)   
[Eigenschaftenzuordnungs-Makros](../atl/reference/property-map-macros.md)

