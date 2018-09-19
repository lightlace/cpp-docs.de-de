---
title: IDBCreateCommandImpl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IDBCreateCommandImpl
- IDBCreateCommandImpl
- ATL.IDBCreateCommandImpl
- IDBCreateCommandImpl.CreateCommand
- CreateCommand
- IDBCreateCommandImpl::CreateCommand
dev_langs:
- C++
helpviewer_keywords:
- IDBCreateCommandImpl class
- CreateCommand method
ms.assetid: eac4755e-1668-42e1-958e-a35620c385ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c6d8a07ded3da02c21c4ee8c528474efc6e52b6c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021563"
---
# <a name="idbcreatecommandimpl-class"></a>IDBCreateCommandImpl-Klasse

Stellt eine Implementierung der [IDBCreateCommand](/previous-versions/windows/desktop/ms711625\(v=vs.85\)) Schnittstelle.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class T, class CommandClass >  
class ATL_NO_VTABLE IDBCreateCommandImpl   
   : public IDBCreateCommand  
```  
  
### <a name="parameters"></a>Parameter  

*T*<br/>
Das Sitzungsobjekt abgeleitet `IDBCreateCommandImpl`.  
  
*CommandClass*<br/>
Command-Klasse.  

## <a name="requirements"></a>Anforderungen  

**Header:** „atldb.h“  
  
## <a name="members"></a>Member  
  
### <a name="interface-methods"></a>Schnittstellenmethoden  
  
|||  
|-|-|  
|[CreateCommand](#createcommand)|Erstellt einen neuen Befehl.|  
  
## <a name="remarks"></a>Hinweise  

Eine optionale Schnittstelle für das Sitzungsobjekt, um einen neuen Befehl zu erhalten.  

## <a name="createcommand"></a> Idbcreatecommandimpl:: CreateCommand

Erstellt einen neuen Befehl ein, und gibt die angeforderte Schnittstelle zurück.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
STDMETHOD(CreateCommand)(IUnknown * pUnkOuter,   
   REFIID riid,   
   IUnknown ** ppvCommand);  
```  
  
#### <a name="parameters"></a>Parameter  

Finden Sie unter [IDBCreateCommand:: CreateCommand](/previous-versions/windows/desktop/ms709772\(v=vs.85\)) in die *OLE DB-Programmierreferenz*.  
  
Einige Parameter entsprechen den *OLE DB-Programmierreferenz* Parameter mit unterschiedlichen Namen, die in beschriebenen `IDBCreateCommand::CreateCommand`:  
  
|OLE DB-Vorlagenparameter|*OLE DB-Programmierreferenz* Parameter|  
|--------------------------------|------------------------------------------------|  
|*ppvCommand*|*ppCommand*|  
  
## <a name="see-also"></a>Siehe auch  

[OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)