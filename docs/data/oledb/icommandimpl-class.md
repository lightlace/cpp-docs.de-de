---
title: ICommandImpl-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ICommandImpl
dev_langs:
- C++
helpviewer_keywords:
- ICommandImpl class
ms.assetid: ef285fef-0d66-45e6-a762-b03357098e3b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 80cc82023131a23ebfea33c5264cf83fdafb1b36
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="icommandimpl-class"></a>ICommandImpl-Klasse
Stellt die Implementierung für die [ICommand](https://msdn.microsoft.com/en-us/library/ms709737.aspx) Schnittstelle.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class T, class CommandBase = ICommand>   
class ATL_NO_VTABLE ICommandImpl : public CommandBase  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `ICommandImpl`.  
  
 `CommandBase`  
 Eine Befehlsschnittstelle. Die Standardeinstellung ist `ICommand`.  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[CancelExecution](../../data/oledb/icommandimpl-cancelexecution.md)|Bricht die Ausführung des aktuellen Befehls ab.|  
|[Abbrechen](../../data/oledb/icommandimpl-cancel.md)|Bricht die Ausführung des aktuellen Befehls ab.|  
|[CreateRowset](../../data/oledb/icommandimpl-createrowset.md)|Erstellt ein Rowsetobjekt.|  
|[Führen Sie](../../data/oledb/icommandimpl-execute.md)|Führt den Befehl.|  
|[GetDBSession](../../data/oledb/icommandimpl-getdbsession.md)|Gibt einen Schnittstellenzeiger zurück, mit der Sitzung, die der Befehl erstellt.|  
|[ICommandImpl](../../data/oledb/icommandimpl-icommandimpl.md)|Der Konstruktor.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|[m_bCancel](../../data/oledb/icommandimpl-m-bcancel.md)|Gibt an, ob der Befehl abgebrochen wird.|  
|[m_bCancelWhenExecuting](../../data/oledb/icommandimpl-m-bcancelwhenexecuting.md)|Gibt an, ob der Befehl ist für die Ausführung abgebrochen wird.|  
|[m_bIsExecuting](../../data/oledb/icommandimpl-m-bisexecuting.md)|Gibt an, ob der Befehl derzeit ausgeführt wird.|  
  
## <a name="remarks"></a>Hinweise  
 Keine verbindliche Schnittstelle für das Command-Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)