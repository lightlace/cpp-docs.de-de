---
title: WINDOWPOS Structure1 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- WINDOWPOS
dev_langs:
- C++
helpviewer_keywords:
- WINDOWPOS structure [MFC]
ms.assetid: a4ea7cd9-c4c2-4480-9c55-cbbff72195e1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7db3991a6767e33c73857daf40a977ac5f6f0b85
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="windowpos-structure1"></a>WINDOWPOS Structure1
Die `WINDOWPOS` Struktur enthält Informationen über die Größe und Position eines Fensters.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct tagWINDOWPOS { /* wp */  
    HWND hwnd;  
    HWND hwndInsertAfter;  
    int x;  
    int y;  
    int cx;  
    int cy;  
    UINT flags;  
} WINDOWPOS;  
```  
  
#### <a name="parameters"></a>Parameter  
 *HWND*  
 Identifiziert das Fenster an.  
  
 *hwndInsertAfter*  
 Identifiziert das Fenster hinter, dem in diesem Fenster befindet.  
  
 *w*  
 Gibt die Position des linken Rands des Fensters.  
  
 *y*  
 Gibt die Position des rechten Rands des Fensters.  
  
 `cx`  
 Gibt die Fensterbreite in Pixel an.  
  
 `cy`  
 Gibt die Fensterhöhe in Pixel an.  
  
 `flags`  
 Gibt Optionen Fenster positionieren. Dieser Member kann einen der folgenden Werte sein:  
  
- **SWP_DRAWFRAME** zeichnet einen Rahmen (definiert in der Beschreibung der Klasse für das Fenster), um das Fenster. Das Fenster empfängt eine `WM_NCCALCSIZE` Nachricht.  
  
- **SWP_FRAMECHANGED** sendet eine `WM_NCCALCSIZE` -Meldung an das Fenster, auch wenn die Größe des Fensters nicht geändert wird. Wenn dieses Flag nicht angegeben ist, `WM_NCCALCSIZE` wird nur gesendet, wenn die Größe des Fensters geändert wird.  
  
- **SWP_HIDEWINDOW** Blendet das Fenster aus.  
  
- `SWP_NOACTIVATE`Das Fenster aktiviert nicht.  
  
- **SWP_NOCOPYBITS** verwirft den gesamten Inhalt des Clientbereichs. Wenn dieses Flag nicht angegeben ist, werden den gültigen Inhalt des Clientbereichs gespeichert und wieder in den Clientbereich kopiert werden, nachdem das Fenster Größe oder neu angeordnet wurden.  
  
- `SWP_NOMOVE`Behält die aktuelle Position (ignoriert die **x** und **y** Elemente).  
  
- **SWP_NOOWNERZORDER** ändert sich nicht auf das Besitzerfenster Position in der Z-Reihenfolge.  
  
- `SWP_NOSIZE`Behält die aktuelle Größe (ignoriert die **Cx** und **cy** Elemente).  
  
- **SWP_NOREDRAW** Änderungen werden nicht neu zeichnet.  
  
- **SWP_NOREPOSITION** wie **SWP_NOOWNERZORDER**.  
  
- **SWP_NOSENDCHANGING** wird verhindert, dass das Fenster empfangen die `WM_WINDOWPOSCHANGING` Nachricht.  
  
- `SWP_NOZORDER`Beibehalten der aktuellen Sortierung (ignoriert die **HwndInsertAfter** Element).  
  
- **SWP_SHOWWINDOW** zeigt das Fenster an.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** winuser.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging)

