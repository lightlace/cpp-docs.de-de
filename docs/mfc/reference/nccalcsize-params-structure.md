---
title: NCCALCSIZE_PARAMS-Struktur | Microsoft-Dokumentation
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
ms.openlocfilehash: 095b66af9dab08e3d8fad040c43e2eaf8d2beb81
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37335642"
---
# <a name="nccalcsizeparams-structure"></a>NCCALCSIZE_PARAMS-Struktur
Die `NCCALCSIZE_PARAMS` Struktur enthält Informationen, die eine Anwendung bei der Nachrichtenverarbeitung WM_NCCALCSIZE verwenden kann, um die Größe, Position und gültigen Inhalt des Clientbereichs eines Fensters zu berechnen.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct tagNCCALCSIZE_PARAMS {  
    RECT rgrc[3];  
    PWINDOWPOS lppos;  
} NCCALCSIZE_PARAMS;  
```  
  
#### <a name="parameters"></a>Parameter  
 *rgrc*  
 Gibt ein Array von Rechtecken. Die erste enthält die neuen Koordinaten eines Fensters, die verschoben oder geändert wurde. Die zweite enthält die Koordinaten des Fensters auf, bevor es verschoben oder ihre Größe geändert wurde. Die dritte enthält die Koordinaten des Clientbereichs eines Fensters aus, bevor es verschoben oder ihre Größe geändert wurde. Wenn das Fenster ein untergeordnetes Fenster ist, sind die Koordinaten relativ zum Clientbereich des übergeordneten Fensters. Wenn das Fenster der obersten Ebene ist, sind die Koordinaten relativ zum Bildschirm an.  
  
 *lppos*  
 Verweist auf eine [WINDOWPOS](../../mfc/reference/windowpos-structure1.md) -Struktur, die in die Operation, verursacht das Fenster verschoben oder angepasst werden, angegebenen Größe und Position-Werte enthält.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** winuser.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)

