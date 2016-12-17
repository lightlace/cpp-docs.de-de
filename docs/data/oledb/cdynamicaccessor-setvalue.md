---
title: "CDynamicAccessor::SetValue"
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
  - "ATL.CDynamicAccessor.SetValue"
  - "ATL::CDynamicAccessor::SetValue"
  - "ATL::CDynamicAccessor::SetValue<ctype>"
  - "CDynamicAccessor.SetValue"
  - "ATL.CDynamicAccessor.SetValue<ctype>"
  - "CDynamicAccessor::SetValue"
  - "CDynamicAccessor::SetValue<ctype>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetValue-Methode"
ms.assetid: ecc18850-96e5-4845-abe5-ab34ad467238
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicAccessor::SetValue
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Speichert Daten auf eine bestimmte Spalte.  
  
## Syntax  
  
```  
  
      template < class ctype >    
bool SetValue(   
   DBORDINAL nColumn,   
   const ctype& data    
) throw( );  
template < class ctype >    
bool SetValue(   
   const CHAR * pColumnName,   
   const ctype& data    
) throw( );  
template <class ctype>   
bool SetValue(  
   const WCHAR *pColumnName,  
   const ctype& data   
) throw( );  
```  
  
#### Parameter  
 `ctype`  
 \[in\] auf Vorlagen basierenden Parameter A, der jeden Datentyp außer Zeichenfolgentypen \(**CHAR\***, **WCHAR\***\) behandelt, die besondere Behandlung erfordern.  `GetValue` verwendet den entsprechenden Datentyp auf Grundlage, was Sie hier angeben.  
  
 `pColumnName`  
 \[in\] Ein Zeiger auf eine Zeichenfolge, die den Spaltennamen enthält.  
  
 `data`  
 \[in\] der Zeiger auf den Speicher, der die Daten enthält.  
  
 `nColumn`  
 \[in\] Spaltennummer.  Spaltennummern beginnen mit 1.  Ein Wert von 0 werden die Lesezeichenspalte an, falls welche vorhanden.  
  
## Rückgabewert  
 Wenn Sie Zeichenfolgendaten festlegen möchten, verwenden Sie die nicht auf Vorlagen basierenden Versionen von `GetValue`.  Die nicht auf Vorlagen basierenden Versionen dieser Methode geben **void\*** zurück, die auf dem Teil des Puffers zeigt, der die angegebenen Daten anderer Spalten enthält.  Gibt **NULL** zurück, wenn die Spalte nicht gefunden wird.  
  
 Für alle anderen Datentypen ist es einfacher, die auf Vorlagen basierenden Versionen von `GetValue`.  Die Vorlage gebildeten Versionen geben **true** bei Erfolg oder **false** auf Fehler zurück.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDynamicAccessor\-Klasse](../../data/oledb/cdynamicaccessor-class.md)