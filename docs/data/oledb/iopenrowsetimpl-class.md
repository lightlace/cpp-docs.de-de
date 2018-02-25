---
title: IOpenRowsetImpl-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IOpenRowsetImpl
dev_langs:
- C++
helpviewer_keywords:
- IOpenRowsetImpl class
ms.assetid: d259cedc-1db4-41cf-bc9f-5030907ab486
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 67f457b4a56d57f33a18473e987fa00b6c10b0df
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="iopenrowsetimpl-class"></a>IOpenRowsetImpl-Klasse
Stellt die Implementierung für die `IOpenRowset` Schnittstelle.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class SessionClass>  
class IOpenRowsetImpl : public IOpenRowset  
```  
  
#### <a name="parameters"></a>Parameter  
 `SessionClass`  
 Die Klasse abgeleitet `IOpenRowsetImpl`.  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[CreateRowset](../../data/oledb/iopenrowsetimpl-createrowset.md)|Erstellt ein Rowsetobjekt. Nicht direkt vom Benutzer aufgerufen.|  
|[OpenRowset](../../data/oledb/iopenrowsetimpl-openrowset.md)|Öffnet und gibt ein Rowset, das alle Zeilen aus einer einzelnen Basistabelle oder einem Index enthält. (Nicht im ATLDB. H)|  
  
## <a name="remarks"></a>Hinweise  
 Die [IOpenRowset](https://msdn.microsoft.com/en-us/library/ms716946.aspx) Schnittstelle für ein Sitzungsobjekt obligatorisch ist. Der Code öffnet und gibt ein Rowset, das alle Zeilen aus einer einzelnen Basistabelle oder einem Index enthält.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)