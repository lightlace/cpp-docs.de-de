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
ms.openlocfilehash: 6a2457ed01214750091bd9ec5a59c9aeac819357
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39336992"
---
# <a name="idbcreatecommandimpl-class"></a>IDBCreateCommandImpl-Klasse
Stellt eine Implementierung der [IDBCreateCommand](https://msdn.microsoft.com/library/ms711625.aspx) Schnittstelle.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class T, class CommandClass >  
class ATL_NO_VTABLE IDBCreateCommandImpl   
   : public IDBCreateCommand  
```  
  
### <a name="parameters"></a>Parameter  
 *T*  
 Das Sitzungsobjekt abgeleitet `IDBCreateCommandImpl`.  
  
 *CommandClass*  
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
 Finden Sie unter [IDBCreateCommand:: CreateCommand](https://msdn.microsoft.com/library/ms709772.aspx) in die *OLE DB-Programmierreferenz*.  
  
 Einige Parameter entsprechen den *OLE DB-Programmierreferenz* Parameter mit unterschiedlichen Namen, die in beschriebenen `IDBCreateCommand::CreateCommand`:  
  
|OLE DB-Vorlagenparameter|*OLE DB-Programmierreferenz* Parameter|  
|--------------------------------|------------------------------------------------|  
|*ppvCommand*|*ppCommand*|  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)