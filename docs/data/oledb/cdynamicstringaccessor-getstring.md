---
title: 'CDynamicStringAccessor:: GetString | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicStringAccessor.GetString
- CDynamicStringAccessor::GetString
dev_langs:
- C++
helpviewer_keywords:
- GetString method
ms.assetid: 4af27f27-7589-49f5-93d8-6ef05c023c8a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cc23fe73eb0d804d0b53950885b1b83aba58ff91
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096547"
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