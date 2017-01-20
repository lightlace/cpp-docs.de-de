---
title: "CDynamicParameterAccessor::GetParam"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CDynamicParameterAccessor::GetParam"
  - "ATL.CDynamicParameterAccessor.GetParam"
  - "CDynamicParameterAccessor::GetParam<ctype>"
  - "CDynamicParameterAccessor.GetParam"
  - "GetParam"
  - "ATL::CDynamicParameterAccessor::GetParam<ctype>"
  - "ATL::CDynamicParameterAccessor::GetParam"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetParam-Methode"
ms.assetid: 893a6bf8-7b55-4f6d-8a10-a43b13be7f56
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicParameterAccessor::GetParam
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft die nonstring Daten für einen bestimmten Parameter vom Parameterpuffer ab.  
  
## Syntax  
  
```  
  
      template < class ctype > bool GetParam(   
   DBORDINAL nParam,   
   ctype* pData    
) const throw( );  
template < class ctype > bool GetParam(   
   TCHAR* pParamName,   
   ctype* pData    
) const throw( );  
void* GetParam(   
   DBORDINAL nParam    
) const throw( );  
void* GetParam(   
   TCHAR* pParamName    
) const throw( );  
```  
  
#### Parameter  
 `ctype`  
 Ein auf Vorlagen basierenden Parameter, der der Datentyp ist.  
  
 `nParam`  
 \[in\] die einen Parameterwert \(Offset von 1\).  Parameter 0 wird für Rückgabewerte reserviert.  In einen Parameterwert ist der Index des Parameters anhand ihrer Reihenfolge im SQL\- oder Prozeduraufruf.  Ein Beispiel finden Sie unter [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md).  
  
 `pParamName`  
 \[in\] Der Name des Parameters.  
  
 `pData`  
 \[out\] der Zeiger auf den Speicher abgerufen, der die Daten aus dem Puffer enthält.  
  
## Rückgabewert  
 Nicht auf Vorlagen basierende Versionen Punkte im Speicher, der die Daten abgerufen aus dem Puffer enthält.  Für auf Vorlagen basierende Versionen, gibt **true** bei Erfolg oder **false** auf Fehler.  
  
 Verwenden Sie `GetParam`, um nonstring Parameterdaten aus dem Puffer abrufen.  Verwenden Sie [GetParamString](../../data/oledb/cdynamicparameteraccessor-getparamstring.md), Zeichenfolgenparameterdaten aus dem Puffer abrufen.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDynamicParameterAccessor\-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)