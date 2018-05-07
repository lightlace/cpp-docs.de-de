---
title: 'CDynamicParameterAccessor:: Getparamio | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- GetParamIO
- CDynamicParameterAccessor::GetParamIO
- ATL.CDynamicParameterAccessor.GetParamIO
- CDynamicParameterAccessor.GetParamIO
- ATL::CDynamicParameterAccessor::GetParamIO
dev_langs:
- C++
helpviewer_keywords:
- GetParamIO method
ms.assetid: 9c485e39-c67e-4df7-a707-c773019c4d1e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 322fa8fe90d323bc14593028386b119a24377e83
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cdynamicparameteraccessorgetparamio"></a>CDynamicParameterAccessor::GetParamIO
Ermittelt, ob der angegebene Parameter ein Eingabe- oder ein Ausgabeparameter ist.  
  
## <a name="syntax"></a>Syntax  
  
```
bool GetParamIO(DBORDINAL nParam,   
   DBPARAMIO* pParamIO) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `nParam`  
 [in] Die Parameteranzahl (Offset von 1). Parameter 0 ist für Rückgabewerte reserviert. Die Parameteranzahl ist der Index des Parameters basierend auf der Reihenfolge der SQL-oder einen Aufruf einer gespeicherten Prozedur. Finden Sie unter [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) ein Beispiel.  
  
 *pParamIO*  
 Ein Zeiger auf die Variable mit dem **DBPARAMIO** Typ (Eingabe oder Ausgabe) des angegebenen Parameters. Er ist wie folgt definiert:  
  
```  
typedef DWORD DBPARAMIO;  
  
enum DBPARAMIOENUM {  
    DBPARAMIO_NOTPARAM   = 0,  
    DBPARAMIO_INPUT      = 0x1,  
    DBPARAMIO_OUTPUT     = 0x2  
};  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** bei Erfolg oder **"false"** bei einem Fehler.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDynamicParameterAccessor-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)