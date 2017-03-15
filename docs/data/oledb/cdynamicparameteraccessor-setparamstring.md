---
title: "CDynamicParameterAccessor::SetParamString | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CDynamicParameterAccessor.SetParamString"
  - "ATL::CDynamicParameterAccessor::SetParamString"
  - "SetParamString"
  - "CDynamicParameterAccessor::SetParamString"
  - "CDynamicParameterAccessor.SetParamString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetParamString-Methode"
ms.assetid: 77a38d23-7e33-4e5a-bda6-c12c4c3fe2e4
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicParameterAccessor::SetParamString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt die Zeichenfolgendaten des angegebenen Parameters fest, der im Puffer gespeichert wird.  
  
## Syntax  
  
```  
  
      bool SetParamString(   
   DBORDINAL nParam,   
   const CHAR* pString,   
   DBSTATUS status = DBSTATUS_S_OK    
) throw( );  
bool SetParamString(   
   DBORDINAL nParam,   
   const WCHAR* pString,   
   DBSTATUS status = DBSTATUS_S_OK    
) throw( );  
```  
  
#### Parameter  
 `nParam`  
 \[in\] die einen Parameterwert \(Offset von 1\).  Parameter 0 wird für Rückgabewerte reserviert.  In einen Parameterwert ist der Index des Parameters anhand ihrer Reihenfolge im SQL\- oder Prozeduraufruf.  Ein Beispiel finden Sie unter [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md).  
  
 `pString`  
 \[in\] Ein Zeiger in ANSI \(**CHAR**\) oder Zeichenfolgendaten des Unicode \(**WCHAR**\) des angegebenen Parameters.  Siehe `DBSTATUS` in oledb.h.  
  
 *status*  
 \[in\] Der `DBSTATUS` Status des angegebenen Parameters.  Weitere Informationen über `DBSTATUS`\-Werte, finden Sie unter [Status](https://msdn.microsoft.com/en-us/library/ms722617.aspx) in der *OLE* DB\-Programmierreferenz, oder indem Sie für `DBSTATUS` in oledb.h.  
  
## Hinweise  
 **true** Gibt bei Erfolg oder **false** auf Fehler.  
  
 `SetParamString` schlägt fehl, wenn Sie versuchen, eine Zeichenfolge, die größer, als die maximale Größe festzulegen, die für `pString` angegeben wird.  
  
 Verwenden Sie `SetParamString` zum Festlegen Zeichenfolgenparameterdaten im Puffer.  Verwenden Sie [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md), um nonstring Parameterdaten im Puffer festzulegen.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDynamicParameterAccessor\-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)