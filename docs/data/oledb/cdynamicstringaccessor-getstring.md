---
title: 'CDynamicStringAccessor:: GetString | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicStringAccessor.GetString
- CDynamicStringAccessor::GetString
dev_langs: C++
helpviewer_keywords: GetString method
ms.assetid: 4af27f27-7589-49f5-93d8-6ef05c023c8a
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9fee0b531fa96d9767b28751e2dd8b3766278983
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicstringaccessorgetstring"></a>CDynamicStringAccessor::GetString
Ruft die Daten der angegebenen Spalte als eine Zeichenfolge ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      BaseType* GetString(  
   DBORDINAL nColumn  
) const throw( );  
BaseType* GetString(  
   const CHAR* pColumnName  
) const throw( );  
BaseType* GetString(  
   const WCHAR* pColumnName  
) const throw( );  
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