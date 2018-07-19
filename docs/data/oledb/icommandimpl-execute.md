---
title: 'ICommandImpl:: Execute | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ICommandImpl::Execute
- ICommandImpl.Execute
dev_langs:
- C++
helpviewer_keywords:
- Execute method
ms.assetid: 033e0d4e-256b-4eed-9215-70e0bebb768c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 369c60c1f6407856fb204654794c214fd9ee8b57
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33100768"
---
# <a name="icommandimplexecute"></a>ICommandImpl::Execute
Führt den Befehl.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT Execute(IUnknown* pUnkOuter,  
   REFIID riid,  
   DBPARAMS* pParams,  
   DBROWCOUNT* pcRowsAffected,  
   IUnknown** ppRowset);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [ICommand:: Execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="remarks"></a>Hinweise  
 Der Ausgangsschnittstelle angefordert wird eine Schnittstelle abgerufen werden, aus dem Rowsetobjekt, das diese Funktion erstellt werden.  
  
 **Führen Sie** Aufrufe [CreateRowset](../../data/oledb/icommandimpl-createrowset.md). Überschreiben Sie die standardmäßige Implementierung mehr als ein Rowset zu erstellen, oder geben Sie Ihren eigenen Bedingungen für das Erstellen von anderen Rowsets.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [ICommandImpl-Klasse](../../data/oledb/icommandimpl-class.md)   
 [ICommandImpl::CancelExecution](../../data/oledb/icommandimpl-cancelexecution.md)