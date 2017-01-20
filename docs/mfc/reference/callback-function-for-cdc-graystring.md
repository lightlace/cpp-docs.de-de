---
title: "R&#252;ckruffunktion f&#252;r CDC::GrayString"
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
  - "Callback Function for CDC::GrayString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Rückruffunktionen, für CDC::GrayString"
ms.assetid: 5217e183-df48-426b-931b-6245022ca36f
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# R&#252;ckruffunktion f&#252;r CDC::GrayString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

*OutputFunc* ist ein Platzhalter für den von der Anwendung bereitgestellten Rückruffunktionsnamen.  
  
## Syntax  
  
```  
  
      BOOL CALLBACK EXPORT OutputFunc(   
   HDC hDC,   
   LPARAM lpData,   
   int nCount    
);  
```  
  
#### Parameter  
 `hDC`  
 Bezeichnet einen Speichergerätekontext mit einer Bitmap mindestens der Breite und Höhe, die von `nWidth` und `nHeight` in `GrayString` angegeben werden.  
  
 `lpData`  
 Punkte der zu zeichnende Zeichenfolge.  
  
 `nCount`  
 Gibt die Anzahl von Zeichen an, die ausgegeben.  
  
## Rückgabewert  
 Der Rückgabewert der Rückruffunktion muss **TRUE** sein, z des Erfolgs festlegen; Andernfalls befindet es **FALSE**.  
  
## Hinweise  
 Die Rückruffunktion \(*OutputFunc*\) muss ein Bild im Verhältnis zu den Koordinaten \(0,0\) positionieren anstatt \(*x*, *y\)*.  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GrayString](../Topic/CDC::GrayString.md)