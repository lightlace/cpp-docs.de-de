---
title: IRowsetIdentityImpl-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IRowsetIdentityImpl
- ATL.IRowsetIdentityImpl
- IRowsetIdentityImpl
dev_langs: C++
helpviewer_keywords: IRowsetIdentityImpl class
ms.assetid: 56821edf-e045-40c8-96bd-231552cd5799
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cef373c7ddafe17a7843f8559588d5f0da9ee270
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetidentityimpl-class"></a>IRowsetIdentityImpl-Klasse
Implementiert die OLE DB- [IRowsetIdentity](https://msdn.microsoft.com/en-us/library/ms715913.aspx) -Schnittstelle, die Tests für Zeilenidentität ermöglicht.  
  
## <a name="syntax"></a>Syntax  
  
```  
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