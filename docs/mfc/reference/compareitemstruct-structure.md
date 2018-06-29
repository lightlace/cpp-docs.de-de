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
ms.openlocfilehash: 5a54b4f4749e7865d793559a9cb5f475c1d57898
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2018
ms.locfileid: "37078257"
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
 *CtlType*  
 **Odt_combobox** (dem gibt einen Besitzer gezeichnetes Listenfeld) oder **ODT_COMBOBOX** (dem gibt ein Ownerdrawn-Kombinationsfeld an).  
  
 *CtlID*  
 Die Steuerelement-ID für das Listenfeld oder Kombinationsfeld.  
  
 *hwndItem*  
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
 Bei jedem eine Anwendung fügt ein neues Element auf ein vom Besitzer gezeichnetes Listenfeld oder Kombinationsfeld erstellt, mit der **CBS_SORT** oder **LBS_SORT** Stil, sendet Windows dem Besitzer eine Nachricht WM_COMPAREITEM. Die *lParam* -Parameter der Nachricht enthält einen long-Zeiger auf eine `COMPAREITEMSTRUCT` Struktur. Nach dem Empfang der Nachrichteninhalts wird der Besitzer vergleicht die beiden Elemente und gibt einen Wert, der angibt, welches Element zuerst sortiert zurück.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** winuser.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem)

