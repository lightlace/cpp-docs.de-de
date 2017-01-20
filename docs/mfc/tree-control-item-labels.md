---
title: "Elementbezeichnungen in Struktursteuerelementen"
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
  - "CTreeCtrl-Klasse, Elementbezeichnungen"
  - "Elementbezeichnungen"
  - "Elementbezeichnungen, Struktursteuerelemente"
  - "Bezeichnungen, CTreeCtrl-Elemente"
  - "Struktursteuerelemente, Elementbezeichnungen"
ms.assetid: fe834107-1a25-4280-aced-774c11565805
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Elementbezeichnungen in Struktursteuerelementen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie geben in der Regel den Text der Beschriftung eines Elements an, wenn Sie das Element dem Strukturansicht\-Steuerelement \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) hinzufügen.  Die `InsertItem`\-Memberfunktion kann [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) eine Struktur, die die Eigenschaften des Elements definiert, u übergeben eine Zeichenfolge, die den Text der Beschriftung enthält.  `InsertItem` verfügt über mehrere Überladungen, die mit verschiedenen Kombinationen von Parametern aufgerufen werden können.  
  
 Eine Strukturansicht belegt für das Speichern jedes Elements; Speicher Text der Elementbezeichnungen akzeptiert einen erheblichen Teil dieses Speichers auf.  Wenn die Anwendung eine Kopie der Zeichenfolgen in der Strukturansicht enthält, können Sie die Speicheranforderungen des Steuerelements verringern, indem Sie dem **LPSTR\_TEXTCALLBACK**\-Wert im **pszText**\-Member von `TV_ITEM` oder `lpszItem` den Parameter angeben, anstatt, tatsächliche Zeichenfolgen dem Strukturansicht\-Steuerelement zu übergeben.  Mit **LPSTR\_TEXTCALLBACK** Ursachen das Struktursteuerelement, um den Text der Beschriftung eines Elements aus der Anwendung abrufen, wenn das Element neu gezeichnet werden muss.  Um den Text abzurufen, sendet das Tree\-Steuerelement eine [TVN\_GETDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773518), die die Benachrichtigung Adresse einer [NMTVDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773418)\-Struktur enthält.  Sie müssen reagieren, indem Sie die entsprechenden Member der enthaltenden Struktur festlegen.  
  
 Eine Strukturansicht wird der Arbeitsspeicher, der vom Heap des Prozesses zugeordnet wird, der das Struktursteuerelement erstellt.  Die maximale Anzahl der Elemente in einem Strukturansicht basiert auf den Arbeitsspeicher, der im Heap verfügbar ist.  Jedes Element verwendet 64 Bytes.  
  
## Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)