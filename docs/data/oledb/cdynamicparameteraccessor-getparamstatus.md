---
title: 'CDynamicParameterAccessor:: Getparamstatus | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDynamicParameterAccessor::GetParamStatus
- CDynamicParameterAccessor.GetParamStatus
- ATL.CDynamicParameterAccessor.GetParamStatus
- ATL::CDynamicParameterAccessor::GetParamStatus
- GetParamStatus
dev_langs:
- C++
helpviewer_keywords:
- GetParamStatus method
ms.assetid: 9300225a-616c-4a7d-82d0-8c2ecd4d8185
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 89c4e97617018645dfea347f9a5f5e6155506f7b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicparameteraccessorgetparamstatus"></a>CDynamicParameterAccessor::GetParamStatus
Ruft den Status des angegebenen Parameters ab, der im Puffer gespeichert ist.  
  
## <a name="syntax"></a>Syntax  
  
```
bool GetParamStatus(DBORDINAL nParam,  
  DBSTATUS* pStatus);  

DBSTATUS* GetParamStatus(DBORDINAL nParam) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `nParam`  
 [in] Die Parameteranzahl (Offset von 1). Parameter 0 ist für Rückgabewerte reserviert. Die Parameteranzahl ist der Index des Parameters basierend auf der Reihenfolge der SQL-oder einen Aufruf einer gespeicherten Prozedur. Finden Sie unter [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) ein Beispiel.  
  
 `pStatus`  
 [out] Ein Zeiger auf die Variable mit dem `DBSTATUS` Status des angegebenen Parameters. Informationen zu `DBSTATUS` -Werte finden Sie in [Status](https://msdn.microsoft.com/en-us/library/ms722617.aspx) in der *OLE DB Programmer's Reference*, oder suchen Sie nach `DBSTATUS` in "OleDb.h".  
  
## <a name="remarks"></a>Hinweise  
 Die erste überschreiben gibt **"true"** bei Erfolg oder **"false"** bei einem Fehler. Die zweite Überschreiben verweist auf den Speicher mit dem Status des angegebenen Parameters.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDynamicParameterAccessor-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)