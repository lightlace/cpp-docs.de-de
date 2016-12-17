---
title: "R&#252;ckruffunktion f&#252;r CDC::EnumObjects"
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
  - "Callback Function for CDC::EnumObjects"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Rückruffunktionen, für CDC::EnumObjects"
ms.assetid: 380088b1-88a5-4fb4-bbb5-dd9e8386572b
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# R&#252;ckruffunktion f&#252;r CDC::EnumObjects
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der *ObjectFunc\-* Name ist ein Platzhalter für den von der Anwendung bereitgestellten Funktionsnamen.  
  
## Syntax  
  
```  
  
      int CALLBACK EXPORT ObjectFunc(   
   LPSTR lpszLogObject,   
   LPSTR* lpData    
);  
```  
  
#### Parameter  
 *lpszLogObject*  
 Punkte zu einer [LOGPEN](../../mfc/reference/logpen-structure.md) oder [LOGBRUSH](../../mfc/reference/logbrush-structure.md) Datenstruktur, die Informationen über die logische Attribute des Objekts enthält.  
  
 `lpData`  
 Punkte zu den von der Anwendung bereitgestellten Daten übergeben der `EnumObjects`\-Funktion.  
  
## Rückgabewert  
 Die Rückruffunktion gibt `int` zurück.  Der Wert dieser Rückgabe ist benutzerdefiniert.  Wenn die Rückruffunktion 0 zurückgibt, beendet `EnumObjects`\-Enumeration früh.  
  
## Hinweise  
 Der tatsächliche Name muss exportiert werden.  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::EnumObjects](../Topic/CDC::EnumObjects.md)