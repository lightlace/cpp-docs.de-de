---
title: "CDynamicStringAccessor::SetString"
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
  - "CDynamicStringAccessor::SetString"
  - "CDynamicStringAccessor.SetString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetString-Methode"
ms.assetid: 94846d8b-4c1b-47fe-acdc-1752981cee25
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicStringAccessor::SetString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt die angegebenen Spaltendaten als Zeichenfolge fest.  
  
## Syntax  
  
```  
HRESULT SetString(  
   DBORDINAL nColumn,  
   BaseType* data  
) throw( );  
HRESULT SetString(  
   const CHAR* pColumnName,  
   BaseType* data  
) throw( );  
HRESULT SetString(  
   const WCHAR* pColumnName,  
   BaseType* data  
) throw( );  
```  
  
#### Parameter  
 `nColumn`  
 \[in\] Spaltennummer.  Spaltennummern beginnen mit 1.  Der spezielle Wert 0 verweist die Lesezeichenspalte an, falls welche vorhanden.  
  
 `pColumnName`  
 \[in\] Ein Zeiger auf eine Zeichenfolge, die den Spaltennamen enthält.  
  
 `data`  
 \[in\] Ein Zeiger auf den geschrieben werden der angegebenen Spalte Zeichenfolgendaten.  
  
## Rückgabewert  
 Ein Zeiger auf das dem Zeichenfolgenwert, der der angegebenen Spalte festzulegen.  Der Wert ist vom Typ `BaseType`, das `CHAR`  oder `WCHAR`  stellen Sie je nachdem, ob `_UNICODE`  oder nicht definiert ist.  
  
## Hinweise  
 Das zweite Überschreibungsformular akzeptiert den Spaltennamen, während eine ANSI\-Zeichenfolge und das dritte Überschreibungsformular den Spaltennamen als Unicode\-Zeichenfolge akzeptiert.  
  
 Wenn `_SECURE_ATL` definiert wurde, um einen Wert ungleich 0 \(null\) haben, wird ein Ablaufassertionsfehler generiert, wenn die Eingabe `data` Zeichenfolge größer als die maximal zulässige Länge der referenzierten Datenspalte ist.  Andernfalls wird die Eingabezeichenfolge verkürzt, wenn es länger als die maximal zulässige Länge ist.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDynamicStringAccessor\-Klasse](../../data/oledb/cdynamicstringaccessor-class.md)