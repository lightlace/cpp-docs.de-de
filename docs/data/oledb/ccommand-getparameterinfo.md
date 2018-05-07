---
title: 'CCommand:: GetParameterInfo | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- GetParameterInfo
- CCommand.GetParameterInfo
- CCommand::GetParameterInfo
dev_langs:
- C++
helpviewer_keywords:
- GetParameterInfo method
ms.assetid: 9cd9277f-0161-4bd8-ad24-58e5e90b92a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 869675c079a392bb1e1e96656e66ef7742f526c6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="ccommandgetparameterinfo"></a>CCommand::GetParameterInfo
Ruft eine Liste der Parameter des Befehls, ihren Namen und ihre Typen ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT CCommandBase::GetParameterInfo(DB_UPARAMS* pParams,  
   DBPARAMINFO** ppParamInfo,  
   OLECHAR** ppNamesBuffer) throw ();  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [ICommandWithParameters:: GetParameterInfo](https://msdn.microsoft.com/en-us/library/ms714917.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CCommand-Klasse](../../data/oledb/ccommand-class.md)