---
title: 'CDynamicAccessor:: SetLength | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CDynamicAccessor::SetLength
- CDynamicAccessor.SetLength
- CDynamicAccessor::SetLength
- ATL.CDynamicAccessor.SetLength
dev_langs: C++
helpviewer_keywords: SetLength method
ms.assetid: 8109ae73-04ec-4a47-be97-ba1e60080384
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 364c6d7bbf33abd0b9a4f2e09cb6760f9a21e4d3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cdynamicaccessorsetlength"></a>CDynamicAccessor::SetLength
Legt die Länge der angegebenen Spalte.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      bool SetLength(   
   DBORDINAL nColumn,   
   DBLENGTH nLength    
) throw( );  
bool SetLength(   
   const CHAR* pColumnName,   
   DBLENGTH nLength    
) throw( );  
bool SetLength(   
   const WCHAR* pColumnName,   
   DBLENGTH nLength    
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 `nColumn`  
 [in] Die Nummer der Spalte. Die spaltenzählung beginnt mit 1. Der Wert 0 verweist auf die Lesezeichenspalte, sofern vorhanden.  
  
 `nLength`  
 [in] Die Länge der Spalte in Bytes.  
  
 `pColumnName`  
 [in] Ein Zeiger auf eine Zeichenfolge, die den Namen der Spalte enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** , wenn die Länge der angegebenen Spalte festgelegt ist. Andernfalls, gibt diese Funktion **"false"**.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicAccessor::GetLength](../../data/oledb/cdynamicaccessor-getlength.md)