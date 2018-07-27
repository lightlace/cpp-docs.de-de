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
ms.openlocfilehash: 1ffc92cecb3b28423aa2e869171f730c956996cd
ms.sourcegitcommit: b0d6777cf4b580d093eaf6104d80a888706e7578
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2018
ms.locfileid: "39269750"
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
