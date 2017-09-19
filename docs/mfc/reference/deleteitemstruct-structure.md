---
title: DELETEITEMSTRUCT-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DELETEITEMSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- DELETEITEMSTRUCT structure
ms.assetid: 48d3998c-f4a8-402a-bf90-df3770a78685
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: f5936cbb863cf8ace851609cb1dc8352e21f9456
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="deleteitemstruct-structure"></a>DELETEITEMSTRUCT-Struktur
Die `DELETEITEMSTRUCT` Struktur beschreibt ein gelöschtes Ownerdrawn-Listenfeld oder Kombinationsfeld Element.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct tagDELETEITEMSTRUCT { /* ditms */  
    UINT CtlType;  
    UINT CtlID;  
    UINT itemID;  
    HWND hwndItem;  
    UINT itemData;  
} DELETEITEMSTRUCT;  
```  
  
#### <a name="parameters"></a>Parameter  
 `CtlType`  
 Gibt an, **ODT_LISTBOX** (ein Ownerdrawn Listenfeld) oder **ODT_COMBOBOX** (ein Ownerdrawn-Kombinationsfeld).  
  
 `CtlID`  
 Gibt den Bezeichner der im Listenfeld oder Kombinationsfeld.  
  
 `itemID`  
 Gibt den Index des Elements im Listenfeld oder Kombinationsfeld entfernt an.  
  
 `hwndItem`  
 Bezeichnet das Steuerelement.  
  
 `itemData`  
 Gibt anwendungsspezifische Daten für das Element an. Dieser Wert wird übergeben, um das Steuerelement in der **lParam** -Parameter der Nachricht, die Sie im Listenfeld oder Kombinationsfeld das Element hinzufügt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn ein Element entfernt wird, aus dem Listenfeld oder Kombinationsfeld oder das Listenfeld oder Kombinationsfeld zerstört wird, sendet Windows die `WM_DELETEITEM` Nachricht an den Besitzer für die einzelnen Elemente. Die **lParam** -Parameter der Nachricht enthält einen Zeiger auf diese Struktur.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem)



