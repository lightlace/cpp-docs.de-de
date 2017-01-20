---
title: "DELETEITEMSTRUCT-Struktur"
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
  - "DELETEITEMSTRUCT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DELETEITEMSTRUCT-Struktur"
ms.assetid: 48d3998c-f4a8-402a-bf90-df3770a78685
caps.latest.revision: 13
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# DELETEITEMSTRUCT-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `DELETEITEMSTRUCT`\-Struktur beschreibt ein gelöschtes Ownerdrawnlistenfeld\- oder \-Kombinationsfeldelement.  
  
## Syntax  
  
```  
  
      typedef struct tagDELETEITEMSTRUCT { /* ditms */  
    UINT CtlType;  
    UINT CtlID;  
    UINT itemID;  
    HWND hwndItem;  
    UINT itemData;  
} DELETEITEMSTRUCT;  
```  
  
#### Parameter  
 `CtlType`  
 Gibt **ODT\_LISTBOX** \(einem Ownerdrawn Listenfeld\) oder **ODT\_COMBOBOX** an \(ein Ownerdrawnkombinationsfeld\).  
  
 `CtlID`  
 Gibt den Bezeichner des Listenfelds oder Kombinationsfeld an.  
  
 `itemID`  
 Gibt Index des Elements in Listenfeldern oder im Kombinationsfeld an, die entfernt wird.  
  
 `hwndItem`  
 Bezeichnet das Steuerelement.  
  
 `itemData`  
 Gibt anwendungsdefinierten Daten für das Element angegeben.  Dieser Wert wird dem Steuerelement im Parameter **lParam** der Meldung übergeben, die dem Element dem Listenfeld oder dem Kombinationsfeld.  
  
## Hinweise  
 Wenn ein Element aus dem Listenfeld aus einem Kombinationsfeld oder entfernt wird, oder wenn das Listenfeld oder das Kombinationsfeld zerstört, Windows `WM_DELETEITEM` sendet die Meldung an den Besitzer für gelöschte jedes Element.  Der Parameter **lParam** der Meldung enthält einen Zeiger auf diese Struktur.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnDeleteItem](../Topic/CWnd::OnDeleteItem.md)