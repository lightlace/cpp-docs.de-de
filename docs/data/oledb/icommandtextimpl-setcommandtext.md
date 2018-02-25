---
title: 'ICommandTextImpl:: SetCommandText | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ICommandTextImpl.SetCommandText
- ICommandTextImpl::SetCommandText
- SetCommandText
dev_langs:
- C++
helpviewer_keywords:
- SetCommandText method
ms.assetid: 7271bfb0-7a8b-4281-b3e8-7c80b9fe79d4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6025413a507aa7fb54e0c8672c94e0f8f162f895
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="icommandtextimplsetcommandtext"></a>ICommandTextImpl::SetCommandText
Legt den Befehlstext, und Ersetzen Sie dabei die vorhandenen Befehlstext fest.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD(SetCommandText)(REFGUID rguidDialect,   
   LPCOLESTR pwszCommand);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [ICommandText:: SetCommandText](https://msdn.microsoft.com/en-us/library/ms709757.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [ICommandTextImpl-Klasse](../../data/oledb/icommandtextimpl-class.md)   
 [ICommandTextImpl::GetCommandText](../../data/oledb/icommandtextimpl-getcommandtext.md)