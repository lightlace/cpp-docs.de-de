---
title: 'ICommandImpl:: Execute | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ICommandImpl::Execute
- ICommandImpl.Execute
dev_langs: C++
helpviewer_keywords: Execute method
ms.assetid: 033e0d4e-256b-4eed-9215-70e0bebb768c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 965a344b55b6d290f112970ff357f383fefcd630
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="icommandimplexecute"></a>ICommandImpl::Execute
Führt den Befehl.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      HRESULT Execute(  
   IUnknown* pUnkOuter,  
   REFIID riid,  
   DBPARAMS* pParams,  
   DBROWCOUNT* pcRowsAffected,  
   IUnknown** ppRowset   
);  
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