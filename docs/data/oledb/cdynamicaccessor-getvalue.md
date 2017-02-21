---
title: "CDynamicAccessor::GetValue | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetValue"
  - "CDynamicAccessor::GetValue<ctype>"
  - "ATL.CDynamicAccessor.GetValue<ctype>"
  - "CDynamicAccessor.GetValue"
  - "CDynamicAccessor::GetValue"
  - "ATL.CDynamicAccessor.GetValue"
  - "ATL::CDynamicAccessor::GetValue"
  - "ATL::CDynamicAccessor::GetValue<ctype>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetValue-Methode"
ms.assetid: 553f44af-68bc-4cb6-8774-e0940003fa90
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicAccessor::GetValue
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ruft die Daten für eine bestimmte Spalte ab.  
  
## Syntax  
  
```  
  
      void* GetValue(   
   DBORDINAL nColumn    
) const throw( );  
void* GetValue(  
   const CHAR* pColumnName   
) const throw( );  
void* GetValue(  
   const WCHAR* pColumnName   
) const throw( );  
template < class ctype >  
bool GetValue(  
   DBORDINAL nColumn,  
   ctype* pData   
) const throw( );  
template < class ctype >  
bool GetValue(  
   const CHAR* pColumnName,  
   ctype* pData   
) const throw( );  
template < class ctype >  
bool GetValue(  
   const WCHAR* pColumnName,  
   ctype* pData   
) const throw( );  
```  
  
#### Parameter  
 `ctype`  
 \[in\] auf Vorlagen basierenden Parameter A, der jeden Datentyp außer Zeichenfolgentypen \(**CHAR\***, **WCHAR\***\) behandelt, die besondere Behandlung erfordern.  `GetValue` verwendet den entsprechenden Datentyp auf Grundlage, was Sie hier angeben.  
  
 `nColumn`  
 \[in\] Spaltennummer.  Spaltennummern beginnen mit 1.  Ein Wert von 0 werden die Lesezeichenspalte an, falls welche vorhanden.  
  
 `pColumnName`  
 \[in\] der Spaltenname.  
  
 `pData`  
 \[out\] der Zeiger die Inhalt der angegebenen Spalte.  
  
## Rückgabewert  
 Wenn Sie Zeichenfolgendaten übergeben möchten, verwenden Sie die nicht auf Vorlagen basierenden Versionen von `GetValue`.  Die nicht auf Vorlagen basierenden Versionen dieser Methode geben **void\*** zurück, die auf dem Teil des Puffers zeigt, der die angegebenen Daten anderer Spalten enthält.  Gibt **NULL** zurück, wenn die Spalte nicht gefunden wird.  
  
 Für alle anderen Datentypen ist es einfacher, die auf Vorlagen basierenden Versionen von `GetValue`.  Die Vorlage gebildeten Versionen geben **true** bei Erfolg oder **false** auf Fehler zurück.  
  
## Hinweise  
 Verwenden Sie die nicht auf Vorlagen basierenden Versionen, um Spalten zurückzugeben, die Zeichenfolgen und die auf Vorlagen basierenden Versionen für Spalten enthalten, die andere Datentypen enthalten.  
  
 Im Debugmodus wird eine Assertion ab, wenn die Größe von `pData` zur Größe der Spalte ungleich ist, auf die sie zeigt.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDynamicAccessor\-Klasse](../../data/oledb/cdynamicaccessor-class.md)