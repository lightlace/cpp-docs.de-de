---
title: "ATL Collection and Enumerator Classes"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Auflistungsklassen, ATL"
  - "Enumeratoren, ATL-Klassen"
ms.assetid: 6818db73-7094-48d8-a0ca-18147beec362
caps.latest.revision: 10
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# ATL Collection and Enumerator Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL stellt die folgenden Klassen, die Ihnen Auflistungen, zu implementieren und Enumeratoren zu unterstützen.  
  
|Klasse|Description|  
|------------|-----------------|  
|[ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)|Auflistungsschnittstellenimplementierung|  
|[IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)|Enumeratorschnittstellenimplementierung \(nimmt die Daten an, die in einem STL\-kompatiblen Container gespeichert werden\)|  
|[CComEnumImpl](../atl/reference/ccomenumimpl-class.md)|Enumeratorschnittstellenimplementierung \(nimmt die Daten an, die in einem Array gespeichert werden\)|  
|[CComEnumOnSTL](../atl/reference/ccomenumonstl-class.md)|Enumeratorobjektimplementierung \(Verwendung `IEnumOnSTLImpl`\)|  
|[CComEnum](../atl/reference/ccomenum-class.md)|Enumeratorobjektimplementierung \(Verwendung `CComEnumImpl`\)|  
|[\_Copy](../atl/atl-copy-policy-classes.md)|Kopierrichtlinienklasse|  
|[\_CopyInterface](../atl/atl-copy-policy-classes.md)|Kopierrichtlinienklasse|  
|[CAdapt](../atl/reference/cadapt-class.md)|Adapterklasse \(aus **operator &**, das `CComPtr`, `CComQIPtr` und in STL\-Containern gespeichert werden, `CComBSTR` zulassen\)|  
  
## Siehe auch  
 [Auflistungen und Enumerationen](../atl/atl-collections-and-enumerators.md)