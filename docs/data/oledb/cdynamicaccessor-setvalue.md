---
title: 'CDynamicAccessor:: SetValue | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDynamicAccessor.SetValue
- ATL::CDynamicAccessor::SetValue
- ATL::CDynamicAccessor::SetValue<ctype>
- CDynamicAccessor.SetValue
- ATL.CDynamicAccessor.SetValue<ctype>
- CDynamicAccessor::SetValue
- CDynamicAccessor::SetValue<ctype>
dev_langs: C++
helpviewer_keywords: SetValue method
ms.assetid: ecc18850-96e5-4845-abe5-ab34ad467238
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 194b87d9422f3e2ebf80fa647353c0cc6f72a5b4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cdynamicaccessorsetvalue"></a>CDynamicAccessor::SetValue
Speichert Daten an eine angegebene Spalte.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      template < class ctype >    
bool SetValue(   
   DBORDINAL nColumn,   
   const ctype& data    
) throw( );  
template < class ctype >    
bool SetValue(   
   const CHAR * pColumnName,   
   const ctype& data    
) throw( );  
template <class ctype>   
bool SetValue(  
   const WCHAR *pColumnName,  
   const ctype& data   
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 `ctype`  
 [in] Ein aus einer Vorlage gebildete Parameter, der einen beliebigen Datentyp aufweisen, mit Ausnahme von Zeichenfolgentypen behandelt (**CHAR\***, **WCHAR\***), die eine besondere Behandlung erfordern. `GetValue`verwendet den entsprechenden Datentyp, der basierend auf den Sie hier angeben.  
  
 `pColumnName`  
 [in] Ein Zeiger auf eine Zeichenfolge, die den Namen der Spalte enthält.  
  
 `data`  
 [in] Der Zeiger auf den Speicher, der Daten enthält.  
  
 `nColumn`  
 [in] Die Nummer der Spalte. Die spaltenzählung beginnt mit 1. Der Wert 0 verweist auf die Lesezeichenspalte, sofern vorhanden.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn Sie Zeichenfolgendaten festlegen möchten, verwenden Sie nicht auf Vorlagen basierende Versionen `GetValue`. Die nicht auf Vorlagen basierende Versionen dieser Methode zurückgeben **"void"\***, welche Punkte der Teil des Puffers, der die angegebene Spaltendaten enthält. Gibt **NULL** , wenn die Spalte nicht gefunden wird.  
  
 Für alle anderen Datentypen ist einfacher zu verwenden, die auf Vorlagen basierenden Versionen `GetValue`. Auf Vorlagen basierende Versionen zurück **"true"** bei Erfolg oder **"false"** bei einem Fehler.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)