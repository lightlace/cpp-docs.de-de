---
title: 'CCommand:: GetParameterInfo | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5006d4bfa042ca0356c42127aeb919339dc61724
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
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