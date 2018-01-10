---
title: CAccessorBase-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CAccessorBase
dev_langs: C++
helpviewer_keywords: CAccessorBase class
ms.assetid: 389b65be-11ca-4ae0-9290-60c621c4982b
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9b7c12430c4e7a6872afd46e72e93a29a3189333
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="caccessorbase-class"></a>CAccessorBase-Klasse
Alle Accessoren in den OLE DB-Vorlagen, die von dieser Klasse abgeleitet werden. `CAccessorBase`ermöglicht ein Rowset, um mehrere Accessoren zu verwalten. Darüber hinaus Bindung für Parameter und Ausgabespalten.  
  
## <a name="syntax"></a>Syntax  
  
```  
// Replace with syntax  
```  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[Schließen](../../data/oledb/caccessorbase-close.md)|Schließt die Accessoren.|  
|[GetHAccessor](../../data/oledb/caccessorbase-gethaccessor.md)|Ruft das Accessorhandle ab.|  
|[GetNumAccessors](../../data/oledb/caccessorbase-getnumaccessors.md)|Ruft die Anzahl der Accessoren, die von der Klasse erstellt.|  
|[IsAutoAccessor](../../data/oledb/caccessorbase-isautoaccessor.md)|Testet, ob der angegebene Accessor ein Autoaccessor handelt.|  
|[ReleaseAccessors](../../data/oledb/caccessorbase-releaseaccessors.md)|Gibt die Accessoren frei.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)