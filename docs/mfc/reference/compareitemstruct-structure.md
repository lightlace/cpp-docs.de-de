---
title: "COMPAREITEMSTRUCT-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "COMPAREITEMSTRUCT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COMPAREITEMSTRUCT-Struktur"
ms.assetid: 4b7131a5-5c7d-4e98-aac7-e85650262b52
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# COMPAREITEMSTRUCT-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `COMPAREITEMSTRUCT`\-Struktur stellt die Bezeichner und die von der Anwendung bereitgestellten Daten für zwei Elemente in einer sortierten, Ownerdrawn Listenfeld oder einem Kombinationsfeld.  
  
## Syntax  
  
```  
  
      typedef struct tagCOMPAREITEMSTRUCT {  
    UINT   CtlType;  
    UINT   CtlID;  
    HWND   hwndItem;  
    UINT   itemID1;  
    DWORD  itemData1;  
    UINT   itemID2;  
    DWORD  itemData2;  
} COMPAREITEMSTRUCT;  
```  
  
#### Parameter  
 `CtlType`  
 **ODT\_LISTBOX** \(gleich bedeutend einem Ownerdrawn Listenfeld angibt\) oder **ODT\_COMBOBOX** \(das ein Ownerdrawnkombinationsfeld angibt\).  
  
 `CtlID`  
 Die Steuerelement\-ID für das Listenfeld oder dem Kombinationsfeld.  
  
 `hwndItem`  
 Das Fensterhandle des Steuerelements.  
  
 *itemID1*  
 Der Index des ersten Elements im Listenfeld oder im Kombinationsfeld, die verglichen wird.  
  
 *itemData1*  
 Von der Anwendung bereitgestellte Daten für den ersten Punkt, der verglichen wird.  Dieser Wert wurde in den Aufruf übergeben, der das Element dem Kombinationsfeld oder dem Listenfeld hinzugefügt.  
  
 *itemID2*  
 Index des zweiten Elements im Listenfeld oder im Kombinationsfeld, die verglichen wird.  
  
 *itemData2*  
 Von der Anwendung bereitgestellte Daten für das zweite Element, das verglichen wird.  Dieser Wert wurde in den Aufruf übergeben, der das Element dem Kombinationsfeld oder dem Listenfeld hinzugefügt.  
  
## Hinweise  
 Wenn eine Anwendung ein neues Element einem Ownerdrawn Listenfeld oder \-Kombinationsfeld hinzufügen, die mit dem **CBS\_SORT** oder **LBS\_SORT** Stil erstellt werden, sendet Windows den Besitzer eine Meldung. `WM_COMPAREITEM` Der `lParam`\-Parameter der Meldung enthält einen langen Zeiger an eine `COMPAREITEMSTRUCT`\-Struktur.  Beim Empfang der Nachricht, vergleicht der Besitzer die beiden Elemente und gibt einen Wert zurück, das Element vor dem anderen sortiert.  
  
## Anforderungen  
 **Header:** winuser.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCompareItem](../Topic/CWnd::OnCompareItem.md)