---
title: "R&#252;ckruffunktion f&#252;r CDC::SetAbortProc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Callback Function for CDC::SetAbortProc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Rückruffunktionen, für CDC::SetAbortProc"
ms.assetid: daa36d5d-15de-40fc-8d37-a865d06c4710
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# R&#252;ckruffunktion f&#252;r CDC::SetAbortProc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der Name *AbortFunc* ist ein Platzhalter für den von der Anwendung bereitgestellten Funktionsnamen.  
  
## Syntax  
  
```  
  
      BOOL CALLBACK EXPORT AbortFunc(   
   HDC hPr,   
   int code    
);  
```  
  
#### Parameter  
 *hPr*  
 Identifiziert den Gerätekontext.  
  
 `code`  
 Gibt an, ob ein Fehler aufgetreten ist.  Er ist 0, wenn kein Fehler aufgetreten ist.  Es ist **SP\_OUTOFDISK**, wenn der Druck \- Manager nur aus Speicherplatz ist und mehr Speicherplatz verfügbar ist, wenn die Anwendung wartet.  Wenn `code`**SP\_OUTOFDISK** ist, muss die Anwendung den Druckauftrag nicht abbrechen.  Wenn nicht, muss es auf den Druck \- Manager führen, indem die **PeekMessage** oder **GetMessage** Windows\-Funktion aufruft.  
  
## Rückgabewert  
 Der Rückgabewert der AbbruchHandlerfunktion ist ungleich 0 \(null\), wenn der Druckauftrag Fortfahren ist, und 0, wenn er abgebrochen wird.  
  
## Hinweise  
 Der tatsächliche Name exportiert werden muss, wie im Abschnitt Hinweise von [CDC::SetAbortProc](../Topic/CDC::SetAbortProc.md) beschrieben.  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::SetAbortProc](../Topic/CDC::SetAbortProc.md)