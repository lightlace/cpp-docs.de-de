---
title: IDBCreateSessionImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IDBCreateSessionImpl
- ATL.IDBCreateSessionImpl
- ATL::IDBCreateSessionImpl
- IDBCreateSessionImpl::CreateSession
- IDBCreateSessionImpl.CreateSession
- CreateSession
dev_langs:
- C++
helpviewer_keywords:
- IDBCreateSessionImpl class
- CreateSession method
ms.assetid: 48c02c5c-8362-45ac-af8e-bb119cf8c5c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2e4427eede8efcd492e90597efe9488a89e6d4de
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49082370"
---
# <a name="idbcreatesessionimpl-class"></a>IDBCreateSessionImpl-Klasse

Stellt eine Implementierung für die [IDBCreateSession](/previous-versions/windows/desktop/ms724076) Schnittstelle.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class T, class SessionClass>  
class ATL_NO_VTABLE IDBCreateSessionImpl   
   : public IDBCreateSession  
```  
  
### <a name="parameters"></a>Parameter  

*T*<br/>
DER KLASSE ABGELEITET  
  
*SessionClass*<br/>
Der Session-Objekt.  

## <a name="requirements"></a>Anforderungen  

**Header:** „atldb.h“ 
  
## <a name="members"></a>Member  
  
### <a name="interface-methods"></a>Schnittstellenmethoden  
  
|||  
|-|-|  
|[CreateSession](#createsession)|Erstellt eine neue Sitzung über das Datenquellenobjekt, und gibt die angeforderte Schnittstelle zurück, auf die neu erstellte Sitzung.|  
  
## <a name="remarks"></a>Hinweise  

Eine erforderliche Schnittstelle für Datenquellenobjekte.  

## <a name="createsession"></a> Idbcreatesessionimpl:: CreateSession

Erstellt eine neue Sitzung über das Datenquellenobjekt, und gibt die angeforderte Schnittstelle zurück, auf die neu erstellte Sitzung.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
STDMETHOD(CreateSession)(IUnknown * pUnkOuter,   
   REFIID riid,   
   IUnknown ** ppDBSession);  
```  
  
#### <a name="parameters"></a>Parameter  

Finden Sie unter [IDBCreateSession:: CreateSession](/previous-versions/windows/desktop/ms714942) in die *OLE DB-Programmierreferenz*.   
  
## <a name="see-also"></a>Siehe auch  

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)