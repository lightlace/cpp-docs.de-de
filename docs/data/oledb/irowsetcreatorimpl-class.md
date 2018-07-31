---
title: IRowsetCreatorImpl-Klasse | Microsoft-Dokumentation
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
- IRowsetCreatorImpl.SetSite
- IRowsetCreatorImpl<T>::SetSite
- IRowsetCreatorImpl::SetSite
- SetSite
- ATL.IRowsetCreatorImpl.SetSite
- ATL::IRowsetCreatorImpl<T>::SetSite
- ATL::IRowsetCreatorImpl::SetSite
- ATL.IRowsetCreatorImpl<T>.SetSite
dev_langs:
- C++
helpviewer_keywords:
- IRowsetCreatorImpl class
- SetSite method
ms.assetid: 92cc950f-7978-4754-8d9a-defa63867d82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0c828708a088c8fe31075a8fe8504f3a1f8c14b4
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337096"
---
# <a name="irowsetcreatorimpl-class"></a>IRowsetCreatorImpl-Klasse
Führt die gleichen Funktionen wie `IObjectWithSite` kann jedoch auch die OLE DB-Eigenschaften `DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS`.  
  
## <a name="syntax"></a>Syntax

```cpp
template < class T >  
class ATL_NO_VTABLE IRowsetCreatorImpl   
   : public IObjectWithSiteImpl< T >  
```  
  
### <a name="parameters"></a>Parameter  
 *T*  
 Eine abgeleitete Klasse `IRowsetCreator`.  

## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[SetSite](#setsite)|Legt fest, die Website, die Rowset-Objekt enthält.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse erbt von [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) und überschreibt [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869). Wenn ein Befehl oder Sitzung Anbieterobjekt ein Rowset erstellt wird, ruft er `QueryInterface` für das Rowsetobjekt, das nach `IObjectWithSite` und ruft `SetSite` übergeben des Rowsetobjekt, das die `IUnkown` Schnittstelle wie die Website-Schnittstelle.  

## <a name="setsite"></a> IRowsetCreatorImpl:: SetSite
Legt fest, die Website, die Rowset-Objekt enthält. Weitere Informationen finden Sie unter [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869).  
  
### <a name="syntax"></a>Syntax  
  
```cpp
STDMETHOD(SetSite )(IUnknown* pCreator);  
```  
  
#### <a name="parameters"></a>Parameter  
 *pCreator*  
 [in] Zeiger auf die `IUnknown` Schnittstellenzeiger auf der Website verwalten von Rowset-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard-HRESULT.  
  
### <a name="remarks"></a>Hinweise  
 Darüber hinaus `IRowsetCreatorImpl::SetSite` ermöglicht OLE DB- `DBPROPCANSCROLLBACKWARDS DBPROPCANFETCHBACKWARDS` Eigenschaften. 

## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)