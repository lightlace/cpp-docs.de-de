---
title: 'CDynamicParameterAccessor:: SetParam | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CDynamicParameterAccessor::SetParam
- ATL::CDynamicParameterAccessor::SetParam<ctype>
- CDynamicParameterAccessor.SetParam
- ATL.CDynamicParameterAccessor.SetParam
- SetParam
- CDynamicParameterAccessor:SetParam
- CDynamicParameterAccessor::SetParam<ctype>
- CDynamicParameterAccessor::SetParam
dev_langs:
- C++
helpviewer_keywords:
- SetParam method
ms.assetid: e2349220-545c-46ad-90da-9113ac52551a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3fcedc0d54e5b25eb4490425253f6c1bfd139a85
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicparameteraccessorsetparam"></a>CDynamicParameterAccessor::SetParam
Legt die Parameterpuffer anhand der angegebenen (keine Zeichenfolgenmethoden) Daten fest.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
template <class ctype>
bool SetParam(DBORDINAL nParam,  
               constctype* pData,  
               DBSTATUS status = DBSTATUS_S_OK) throw();  

template <class ctype>  
bool SetParam(TCHAR* pParamName,  
               const ctype* pData,  
               DBSTATUS status = DBSTATUS_S_OK) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `ctype`  
 Ein aus einer Vorlage gebildete-Parameter, der den Datentyp darstellt.  
  
 `nParam`  
 [in] Die Parameteranzahl (Offset von 1). Parameter 0 ist für Rückgabewerte reserviert. Die Parameteranzahl ist der Index des Parameters basierend auf der Reihenfolge der SQL-oder einen Aufruf einer gespeicherten Prozedur. Zum Beispiel:  
  
 [!code-cpp[NVC_OLEDB_Consumer#8](../../data/oledb/codesnippet/cpp/cdynamicparameteraccessor-setparam_1.cpp)]  
  
 `pParamName`  
 [in] Der Name des Parameters.  
  
 `pData`  
 [in] Der Zeiger auf den Speicher mit den Daten in den Puffer geschrieben werden sollen.  
  
 *status*  
 [in] Die `DBSTATUS` Status in der Spalte. Informationen zu `DBSTATUS` -Werte finden Sie in [Status](https://msdn.microsoft.com/en-us/library/ms722617.aspx) in der *OLE DB Programmer's Reference*, oder suchen Sie nach `DBSTATUS` in "OleDb.h".  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** bei Erfolg oder **"false"** bei einem Fehler.  
  
 Verwendung `SetParam` Zeichenfolgendaten-Parameter im Puffer festgelegt. Verwendung [SetParamString](../../data/oledb/cdynamicparameteraccessor-setparamstring.md) Abfragezeichenfolge-Parameterdaten zur im Puffer festgelegt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDynamicParameterAccessor-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)