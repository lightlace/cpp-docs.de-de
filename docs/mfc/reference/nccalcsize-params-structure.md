---
title: NCCALCSIZE_PARAMS-Struktur | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- NCCALCSIZE_PARAMS
dev_langs:
- C++
helpviewer_keywords:
- NCCALCSIZE_PARAMS structure [MFC]
ms.assetid: 3424cd9f-806a-4089-82fb-414187589edf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 76a0a16ff0a2c90c6dd6060badc2c79dde1af231
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="nccalcsizeparams-structure"></a>NCCALCSIZE_PARAMS-Struktur
Die `NCCALCSIZE_PARAMS` Struktur enthält Informationen, die eine Anwendung, während der Verarbeitung verwenden kann der `WM_NCCALCSIZE` Nachricht zum Berechnen der Größe, Position und gültiger Inhalt des Clientbereichs eines Fensters.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct tagNCCALCSIZE_PARAMS {  
    RECT rgrc[3];  
    PWINDOWPOS lppos;  
} NCCALCSIZE_PARAMS;  
```  
  
#### <a name="parameters"></a>Parameter  
 *rgrc*  
 Gibt ein Array von Rechtecken. Die erste Zeile enthält die neuen Koordinaten eines Fensters, das verschoben oder geändert wurde. Das zweite enthält die Koordinaten des Fensters, bevor es verschoben oder dessen Größe geändert wurde. Das dritte enthält die Koordinaten des Clientbereichs eines Fensters, bevor es verschoben oder dessen Größe geändert wurde. Wenn das Fenster ein untergeordnetes Fenster ist, sind die Koordinaten relativ zum Clientbereich des übergeordneten Fensters. Wenn das Fenster der obersten Ebene ist, sind die Koordinaten relativ zu dem Bildschirm.  
  
 *lppos*  
 Verweist auf eine [WINDOWPOS](../../mfc/reference/windowpos-structure1.md) -Struktur, die in der Vorgang, verursacht das Fenster verschieben oder die Größe, angegebenen Größe und Position Werte enthält.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** winuser.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)

