---
title: IDBCreateCommandImpl-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::IDBCreateCommandImpl
- IDBCreateCommandImpl
- ATL.IDBCreateCommandImpl
dev_langs:
- C++
helpviewer_keywords:
- IDBCreateCommandImpl class
ms.assetid: eac4755e-1668-42e1-958e-a35620c385ae
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3a4e5d676c004c7439b58631e87fbe0ac1e1af22
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="idbcreatecommandimpl-class"></a>IDBCreateCommandImpl-Klasse
Stellt eine Implementierung von der [IDBCreateCommand](https://msdn.microsoft.com/en-us/library/ms711625.aspx) Schnittstelle.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class T, class CommandClass >  
class ATL_NO_VTABLE IDBCreateCommandImpl   
   : public IDBCreateCommand  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Das Sitzungsobjekt abgeleitet `IDBCreateCommandImpl`.  
  
 `CommandClass`  
 Command-Klasse.  
  
## <a name="members"></a>Member  
  
### <a name="interface-methods"></a>Schnittstellenmethoden  
  
|||  
|-|-|  
|[CreateCommand](../../data/oledb/idbcreatecommandimpl-createcommand.md)|Erstellt einen neuen Befehl.|  
  
## <a name="remarks"></a>Hinweise  
 Eine optionale Schnittstelle für das Sitzungsobjekt, um einen neuen Befehl zu erhalten.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)