---
title: 'ICommandTextImpl:: Getcommandtext | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- GetCommandText
- ICommandTextImpl.GetCommandText
- ICommandTextImpl::GetCommandText
dev_langs:
- C++
helpviewer_keywords:
- GetCommandText method
ms.assetid: 0f8da470-b1c3-4573-974f-1acc111e3984
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e2f52f17258e4a317f58e40a60583998673f2efd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icommandtextimplgetcommandtext"></a>ICommandTextImpl::GetCommandText
Gibt den Text Befehlssatz, der vom letzten Aufruf von [SetCommandText](../../data/oledb/icommandtextimpl-setcommandtext.md).  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD(GetCommandText)(GUID * pguidDialect,   
   LPOLESTR * ppwszCommand);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [ICommandText::GetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) in der *OLE DB Programmer's Reference*. Die *PguidDialect* Parameter ist standardmäßig ignoriert.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [ICommandTextImpl-Klasse](../../data/oledb/icommandtextimpl-class.md)