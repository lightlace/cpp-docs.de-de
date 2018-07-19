---
title: WINDOWPOS Struktur 1 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- WINDOWPOS
dev_langs:
- C++
helpviewer_keywords:
- WINDOWPOS structure [MFC]
ms.assetid: a4ea7cd9-c4c2-4480-9c55-cbbff72195e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db51e8f9924d69406989b3a9ac12b45f0e55e870
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37885961"
---
# <a name="windowpos-structure1"></a>WINDOWPOS Struktur 1
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
 Bestimmt das Fenster an.  
  
 *hwndInsertAfter*  
 Gibt das Fenster, die hinter, der dieses Fenster dort platziert wird.  
  
 *w*  
 Gibt die Position des linken Rands des Fensters.  
  
 *y*  
 Gibt die Position des rechten Rands des Fensters.  
  
 *CX*  
 Gibt die Fensterbreite in Pixel an.  
  
 *CY*  
 Gibt die Höhe des Fensters, in Pixel an.  
  
 *flags*  
 Gibt Optionen für Fenster-Positionierung. Dieser Member kann einen der folgenden Werte sein:  
  
- SWP_DRAWFRAME zeichnet einen Rahmen (definiert in der Beschreibung der Klasse für das Fenster), um das Fenster. Das Fenster empfängt eine Nachricht WM_NCCALCSIZE.  
  
- SWP_FRAMECHANGED sendet eine WM_NCCALCSIZE Meldung, um Fenster, auch wenn die Größe des Fensters nicht geändert wird. Wenn dieses Flag nicht angegeben ist, wird die WM_NCCALCSIZE gesendet, nur, wenn die Größe des Fensters geändert wird.  
  
- SWP_HIDEWINDOW Blendet das Fenster aus.  
  
- SWP_NOACTIVATE werden diese nicht das Fenster aktiviert.  
  
- SWP_NOCOPYBITS verwirft den gesamten Inhalt des Clientbereichs. Wenn dieses Flag nicht angegeben ist, den gültigen Inhalt des Clientbereichs gespeichert und wieder in den Clientbereich kopiert werden, nachdem das Fenster angepasst oder neu angeordnet wird.  
  
- Aktuelle Position SWP_NOMOVE beibehalten (ignoriert die `x` und `y` Mitglieder).  
  
- SWP_NOOWNERZORDER ändert nicht das besitzende Fenster die Position in der Z-Reihenfolge.  
  
- Aktuelle Größe behält SWP_NOSIZE (ignoriert die `cx` und `cy` Mitglieder).  
  
- SWP_NOREDRAW ist neu zeichnen nicht auf Änderungen.  
  
- SWP_NOREPOSITION SWP_NOOWNERZORDER identisch.  
  
- SWP_NOSENDCHANGING verhindert, dass die WM_WINDOWPOSCHANGING-Nachricht empfangen.  
  
- SWP_NOZORDER behält den aktuellen Sortierung (ignoriert die `hwndInsertAfter` Member).  
  
- SWP_SHOWWINDOW zeigt das Fenster.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** winuser.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging)

