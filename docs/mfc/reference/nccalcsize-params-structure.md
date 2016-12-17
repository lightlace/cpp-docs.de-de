---
title: "NCCALCSIZE_PARAMS-Struktur"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "NCCALCSIZE_PARAMS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NCCALCSIZE_PARAMS-Struktur"
ms.assetid: 3424cd9f-806a-4089-82fb-414187589edf
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# NCCALCSIZE_PARAMS-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

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
 [CWnd::OnNcCalcSize](../../mfc/reference/cwnd-class.md#OnNcCalcSize)

