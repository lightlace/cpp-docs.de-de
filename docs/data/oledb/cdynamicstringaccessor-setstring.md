---
title: 'CDynamicStringAccessor:: SetString | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicStringAccessor::SetString
- CDynamicStringAccessor.SetString
dev_langs:
- C++
helpviewer_keywords:
- SetString method
ms.assetid: 94846d8b-4c1b-47fe-acdc-1752981cee25
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f5f4b7f9354de7f6c6ad10ba472bfd31873a0355
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33095904"
---
# <a name="cdynamicstringaccessorsetstring"></a>CDynamicStringAccessor::SetString
Legt die angegebene Spalte als eine Zeichenfolge fest.  
  
## <a name="syntax"></a>Syntax  
  
```
HRESULT SetString(DBORDINAL nColumn,  
  BaseType* data) throw();  


HRESULT SetString(const CHAR* pColumnName,  
   BaseType* data) throw();  


HRESULT SetString(const WCHAR* pColumnName,  
   BaseType* data) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `nColumn`  
 [in] Die Nummer der Spalte. Die spaltenzählung beginnt mit 1. Der spezielle Wert 0 verweist auf die Lesezeichenspalte, sofern vorhanden.  
  
 `pColumnName`  
 [in] Ein Zeiger auf eine Zeichenfolge, die den Spaltennamen enthält.  
  
 `data`  
 [in] Ein Zeiger auf die Zeichenfolgendaten in der angegebenen Spalte geschrieben werden sollen.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den String-Wert, auf die angegebene Spalte festgelegt. Der Wert ist vom Typ `BaseType`, werden die `CHAR` oder `WCHAR` je nachdem, ob `_UNICODE` oder nicht definiert ist.  
  
## <a name="remarks"></a>Hinweise  
 Die zweite Form nimmt überschreiben den Spaltennamen als eine ANSI-Zeichenfolge, und die dritte überschreiben Formular nimmt den Spaltennamen als Unicode-Zeichenfolge.  
  
 Wenn `_SECURE_ATL` definiert um einen Wert ungleich NULL haben, den Fall eines Laufzeitfehlers Assertion wird generiert, wenn die Eingabe `data` Zeichenfolge ist länger als die maximal zulässige Länge der Spalte auf den verwiesen wird. Andernfalls wird die Eingabezeichenfolge wird jedoch länger als die maximal zulässige Länge abgeschnitten.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDynamicStringAccessor-Klasse](../../data/oledb/cdynamicstringaccessor-class.md)