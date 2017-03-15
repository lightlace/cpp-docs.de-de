---
title: "CDynamicParameterAccessor::SetParamStatus | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicParameterAccessor::SetParamStatus"
  - "ATL.CDynamicParameterAccessor.SetParamStatus"
  - "ATL::CDynamicParameterAccessor::SetParamStatus"
  - "CDynamicParameterAccessor.SetParamStatus"
  - "SetParamStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetParamStatus-Methode"
ms.assetid: 0c2271f6-457d-46ca-88b7-4590aadb20d7
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicParameterAccessor::SetParamStatus
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt den Status des angegebenen Parameters fest, der im Puffer gespeichert wird.  
  
## Syntax  
  
```  
  
      bool SetParamStatus(  
   DBORDINAL nParam,  
   DBSTATUS status  
);  
```  
  
#### Parameter  
 `nParam`  
 \[in\] die einen Parameterwert \(Offset von 1\).  Parameter 0 wird für Rückgabewerte reserviert.  In einen Parameterwert ist der Index des Parameters anhand ihrer Reihenfolge im SQL\- oder Prozeduraufruf.  Ein Beispiel finden Sie unter [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md).  
  
 *status*  
 \[in\] Der `DBSTATUS` Status des angegebenen Parameters.  Weitere Informationen über `DBSTATUS`\-Werte, finden Sie unter [Status](https://msdn.microsoft.com/en-us/library/ms722617.aspx) in der *OLE* DB\-Programmierreferenz, oder indem Sie für `DBSTATUS` in oledb.h.  
  
## Hinweise  
 **true** Gibt bei Erfolg oder **false** auf Fehler.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDynamicParameterAccessor\-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)