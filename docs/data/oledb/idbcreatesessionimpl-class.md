---
title: IDBCreateSessionImpl-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IDBCreateSessionImpl
- ATL.IDBCreateSessionImpl
- ATL::IDBCreateSessionImpl
dev_langs:
- C++
helpviewer_keywords:
- IDBCreateSessionImpl class
ms.assetid: 48c02c5c-8362-45ac-af8e-bb119cf8c5c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3e027faa11ec7c2a2b6c8d29ef99fe95419a7594
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33100264"
---
# <a name="idbcreatesessionimpl-class"></a>IDBCreateSessionImpl-Klasse
Stellt eine Implementierung für die [IDBCreateSession](https://msdn.microsoft.com/en-us/library/ms724076.aspx) Schnittstelle.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class T, class SessionClass>  
class ATL_NO_VTABLE IDBCreateSessionImpl   
   : public IDBCreateSession  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 DER KLASSE ABGELEITET WURDE.  
  
 `SessionClass`  
 Das Sitzungsobjekt.  
  
## <a name="members"></a>Member  
  
### <a name="interface-methods"></a>Schnittstellenmethoden  
  
|||  
|-|-|  
|[CreateSession](../../data/oledb/idbcreatesessionimpl-createsession.md)|Erstellt eine neue Sitzung aus dem Datenquellensicht-Objekt und gibt die angeforderte Schnittstelle auf die neu erstellte Sitzung zurück.|  
  
## <a name="remarks"></a>Hinweise  
 Keine verbindliche Schnittstelle für Datenquellenobjekte.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)