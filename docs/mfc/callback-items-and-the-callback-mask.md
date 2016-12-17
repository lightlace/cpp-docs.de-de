---
title: "R&#252;ckrufelemente und die R&#252;ckrufmaske"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Rückrufelemente in der CListCtrl-Klasse"
  - "CListCtrl-Klasse, Rückrufelemente und Rückrufmaske"
ms.assetid: 67c1f76f-6144-453e-9376-6712f89430ae
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# R&#252;ckrufelemente und die R&#252;ckrufmaske
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Für jedes seiner Elemente, speichert ein Listenansicht\-Steuerelement in der Regel den Bezeichnungstext, den Bildlistenindex der Symbole des Elements und einem Satz von Bitflags für den Zustand des Elements.  Sie können einzelne Elemente als Rückrufelemente definieren, die hilfreich sind, wenn die Anwendung bereits einige der Informationen für ein Element gespeichert werden.  
  
 Sie definieren ein Element wie ein Rückrufelement, indem Sie entsprechenden Werte für die `pszText` und `iImage` müssen Member der **LV\_ITEM** \-Struktur angeben \(siehe [CListCtrl::GetItem](../Topic/CListCtrl::GetItem.md)\).  Wenn die Verwendung des Elements oder den Text des Unterelements beibehält, den **LPSTR\_TEXTCALLBACK**\-Wert für den `pszText`\-Member.  Wenn die Anwendung das Symbol für das Element nachverfolgt, den **I\_IMAGECALLBACK**\-Wert für den `iImage`\-Member.  
  
 Zusätzlich zum Definieren von Rückrufelementen, können Sie die Rückrufmaske des Steuerelements ändern.  Diese Maske ist ein Satz von Bitflags, die den Elementzuständen angeben, für die die Anwendung, anstatt das Steuerelement, Speicher die aktuellen Daten.  Die Rückrufmaske gilt auf die Elemente aller Steuerelements, anders als die Rückrufelementbezeichnung zu, die auf ein bestimmtes Element gilt.  Die Rückrufmaske ist standardmäßig null und heißt dass die Kontrollspuren alle Zustände.  Um dieses Standardverhalten zu ändern, initialisieren Sie die Maske zu jeder Kombination der folgenden Werte:  
  
-   `LVIS_CUT` wird das Element für einen Ausschneide\- und Einfügevorgang markiert.  
  
-   `LVIS_DROPHILITED` das Element wird als Drag & Drop\-Ziel hervorgehoben.  
  
-   `LVIS_FOCUSED` \- Element besitzt den Fokus.  
  
-   `LVIS_SELECTED` das Element ist ausgewählt.  
  
-   **LVIS\_OVERLAYMASK** speichert die Anwendung den Bildlistenindex des aktuellen Overlaybilds für jedes Element.  
  
-   **LVIS\_STATEIMAGEMASK** speichert die Anwendung den Bildlistenindex des Bilds des aktuellen Zustands für jedes Element.  
  
 Weitere Informationen zum Abrufen und Festlegen dieser Maske, finden Sie unter [CListCtrl::GetCallbackMask](../Topic/CListCtrl::GetCallbackMask.md) und [CListCtrl::SetCallbackMask](../Topic/CListCtrl::SetCallbackMask.md).  
  
## Siehe auch  
 [Verwenden von CListCtrl](../mfc/using-clistctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)