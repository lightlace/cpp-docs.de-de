---
title: WINDOWPOS Structure1 | Microsoft-Dokumentation
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
- WINDOWPOS structure
ms.assetid: a4ea7cd9-c4c2-4480-9c55-cbbff72195e1
caps.latest.revision: 11
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 522b15d630c3a5a3593010250db0491601493c69
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

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
 Identifiziert das Fenster.  
  
 *hwndInsertAfter*  
 Identifiziert das Fenster hinter, dem in diesem Fenster befindet.  
  
 *x*  
 Gibt die Position des linken Rands des Fensters.  
  
 *y*  
 Gibt die Position des rechten Rands des Fensters.  
  
 `cx`  
 Gibt die Breite des Fensters in Pixel.  
  
 `cy`  
 Gibt die Höhe des Fensters in Pixel.  
  
 `flags`  
 Gibt die Optionen im Fenster positioniert. Dieser Member kann einen der folgenden Werte sein:  
  
- **SWP_DRAWFRAME** zeichnet einen Rahmen (definiert in der Beschreibung der Klasse für das Fenster), um das Fenster. Das Fenster empfängt eine `WM_NCCALCSIZE` Nachricht.  
  
- **SWP_FRAMECHANGED** sendet eine `WM_NCCALCSIZE` Meldung in das Fenster, auch wenn die Größe des Fensters nicht geändert wird. Wenn dieses Flag nicht angegeben ist, `WM_NCCALCSIZE` wird nur gesendet, wenn die Größe des Fensters geändert wird.  
  
- **SWP_HIDEWINDOW** Blendet das Fenster aus.  
  
- `SWP_NOACTIVATE`Das Fenster wird nicht aktiviert werden.  
  
- **SWP_NOCOPYBITS** verwirft den gesamten Inhalt des Clientbereichs. Wenn dieses Flag nicht angegeben ist, werden der gültige Inhalt des Clientbereichs gespeichert und wieder in den Clientbereich kopiert werden, nachdem das Fenster angepasst oder neu angeordnet wird.  
  
- `SWP_NOMOVE`Behält die aktuelle Position (ignoriert die **x** und **y** Elemente).  
  
- **SWP_NOOWNERZORDER** ändert nicht das Besitzerfenster Position in der Z-Reihenfolge.  
  
- `SWP_NOSIZE`Aktuelle Größe beibehält (ignoriert die **Cx** und **cy** Elemente).  
  
- **SWP_NOREDRAW** Änderungen wird nicht neu gezeichnet.  
  
- **SWP_NOREPOSITION** wie **SWP_NOOWNERZORDER**.  
  
- **SWP_NOSENDCHANGING** verhindert, empfangen die `WM_WINDOWPOSCHANGING` Nachricht.  
  
- `SWP_NOZORDER`Beibehalten der aktuellen Sortierung (ignoriert die **HwndInsertAfter** Element).  
  
- **SWP_SHOWWINDOW** zeigt das Fenster an.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** winuser.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging)


