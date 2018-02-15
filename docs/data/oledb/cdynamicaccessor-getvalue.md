---
title: 'CDynamicAccessor:: GetValue | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1602b784db2f6eac0984ce1fca3fb8d1276b0666
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
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