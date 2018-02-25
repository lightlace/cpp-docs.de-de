---
title: IRowsetIdentityImpl-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::IRowsetIdentityImpl
- ATL.IRowsetIdentityImpl
- IRowsetIdentityImpl
dev_langs:
- C++
helpviewer_keywords:
- IRowsetIdentityImpl class
ms.assetid: 56821edf-e045-40c8-96bd-231552cd5799
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: da2833ba774035da38deb2bf4f0e0afc892e6caf
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="irowsetidentityimpl-class"></a>IRowsetIdentityImpl-Klasse
Implementiert die OLE DB- [IRowsetIdentity](https://msdn.microsoft.com/en-us/library/ms715913.aspx) -Schnittstelle, die Tests für Zeilenidentität ermöglicht.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class T, class RowClass = CSimpleRow>  
class ATL_NO_VTABLE IRowsetIdentityImpl   
   : public IRowsetIdentity  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Eine abgeleitete Klasse `IRowsetIdentityImpl`.  
  
 `RowClass`  
 Die Einheit für die Speicherung der **HROW**.  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[IsSameRow](../../data/oledb/irowsetidentityimpl-issamerow.md)|Vergleicht zwei Zeilenhandles, um festzustellen, ob sie auf der gleichen Zeile verweisen.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)