---
title: "CHAIN_PROPERTY_SET | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CHAIN_PROPERTY_SET"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHAIN_PROPERTY_SET-Makro"
ms.assetid: 2bcf6d7d-f4e5-480d-9140-1e32a0994c94
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CHAIN_PROPERTY_SET
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Makro verkettet Eigenschaftengruppen zusammen.  
  
## Syntax  
  
```  
  
CHAIN_PROPERTY_SET(  
ChainClass   
)  
  
```  
  
#### Parameter  
 *ChainClass*  
 \[in\] Der Name der Klasse, von Eigenschaften für zu verketten.  Dies ist eine Klasse, die im ATL\-Projekt\-Assistenten generiert wird, der bereits eine Zuordnung enthält \(z eine Sitzung, einen Befehl oder eine Datenquellenobjektklasse\).  
  
## Hinweise  
 Sie können einen Eigenschaftensatz von einer anderen Klasse zu der Klasse verketten, und greifen auf die Eigenschaften direkt von der Klasse zu.  
  
> [!CAUTION]
>  Verwenden Sie dieses Makro nur begrenzt.  Missbräuchliche Verwendung kann bewirken einen Consumer, die OLE DB\-Übereinstimmungstests zu belassen.  
  
## Anforderungen  
 **Header:** atldb.h  
  
## Siehe auch  
 [Makros für OLE DB\-Anbietervorlagen](../../data/oledb/macros-for-ole-db-provider-templates.md)