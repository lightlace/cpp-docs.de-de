---
title: IRowsetCreatorImpl-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0492994193130ffa6a547691490b4da1ae557c8f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33102136"
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