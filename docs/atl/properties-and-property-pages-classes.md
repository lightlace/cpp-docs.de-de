---
title: Eigenschaften und Seiten-Klassen (ATL) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.atl.properties
dev_langs: C++
helpviewer_keywords:
- property pages, classes
- properties [ATL], classes
- properties [ATL]
ms.assetid: 31616f98-69f8-48b2-8d58-b8e7d1c2b2d8
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b6615f09245f4be3d5d98d1507b238c3b0d7b94c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="properties-and-property-pages-classes"></a>Eigenschaft Seiten-Klassen und Eigenschaften
Die folgenden Klassen unterstützen Eigenschaften und Eigenschaftenseiten:  
  
-   [CComDispatchDriver](../atl/reference/atl-typedefs.md#ccomdispatchdriver) Ruft ab oder legt die Eigenschaften eines Objekts über eine `IDispatch` Zeiger.  
  
-   [CStockPropImpl](../atl/reference/cstockpropimpl-class.md) implementiert die Basiseigenschaften, ATL unterstützt  
  
-   [IPerPropertyBrowsingImpl](../atl/reference/iperpropertybrowsingimpl-class.md) greift auf die Informationen in den Eigenschaftenseiten für ein Objekt.  
  
-   [IPersistPropertyBagImpl](../atl/reference/ipersistpropertybagimpl-class.md) Eigenschaften eines Objekts in einem Client bereitgestellte Eigenschaftenbehälter gespeichert.  
  
-   [IPropertyPageImpl](../atl/reference/ipropertypageimpl-class.md) verwaltet eine bestimmte Eigenschaftenseite in einem Eigenschaftenblatt.  
  
-   [IPropertyPage2Impl](../atl/reference/ipropertypage2impl-class.md) ähnelt `IPropertyPageImpl`, aber auch kann ein Client eine bestimmte Eigenschaft auf einer Eigenschaftenseite auswählen.  
  
-   [ISpecifyPropertyPagesImpl](../atl/reference/ispecifypropertypagesimpl-class.md) erhält die CLSIDs für Eigenschaftenseiten, die von einem Objekt unterstützt.  
  
## <a name="related-articles"></a>Verwandte Artikel  
 [ATL-Lernprogramm](../atl/active-template-library-atl-tutorial.md)  
  
 [ATL COM-Eigenschaftenseiten](../atl/atl-com-property-pages.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../atl/atl-class-overview.md)   
 [Eigenschaftenzuordnungs-Makros](../atl/reference/property-map-macros.md)

