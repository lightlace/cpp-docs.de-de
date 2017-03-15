---
title: "CDynamicParameterAccessor::GetParamStatus | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicParameterAccessor::GetParamStatus"
  - "CDynamicParameterAccessor.GetParamStatus"
  - "ATL.CDynamicParameterAccessor.GetParamStatus"
  - "ATL::CDynamicParameterAccessor::GetParamStatus"
  - "GetParamStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetParamStatus-Methode"
ms.assetid: 9300225a-616c-4a7d-82d0-8c2ecd4d8185
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicParameterAccessor::GetParamStatus
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft den Status des angegebenen Parameters ab, der im Puffer gespeichert wird.  
  
## Syntax  
  
```  
  
      bool GetParamStatus(  
   DBORDINAL nParam,  
   DBSTATUS* pStatus  
);  
DBSTATUS* GetParamStatus(   
   DBORDINAL nParam    
) const throw( );  
```  
  
#### Parameter  
 `nParam`  
 \[in\] die einen Parameterwert \(Offset von 1\).  Parameter 0 wird für Rückgabewerte reserviert.  In einen Parameterwert ist der Index des Parameters anhand ihrer Reihenfolge im SQL\- oder Prozeduraufruf.  Ein Beispiel finden Sie unter [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md).  
  
 `pStatus`  
 \[out\] Ein Zeiger auf die Variable `DBSTATUS`, die den Status des angegebenen Parameters enthält.  Weitere Informationen über `DBSTATUS`\-Werte, finden Sie unter [Status](https://msdn.microsoft.com/en-us/library/ms722617.aspx) in der *OLE* DB\-Programmierreferenz, oder indem Sie für `DBSTATUS` in oledb.h.  
  
## Hinweise  
 Die erste Überschreibung gibt **true** bei Erfolg oder **false** auf Fehler zurück.  Die zweiten Überschreiben zeigt auf den Arbeitsspeicher, der den Status des angegebenen Parameters enthält.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDynamicParameterAccessor\-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)