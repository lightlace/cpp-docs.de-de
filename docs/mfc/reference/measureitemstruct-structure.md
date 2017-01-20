---
title: "MEASUREITEMSTRUCT-Struktur"
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
  - "MEASUREITEMSTRUCT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MEASUREITEMSTRUCT-Struktur"
ms.assetid: d141ace4-47cb-46b5-a81c-ad2c5e5a8501
caps.latest.revision: 11
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# MEASUREITEMSTRUCT-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Struktur `MEASUREITEMSTRUCT` informiert Windows über die Abmessungen eines Ownerdrawnsteuerelements oder \-Menüelements.  
  
## Syntax  
  
```  
  
      typedef struct tagMEASUREITEMSTRUCT {  
   UINT CtlType;  
   UINT CtlID;  
   UINT itemID;  
   UINT itemWidth;  
   UINT itemHeight;  
   DWORD itemData  
} MEASUREITEMSTRUCT;  
```  
  
#### Parameter  
 `CtlType`  
 Enthält den Steuerelementtyp.  Die Werte für Steuerelementtypen sind, wie folgt:  
  
-   **ODT\_COMBOBOX** Ownerdrawnkombinationsfeld  
  
-   Ownerdrawn Listenfeld **ODT\_LISTBOX**  
  
-   **ODT\_MENU** Ownerdrawnmenü  
  
 `CtlID`  
 Enthält die Steuerelement\-ID für ein Kombinationsfeld, ein Listenfeld oder eine Schaltfläche.  Dieser Member wird nicht für ein Menü verwendet.  
  
 `itemID`  
 Enthält die ID für Menüelement ein Menü oder die Liste\-FeldElement ID für ein VariableHöhen\-Kombinationsfeld oder \-Listenfeld.  Dieser Member wird nicht für ein KorrigierteHöhen\-Kombinationsfeld oder \-Listenfeld oder für eine Schaltfläche verwendet.  
  
 *itemWidth*  
 Gibt die Breite eines Menüelements an.  Der Besitzer des Ownerdrawnmenüelements muss diesen Member ausfüllen, bevor von der Meldung zurückgegeben wird.  
  
 *itemHeight*  
 Gibt die Höhe eines einzelnen Elements in einem Listenfeld oder einem Menü an.  Bevor sie von der Meldung zurückgegeben wird, muss der Besitzer des Ownerdrawnkombinationsfelds, \-Listenfelds oder \-Menüelements diesen Member ergänzen.  Die maximale Höhe eines Listenfeldelements ist 255.  
  
 `itemData`  
 Für ein Kombinations\- oder Listenfeld enthält dieser Member den Wert, der dem Listenfeld durch eine der folgenden Zeichenfolgen übergeben werden:  
  
-   [CComboBox::AddString](../Topic/CComboBox::AddString.md)  
  
-   [CComboBox::InsertString](../Topic/CComboBox::InsertString.md)  
  
-   [CListBox::AddString](../Topic/CListBox::AddString.md)  
  
-   [CListBox::InsertString](../Topic/CListBox::InsertString.md)  
  
 Ein Menü enthält dieser Member den Wert, der im Menü durch eine der folgenden Zeichenfolgen übergeben werden:  
  
-   [CMenu::AppendMenu](../Topic/CMenu::AppendMenu.md)  
  
-   [CMenu::InsertMenu](../Topic/CMenu::InsertMenu.md)  
  
-   [CMenu::ModifyMenu](../Topic/CMenu::ModifyMenu.md)  
  
 Dies ermöglicht Windows zur Prozessbenutzerinteraktion mit dem Steuerelement ordnungsgemäß.  Fehler, die richtigen Member `MEASUREITEMSTRUCT` in der Struktur zu ergänzen verursacht ungültiges Vorgang des Steuerelements.  
  
## Anforderungen  
 **Header:** winuser.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnMeasureItem](../Topic/CWnd::OnMeasureItem.md)