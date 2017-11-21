---
title: MEASUREITEMSTRUCT-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: MEASUREITEMSTRUCT
dev_langs: C++
helpviewer_keywords: MEASUREITEMSTRUCT structure [MFC]
ms.assetid: d141ace4-47cb-46b5-a81c-ad2c5e5a8501
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ee54b10c4eddb272653615caa7ef7ba62f707622
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="measureitemstruct-structure"></a>MEASUREITEMSTRUCT-Struktur
Die `MEASUREITEMSTRUCT` Struktur informiert Windows über die Abmessungen eines Ownerdrawn-Steuerelement oder Menüelement-Elements.  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 `CtlType`  
 Enthält den Steuerelementtyp ". Folgende Werte sind für Steuerelementtypen gültig:  
  
- **ODT_COMBOBOX** Ownerdrawn-Kombinationsfeld  
  
- **Odt_combobox** Besitzer gezeichnetes Listenfeld  
  
- **ODT_MENU** Besitzer gezeichnetes Menü  
  
 `CtlID`  
 Enthält die Steuerelement-ID für ein Kombinationsfeld, Listenfeld oder Schaltfläche. Dieser Member wird nicht für ein Menü verwendet.  
  
 `itemID`  
 Die Menüelement ID für ein Menü oder die Listenfeldelement ID für ein variabler Höhe Kombinationsfeld oder Listenfeld enthält. Dieses Element ist nicht für eine feste Höhe Kombinationsfeld oder Listenfeld oder für eine Schaltfläche verwendet.  
  
 *itemWidth*  
 Gibt die Breite eines Menüelements. Der Besitzer des Menüelements Ownerdrawn-muss bei diesem Member ausfüllen, bevor sie aus der Nachricht zurückgibt.  
  
 *itemHeight*  
 Gibt die Höhe eines einzelnen Elements in einem Listenfeld oder ein Menü an. Vor der Rückgabe aus der Nachricht, die Besitzer des Kombinationsfelds Ownerdrawn-muss bei diesem Member im Listenfeld oder Menüelement ausfüllen. Die maximale Höhe des ein Listenfeldelement ist 255.  
  
 `itemData`  
 Für ein Kombinationsfeld oder Listenfeld enthält dieser Member den Wert, der dem Listenfeld von einer der folgenden Methoden übergeben wurde:  
  
- [CComboBox:: AddString](../../mfc/reference/ccombobox-class.md#addstring)  
  
- [CComboBox::InsertString](../../mfc/reference/ccombobox-class.md#insertstring)  
  
- [CListBox::AddString](../../mfc/reference/clistbox-class.md#addstring)  
  
- [CListBox::InsertString](../../mfc/reference/clistbox-class.md#insertstring)  
  
 Für ein Menü enthält dieser Member den Wert, der dem Menü durch eine der folgenden Methoden übergeben wurde:  
  
- [CMenu::AppendMenu](../../mfc/reference/cmenu-class.md#appendmenu)  
  
- [CMenu::InsertMenu](../../mfc/reference/cmenu-class.md#insertmenu)  
  
- [CMenu::ModifyMenu](../../mfc/reference/cmenu-class.md#modifymenu)  
  
 Dies ermöglicht Windows Benutzerinteraktion mit dem Steuerelement ordnungsgemäß verarbeiten. Fehler beim Ausfüllen der entsprechenden Elemente in der `MEASUREITEMSTRUCT` Struktur führt dazu, dass falsche Vorgang des Steuerelements.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** winuser.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem)

