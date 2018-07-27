---
title: IGetDataSourceImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IGetDataSourceImpl
- ATL.IGetDataSourceImpl<T>
- ATL.IGetDataSourceImpl
- ATL::IGetDataSourceImpl
- ATL::IGetDataSourceImpl<T>
- GetDataSource
- IGetDataSourceImpl.GetDataSource
- IGetDataSourceImpl::GetDataSource
dev_langs:
- C++
helpviewer_keywords:
- IGetDataSourceImpl class
- GetDataSource method
ms.assetid: d63f3178-d663-4f01-8c09-8aab2dd6805a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 558578a82f1906d7481abebc5e1f1719b1983724
ms.sourcegitcommit: b0d6777cf4b580d093eaf6104d80a888706e7578
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2018
ms.locfileid: "39269936"
---
# <a name="igetdatasourceimpl-class"></a>IGetDataSourceImpl-Klasse
Stellt eine Implementierung der [IGetDataSource](https://msdn.microsoft.com/library/ms709721.aspx) Objekt.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class T>  
class ATL_NO_VTABLE IGetDataSourceImpl : public IGetDataSource  
```  
  
### <a name="parameters"></a>Parameter  
 *T*  
 Abgeleitet von die Klasse `IGetDataSourceImpl`.  

## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="members"></a>Member  
  
### <a name="interface-methods"></a>Schnittstellenmethoden  
  
|||  
|-|-|  
|[GetDataSource](#getdatasource)|Gibt einen Schnittstellenzeiger auf das Datenquellenobjekt, das die Sitzung erstellt haben.|  
  
## <a name="remarks"></a>Hinweise  
 Dies ist eine erforderliche Schnittstelle für die Sitzung erhalten Sie einen Schnittstellenzeiger auf das Datenquellenobjekt.  

## <a name="getdatasource"></a> Igetdatasourceimpl:: GetDatasource
Gibt einen Schnittstellenzeiger auf das Datenquellenobjekt, das die Sitzung erstellt haben.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD(GetDataSource)(REFIID riid,   
   IUnknown ** ppDataSource);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IGetDataSource::GetDataSource](https://msdn.microsoft.com/library/ms725443.aspx) in die *OLE DB-Programmierreferenz*.  
  
### <a name="remarks"></a>Hinweise  
 Nützlich, wenn Sie auf Eigenschaften in das neue Datenquellenobjekt zugreifen müssen.  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)
