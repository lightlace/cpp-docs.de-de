---
title: IRowsetCreatorImpl-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::IRowsetCreatorImpl
- ATL.IRowsetCreatorImpl
- ATL::IRowsetCreatorImpl<T>
- ATL.IRowsetCreatorImpl<T>
- IRowsetCreatorImpl
dev_langs:
- C++
helpviewer_keywords:
- IRowsetCreatorImpl class
ms.assetid: 92cc950f-7978-4754-8d9a-defa63867d82
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 51d984f2254c8a2a135b5ecb386e8f195946366b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="irowsetcreatorimpl-class"></a>IRowsetCreatorImpl-Klasse
Führt die gleichen Funktionen wie `IObjectWithSite` können jedoch auch die Eigenschaften des OLE DB- **DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS**.  
  
## <a name="syntax"></a>Syntax

```cpp
template < class T >  
class ATL_NO_VTABLE IRowsetCreatorImpl   
   : public IObjectWithSiteImpl< T >  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Eine abgeleitete Klasse **IRowsetCreator**.  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[SetSite](../../data/oledb/irowsetcreatorimpl-setsite.md)|Legt die Website, die Rowset-Objekte enthält.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse erbt von ["IObjectWithSite"](http://msdn.microsoft.com/library/windows/desktop/ms693765) und überschreibt [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869). Wenn ein Befehl oder Sitzung Anbieterobjekt ein Rowset erstellt, ruft er `QueryInterface` für die Suche nach Rowsetobjekt `IObjectWithSite` und ruft `SetSite` und übergeben des Rowsetobjekt **IUnkown** Schnittstelle als die Standort-Schnittstelle.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)