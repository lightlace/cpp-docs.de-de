---
title: 'ICommandImpl:: Getdbsession | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ICommandImpl::GetDBSession
- GetDBSession
- ICommandImpl.GetDBSession
dev_langs:
- C++
helpviewer_keywords:
- GetDBSession method
ms.assetid: e5b1cb13-453f-4698-90bf-f6bfe6814a54
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 116838ebb5857d5761b9d58d4f84e315de56d240
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icommandimplgetdbsession"></a>ICommandImpl::GetDBSession
Gibt einen Schnittstellenzeiger zurück, mit der Sitzung, die der Befehl erstellt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD (GetDBSession) (REFIID riid,  
   IUnknown** ppSession);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [ICommand::GetDBSession](https://msdn.microsoft.com/en-us/library/ms719622.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="remarks"></a>Hinweise  
 Hilfreich zum Abrufen von Eigenschaften aus der Sitzung.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [ICommandImpl-Klasse](../../data/oledb/icommandimpl-class.md)