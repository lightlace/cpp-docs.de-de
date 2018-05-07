---
title: NCCALCSIZE_PARAMS-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- NCCALCSIZE_PARAMS
dev_langs:
- C++
helpviewer_keywords:
- NCCALCSIZE_PARAMS structure [MFC]
ms.assetid: 3424cd9f-806a-4089-82fb-414187589edf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 07db612cb6dbde0dd762cf709ac6040bbd836c4b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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

