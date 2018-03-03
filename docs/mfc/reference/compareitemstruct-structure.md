---
title: COMPAREITEMSTRUCT-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- COMPAREITEMSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- COMPAREITEMSTRUCT structure [MFC]
ms.assetid: 4b7131a5-5c7d-4e98-aac7-e85650262b52
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7903e51a83533c8f2458c4400c64717021a1ccb8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compareitemstruct-structure"></a>COMPAREITEMSTRUCT-Struktur
Die `COMPAREITEMSTRUCT` Struktur bereitstellt, die Bezeichner und die Anwendung bereitgestellte Daten für zwei Elemente in einer sortierten, Besitzer gezeichnetes Listenfeld oder Kombinationsfeld.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct tagCOMPAREITEMSTRUCT {  
    UINT CtlType;  
    UINT CtlID;  
    HWND hwndItem;  
    UINT itemID1;  
    DWORD itemData1;  
    UINT itemID2;  
    DWORD itemData2;  
} COMPAREITEMSTRUCT;  
```  
  
#### <a name="parameters"></a>Parameter  
 `CtlType`  
 **Odt_combobox** (dem gibt einen Besitzer gezeichnetes Listenfeld) oder **ODT_COMBOBOX** (dem gibt ein Ownerdrawn-Kombinationsfeld an).  
  
 `CtlID`  
 Die Steuerelement-ID für das Listenfeld oder Kombinationsfeld.  
  
 `hwndItem`  
 Das Fensterhandle des Steuerelements.  
  
 *itemID1*  
 Der Index des ersten Elements in das Listenfeld oder Kombinationsfeld verglichen wird.  
  
 *itemData1*  
 Von der Anwendung bereitgestellten Daten für das erste Element verglichen wird. Dieser Wert wurde im Aufruf übergeben, die das Element im Kombinationsfeld oder Liste hinzugefügt.  
  
 *itemID2*  
 Der Index des zweiten Elements in das Listenfeld oder Kombinationsfeld verglichen wird.  
  
 *itemData2*  
 Von der Anwendung bereitgestellten Daten für das zweite Element verglichen wird. Dieser Wert wurde im Aufruf übergeben, die das Element im Kombinationsfeld oder Liste hinzugefügt.  
  
## <a name="remarks"></a>Hinweise  
 Bei jedem eine Anwendung fügt ein neues Element auf ein vom Besitzer gezeichnetes Listenfeld oder Kombinationsfeld erstellt, mit der **CBS_SORT** oder **LBS_SORT** Stil, sendet Windows den Besitzer einer `WM_COMPAREITEM` Nachricht. Die `lParam` -Parameter der Nachricht enthält einen long-Zeiger auf eine `COMPAREITEMSTRUCT` Struktur. Nach dem Empfang der Nachrichteninhalts wird der Besitzer vergleicht die beiden Elemente und gibt einen Wert, der angibt, welches Element zuerst sortiert zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** winuser.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem)

