---
title: "WINDOWPOS-Struktur"
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
  - "WINDOWPOS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WINDOWPOS Struktur"
ms.assetid: a4ea7cd9-c4c2-4480-9c55-cbbff72195e1
caps.latest.revision: 11
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# WINDOWPOS-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `WINDOWPOS`\-Struktur enthält Informationen über die Größe und die Position eines Fensters.  
  
## Syntax  
  
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
  
#### Parameter  
 *hwnd*  
 Identifiziert das Fenster.  
  
 *hwndInsertAfter*  
 Identifiziert das Fenster, hinter dem dieses Fenster platziert wird.  
  
 *x*  
 Gibt die Position des linken Rands des Fensters an.  
  
 *y*  
 Gibt die Position des rechten Rands des Fensters an.  
  
 `cx`  
 Gibt der Fensterbreite, in Pixel an.  
  
 `cy`  
 Gibt der Fensterhöhe, in Pixel an.  
  
 `flags`  
 Gibt den Fenster\-Positionieren von Optionen an.  Dieser Member kann einer der folgenden Werte sein:  
  
-   **SWP\_DRAWFRAME** zeichnet Frames \(definiert in der Klassenbeschreibung zum Fenster\) das Fenster.  Das Fenster `WM_NCCALCSIZE` empfängt eine Meldung.  
  
-   **SWP\_FRAMECHANGED** `WM_NCCALCSIZE` sendet eine Meldung im Fenster, wenn die Größe des Fensters nicht geändert wird.  Wenn dieses Flag nicht angegeben wird, wird `WM_NCCALCSIZE` nur gesendet, wenn die Größe des Fensters geändert wird.  
  
-   **SWP\_HIDEWINDOW** blendet das Fenster aus.  
  
-   `SWP_NOACTIVATE` ermöglicht keine das Fenster.  
  
-   **SWP\_NOCOPYBITS** verwirft den gesamten Inhalt des Clientbereichs.  Wenn dieses Flag nicht angegeben wird, wird der gültige Inhalt des Clientbereichs zurück in den Clientbereich gespeichert und kopiert, nachdem das Fenster angepasst oder neu angeordnet ist.  
  
-   `SWP_NOMOVE` verwaltet aktuelle Position beibehalten \(ignoriert die **w** und **y**\-Member\).  
  
-   **SWP\_NOOWNERZORDER** ändert nicht die Position des Besitzerfensters in der Z\-Reihenfolge.  
  
-   `SWP_NOSIZE` verwaltet aktuelle Größe \(ignoriert die **cx** und **cy**\-Member\).  
  
-   **SWP\_NOREDRAW** zeichnet keine Änderungen neu.  
  
-   **SWP\_NOREPOSITION** entspricht der **SWP\_NOOWNERZORDER**.  
  
-   **SWP\_NOSENDCHANGING** verhindert, dass das Fenster die Meldung empfängt. `WM_WINDOWPOSCHANGING`  
  
-   `SWP_NOZORDER` verwaltet aktuelle Reihenfolge bei \(ignoriert den **hwndInsertAfter**\-Member\).  
  
-   **SWP\_SHOWWINDOW** zeigt das Fenster.  
  
## Anforderungen  
 **Header:** winuser.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnWindowPosChanging](../Topic/CWnd::OnWindowPosChanging.md)