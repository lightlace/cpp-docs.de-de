---
title: 'ICommandImpl:: Getdbsession | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ICommandImpl::GetDBSession
- GetDBSession
- ICommandImpl.GetDBSession
dev_langs: C++
helpviewer_keywords: GetDBSession method
ms.assetid: e5b1cb13-453f-4698-90bf-f6bfe6814a54
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6d848b9bc541c74d6820932335542707c12263e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="icommandimplgetdbsession"></a>ICommandImpl::GetDBSession
Gibt einen Schnittstellenzeiger zurück, mit der Sitzung, die der Befehl erstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      STDMETHOD (GetDBSession) (  
   REFIID riid,  
   IUnknown** ppSession   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [ICommand::GetDBSession](https://msdn.microsoft.com/en-us/library/ms719622.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="remarks"></a>Hinweise  
 Hilfreich zum Abrufen von Eigenschaften aus der Sitzung.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [ICommandImpl-Klasse](../../data/oledb/icommandimpl-class.md)