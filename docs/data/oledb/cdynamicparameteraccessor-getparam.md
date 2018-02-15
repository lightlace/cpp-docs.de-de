---
title: 'CDynamicParameterAccessor:: GetParam | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicParameterAccessor::GetParam
- ATL.CDynamicParameterAccessor.GetParam
- CDynamicParameterAccessor::GetParam<ctype>
- CDynamicParameterAccessor.GetParam
- GetParam
- ATL::CDynamicParameterAccessor::GetParam<ctype>
- ATL::CDynamicParameterAccessor::GetParam
dev_langs:
- C++
helpviewer_keywords:
- GetParam method
ms.assetid: 893a6bf8-7b55-4f6d-8a10-a43b13be7f56
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a54da47714be4f0230145b3aa5d8b66df44e3679
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="cdynamicparameteraccessorgetparam"></a>CDynamicParameterAccessor::GetParam
Ruft die Zeichenfolgendaten für einen angegebenen Parameter aus dem Parameterpuffer ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
template <class ctype>bool GetParam(DBORDINAL nParam,   
  ctype* pData) const throw();  

template <class ctype> bool GetParam(TCHAR* pParamName,   
   ctype* pData) const throw();  

void* GetParam(DBORDINAL nParam) const throw();  

void* GetParam(TCHAR* pParamName) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `ctype`  
 Ein aus einer Vorlage gebildete-Parameter, der den Datentyp darstellt.  
  
 `nParam`  
 [in] Die Parameteranzahl (Offset von 1). Parameter 0 ist für Rückgabewerte reserviert. Die Parameteranzahl ist der Index des Parameters basierend auf der Reihenfolge der SQL-oder einen Aufruf einer gespeicherten Prozedur. Finden Sie unter [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) ein Beispiel.  
  
 `pParamName`  
 [in] Der Name des Parameters.  
  
 `pData`  
 [out] Der Zeiger auf den Speicher mit den Daten aus dem Puffer abgerufen werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 Für auf Vorlagen basierende Versionen abgerufen, verweist auf den Speicher mit den Daten aus dem Puffer. Für auf Vorlagen basierende Versionen gibt **"true"** bei Erfolg oder **"false"** bei einem Fehler.  
  
 Verwendung `GetParam` abzurufenden Objektressourcen Parameterdaten aus dem Puffer. Verwendung [GetParamString](../../data/oledb/cdynamicparameteraccessor-getparamstring.md) abzurufenden Zeichenfolge Parameterdaten aus dem Puffer.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDynamicParameterAccessor-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)