---
title: IDBCreateSessionImpl-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDBCreateSessionImpl
- ATL.IDBCreateSessionImpl
- ATL::IDBCreateSessionImpl
dev_langs: C++
helpviewer_keywords: IDBCreateSessionImpl class
ms.assetid: 48c02c5c-8362-45ac-af8e-bb119cf8c5c7
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f5f8cb4e35c14ddbb8a7f8df3fe3686025cf5eae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="idbcreatesessionimpl-class"></a>IDBCreateSessionImpl-Klasse
Stellt eine Implementierung für die [IDBCreateSession](https://msdn.microsoft.com/en-us/library/ms724076.aspx) Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```  
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