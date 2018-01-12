---
title: IGetDataSourceImpl-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IGetDataSourceImpl
- ATL.IGetDataSourceImpl<T>
- ATL.IGetDataSourceImpl
- ATL::IGetDataSourceImpl
- ATL::IGetDataSourceImpl<T>
dev_langs: C++
helpviewer_keywords: IGetDataSourceImpl class
ms.assetid: d63f3178-d663-4f01-8c09-8aab2dd6805a
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c83ab71b7b19d410dd0157f3400ebc1a58a63916
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="igetdatasourceimpl-class"></a>IGetDataSourceImpl-Klasse
Stellt eine Implementierung von der [IGetDataSource](https://msdn.microsoft.com/en-us/library/ms709721.aspx) Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class T>  
class ATL_NO_VTABLE IGetDataSourceImpl : public IGetDataSource  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `IGetDataSourceImpl`.  
  
## <a name="members"></a>Member  
  
### <a name="interface-methods"></a>Schnittstellenmethoden  
  
|||  
|-|-|  
|[GetDataSource](../../data/oledb/igetdatasourceimpl-getdatasource.md)|Gibt einen Schnittstellenzeiger auf das Datenquellenobjekt, das die Sitzung erstellt.|  
  
## <a name="remarks"></a>Hinweise  
 Dies ist eine erforderliche Schnittstelle für die Sitzung, um einen Schnittstellenzeiger auf das Datenquellenobjekt zu erhalten.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)