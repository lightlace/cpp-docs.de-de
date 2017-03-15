---
title: "CDynamicParameterAccessor::GetParamIO | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetParamIO"
  - "CDynamicParameterAccessor::GetParamIO"
  - "ATL.CDynamicParameterAccessor.GetParamIO"
  - "CDynamicParameterAccessor.GetParamIO"
  - "ATL::CDynamicParameterAccessor::GetParamIO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetParamIO-Methode"
ms.assetid: 9c485e39-c67e-4df7-a707-c773019c4d1e
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CDynamicParameterAccessor::GetParamIO
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bestimmt, ob der angegebene Parameter einen Ein\- oder Ausgabeparameter handelt.  
  
## Syntax  
  
```  
  
      bool GetParamIO(   
   DBORDINAL nParam,   
   DBPARAMIO * pParamIO    
) const throw( );  
```  
  
#### Parameter  
 `nParam`  
 \[in\] die einen Parameterwert \(Offset von 1\).  Parameter 0 wird für Rückgabewerte reserviert.  In einen Parameterwert ist der Index des Parameters anhand ihrer Reihenfolge im SQL\- oder Prozeduraufruf.  Ein Beispiel finden Sie unter [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md).  
  
 *pParamIO*  
 Ein Zeiger der Variablen, die den Typ enthält **DBPARAMIO** \(Eingabe oder Ausgabe\) des angegebenen Parameters.  Er wird definiert, wie folgt:  
  
 `typedef DWORD DBPARAMIO;`  
  
 `enum DBPARAMIOENUM`  
  
 `{   DBPARAMIO_NOTPARAM   = 0,`  
  
 `DBPARAMIO_INPUT      = 0x1,`  
  
 `DBPARAMIO_OUTPUT     = 0x2`  
  
 `};`  
  
## Rückgabewert  
 **true** Gibt bei Erfolg oder **false** auf Fehler.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDynamicParameterAccessor\-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)