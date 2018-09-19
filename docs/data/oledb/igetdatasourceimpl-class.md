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
ms.openlocfilehash: 9ecc830937e36e213177205549ee4dd4e989e0ed
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118699"
---
# <a name="igetdatasourceimpl-class"></a>IGetDataSourceImpl-Klasse

Stellt eine Implementierung der [IGetDataSource](/previous-versions/windows/desktop/ms709721\(v=vs.85\)) Objekt.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class T>  
class ATL_NO_VTABLE IGetDataSourceImpl : public IGetDataSource  
```  
  
### <a name="parameters"></a>Parameter  

*T*<br/>
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

Finden Sie unter [IGetDataSource::GetDataSource](/previous-versions/windows/desktop/ms725443\(v=vs.85\)) in die *OLE DB-Programmierreferenz*.  
  
### <a name="remarks"></a>Hinweise  

Nützlich, wenn Sie auf Eigenschaften in das neue Datenquellenobjekt zugreifen müssen.  
  
## <a name="see-also"></a>Siehe auch  

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)