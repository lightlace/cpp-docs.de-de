---
title: COMPAREITEMSTRUCT-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COMPAREITEMSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- COMPAREITEMSTRUCT structure [MFC]
ms.assetid: 4b7131a5-5c7d-4e98-aac7-e85650262b52
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a94d39c6b6c256444cd2850f7e55a7e4b87f6d7a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33368630"
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

