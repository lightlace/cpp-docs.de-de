---
title: 'CDynamicStringAccessor:: GetString | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDynamicStringAccessor.GetString
- CDynamicStringAccessor::GetString
dev_langs:
- C++
helpviewer_keywords:
- GetString method
ms.assetid: 4af27f27-7589-49f5-93d8-6ef05c023c8a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7c6a2340ddd0e123720cd59bb2ee0bf8ca58504f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicstringaccessorgetstring"></a>CDynamicStringAccessor::GetString
Ruft die Daten der angegebenen Spalte als eine Zeichenfolge ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      BaseType* GetString(DBORDINAL nColumn) const throw();  

BaseType* GetString(const CHAR* pColumnName) const throw();  

BaseType* GetString(const WCHAR* pColumnName) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `nColumn`  
 [in] Die Nummer der Spalte. Die spaltenzählung beginnt mit 1. Der Wert 0 verweist auf die Lesezeichenspalte, sofern vorhanden.  
  
 `pColumnName`  
 [in] Ein Zeiger auf eine Zeichenfolge, die den Spaltennamen enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den String-Wert, die aus der angegebenen Spalte abgerufen werden. Der Wert ist vom Typ ***BaseType***, werden die **CHAR** oder **WCHAR** abhängig davon, ob _UNICODE oder nicht definiert ist. Gibt NULL zurück, wenn die angegebene Spalte nicht gefunden wird.  
  
## <a name="remarks"></a>Hinweise  
 Die zweite außer Kraft setzen Formular nimmt den Namen der Spalte als eine ANSI-Zeichenfolge an. Das dritte überschreiben Formular nimmt den Namen der Spalte als Unicode-Zeichenfolge.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDynamicStringAccessor-Klasse](../../data/oledb/cdynamicstringaccessor-class.md)