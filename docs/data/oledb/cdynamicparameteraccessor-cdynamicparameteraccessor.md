---
title: "CDynamicParameterAccessor::CDynamicParameterAccessor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicParameterAccessor::CDynamicParameterAccessor"
  - "CDynamicParameterAccessor.CDynamicParameterAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDynamicParameterAccessor-Klasse, Konstruktor"
  - "CDynamicParameterAccessor-Methode"
ms.assetid: a1cce5e4-dfb9-43a2-bfb8-0435c653674a
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicParameterAccessor::CDynamicParameterAccessor
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der \-Konstruktor.  
  
## Syntax  
  
```  
  
      typedef CDynamicParameterAccessor _ParamClass;  
CDynamicParameterAccessor(   
   DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,   
   DBLENGTH nBlobSize = 8000 )   
   : CDynamicAccessor( eBlobHandling, nBlobSize )  
```  
  
#### Parameter  
 `eBlobHandling`  
 Gibt an, wie die Verarbeitungsmöglichkeiten behandelt werden sollen.  Der Standardwert ist **DBBLOBHANDLING\_DEFAULT**.  [CDynamicAccessor::SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md) finden Sie eine Beschreibung der **DBBLOBHANDLINGENUM**\-Werte.  
  
 `nBlobSize`  
 Die maximale BLOBgröße in Bytes; Spaltendaten über diesen Wert werden als BLOB behandelt.  Der Standardwert ist 8,000.  Ausführliche Informationen finden Sie unter [CDynamicAccessor::SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md).  
  
## Hinweise  
 Siehe den Konstruktor [CDynamicAccessor::CDynamicAccessor](../../data/oledb/cdynamicaccessor-cdynamicaccessor.md) weitere Informationen zu BLOBbehandlung.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDynamicParameterAccessor\-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)