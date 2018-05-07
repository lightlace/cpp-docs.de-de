---
title: CAccessorBase-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CAccessorBase
dev_langs:
- C++
helpviewer_keywords:
- CAccessorBase class
ms.assetid: 389b65be-11ca-4ae0-9290-60c621c4982b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f598f49d279085b23e0bd3b94c48620363b5a816
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="caccessorbase-class"></a>CAccessorBase-Klasse
Alle Accessoren in den OLE DB-Vorlagen, die von dieser Klasse abgeleitet werden. `CAccessorBase` ermöglicht ein Rowset, um mehrere Accessoren zu verwalten. Darüber hinaus Bindung für Parameter und Ausgabespalten.  
  
## <a name="syntax"></a>Syntax

```cpp
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