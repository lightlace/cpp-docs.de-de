---
title: NCCALCSIZE_PARAMS-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- NCCALCSIZE_PARAMS
dev_langs:
- C++
helpviewer_keywords:
- NCCALCSIZE_PARAMS structure
ms.assetid: 3424cd9f-806a-4089-82fb-414187589edf
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 88c25fd5e5862d5f0954ae853442c66eaf7320c8
ms.lasthandoff: 02/24/2017

---
# <a name="nccalcsizeparams-structure"></a>NCCALCSIZE_PARAMS-Struktur
Die `NCCALCSIZE_PARAMS` Struktur enthält Informationen, die eine Anwendung, während der Verarbeitung verwenden kann der `WM_NCCALCSIZE` Nachricht zum Berechnen der Größe, Position und gültige Inhalt des Clientbereichs eines Fensters.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct tagNCCALCSIZE_PARAMS {  
    RECT rgrc[3];  
    PWINDOWPOS lppos;  
} NCCALCSIZE_PARAMS;  
```  
  
#### <a name="parameters"></a>Parameter  
 *rgrc*  
 Gibt ein Array von Rechtecken. Die erste enthält die neuen Koordinaten eines Fensters, die verschoben oder geändert wurden. Die zweite enthält die Koordinaten des Fensters, bevor es verschoben oder geändert wurde. Das dritte enthält die Koordinaten des Clientbereichs eines Fensters, bevor es verschoben oder geändert wurde. Wenn das Fenster ein untergeordnetes Fenster ist, sind die Koordinaten relativ zum Clientbereich des übergeordneten Fensters. Wenn das Fenster der obersten Ebene ist, sind die Koordinaten relativ zum Bildschirm.  
  
 *lppos*  
 Verweist auf eine [WINDOWPOS](../../mfc/reference/windowpos-structure1.md) Struktur, die die Größe und Position Werte gemäß der Vorgang, verursacht das Fenster verschoben oder geändert werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** winuser.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)


