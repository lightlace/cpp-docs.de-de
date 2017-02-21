---
title: "CDynamicStringAccessor::GetString | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicStringAccessor.GetString"
  - "CDynamicStringAccessor::GetString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetString-Methode"
ms.assetid: 4af27f27-7589-49f5-93d8-6ef05c023c8a
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CDynamicStringAccessor::GetString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft die angegebenen Spaltendaten als Zeichenfolge ab.  
  
## Syntax  
  
```  
  
      BaseType* GetString(  
   DBORDINAL nColumn  
) const throw( );  
BaseType* GetString(  
   const CHAR* pColumnName  
) const throw( );  
BaseType* GetString(  
   const WCHAR* pColumnName  
) const throw( );  
```  
  
#### Parameter  
 `nColumn`  
 \[in\] Spaltennummer.  Spaltennummern beginnen mit 1.  Ein Wert von 0 werden die Lesezeichenspalte an, falls welche vorhanden.  
  
 `pColumnName`  
 \[in\] Ein Zeiger auf eine Zeichenfolge, die den Spaltennamen enthält.  
  
## Rückgabewert  
 Ein Zeiger auf den Zeichenfolgenwert abgerufen von der angegebenen Spalte.  Der Wert ist vom Typ ***BaseType***, das **CHAR**  oder **WCHAR**  stellen Sie je nachdem, ob \_UNICODE oder nicht definiert ist.  EINGABETASTE MACHT ungültig, wenn die angegebenen Spalte nicht gefunden wird.  
  
## Hinweise  
 Das zweite Überschreibungsformular akzeptiert den Spaltennamen als ANSI\-Zeichenfolge.  Das dritte Überschreibungsformular akzeptiert den Spaltennamen als Unicode\-Zeichenfolge.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDynamicStringAccessor\-Klasse](../../data/oledb/cdynamicstringaccessor-class.md)