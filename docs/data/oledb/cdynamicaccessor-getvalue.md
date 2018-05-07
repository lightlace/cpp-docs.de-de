---
title: 'CDynamicAccessor:: GetValue | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- GetValue
- CDynamicAccessor::GetValue<ctype>
- ATL.CDynamicAccessor.GetValue<ctype>
- CDynamicAccessor.GetValue
- CDynamicAccessor::GetValue
- ATL.CDynamicAccessor.GetValue
- ATL::CDynamicAccessor::GetValue
- ATL::CDynamicAccessor::GetValue<ctype>
dev_langs:
- C++
helpviewer_keywords:
- GetValue method
ms.assetid: 553f44af-68bc-4cb6-8774-e0940003fa90
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7e43707d4697fbbeece5475f71b7e2f93e731772
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cdynamicaccessorgetvalue"></a>CDynamicAccessor::GetValue
Ruft die Daten für eine angegebene Spalte ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
void* GetValue(DBORDINAL nColumn) const throw();  

void* GetValue(const CHAR* pColumnName) const throw();  

void* GetValue(const WCHAR* pColumnName) const throw();  

template < class ctype >
bool GetValue(DBORDINAL nColumn, ctype* pData) const throw();  

template < class ctype >  
bool GetValue(const CHAR* pColumnName, ctype* pData) const throw();  

template < class ctype >  
bool GetValue(const WCHAR* pColumnName, ctype* pData) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `ctype`  
 [in] Ein aus einer Vorlage gebildete Parameter, der einen beliebigen Datentyp aufweisen, mit Ausnahme von Zeichenfolgentypen behandelt (**CHAR\***, **WCHAR\***), die eine besondere Behandlung erfordern. `GetValue` verwendet den entsprechenden Datentyp, der basierend auf den Sie hier angeben.  
  
 `nColumn`  
 [in] Die Nummer der Spalte. Die spaltenzählung beginnt mit 1. Der Wert 0 verweist auf die Lesezeichenspalte, sofern vorhanden.  
  
 `pColumnName`  
 [in] Der Spaltenname.  
  
 `pData`  
 [out] Der Zeiger auf den Inhalt der angegebenen Spalte.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn Sie Zeichenfolgendaten übergeben möchten, verwenden Sie nicht auf Vorlagen basierende Versionen `GetValue`. Die nicht auf Vorlagen basierende Versionen dieser Methode zurückgeben **"void"\***, welche Punkte der Teil des Puffers, der die angegebene Spaltendaten enthält. Gibt **NULL** , wenn die Spalte nicht gefunden wird.  
  
 Für alle anderen Datentypen ist einfacher zu verwenden, die auf Vorlagen basierenden Versionen `GetValue`. Auf Vorlagen basierende Versionen zurück **"true"** bei Erfolg oder **"false"** bei einem Fehler.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie nicht auf Vorlagen basierende Versionen, um Spalten zurückzugeben, die Zeichenfolgen und für Spalten, die andere Datentypen enthalten die aus einer Vorlage gebildete Versionen enthalten.  
  
 Im Debugmodus befindet, werden Sie eine Assertion erhalten, wenn die Größe des `pData` auf die Größe der Spalte auf den er zeigt ungleich ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)