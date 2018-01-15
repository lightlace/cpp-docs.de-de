---
title: DELETEITEMSTRUCT-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DELETEITEMSTRUCT
dev_langs: C++
helpviewer_keywords: DELETEITEMSTRUCT structure [MFC]
ms.assetid: 48d3998c-f4a8-402a-bf90-df3770a78685
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 93be7b23ae713caea5fa64e437fe792c550589f1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="deleteitemstruct-structure"></a>DELETEITEMSTRUCT-Struktur
Die `DELETEITEMSTRUCT` Struktur beschreibt ein gelöschtes Besitzer gezeichnetes Listenfeld oder Kombinationsfeld Element.  
  
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
 Gibt an, **odt_combobox** (ein Besitzer gezeichnetes Listenfeld) oder **ODT_COMBOBOX** (ein Ownerdrawn-Kombinationsfeld).  
  
 `CtlID`  
 Gibt den Bezeichner der im Listenfeld oder Kombinationsfeld.  
  
 `itemID`  
 Gibt den Index des Elements in das Listenfeld oder Kombinationsfeld, die entfernt an.  
  
 `hwndItem`  
 Bezeichnet das Steuerelement.  
  
 `itemData`  
 Gibt anwendungsspezifische Daten für das Element an. Dieser Wert wird übergeben, auf das Steuerelement in der **lParam** -Parameter der Nachricht, die das Element im Listenfeld oder Kombinationsfeld hinzufügt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn ein Element entfernt wird, aus dem Listenfeld oder Kombinationsfeld, oder wenn das Listenfeld oder Kombinationsfeld zerstört wird, sendet Windows die `WM_DELETEITEM` Nachricht an den Besitzer jedes gelöschtes Element. Die **lParam** -Parameter der Nachricht enthält einen Zeiger auf diese Struktur.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem)


