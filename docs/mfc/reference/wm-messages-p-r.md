---
title: "WM_-Meldungen: P - R"
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
  - "ON_WM_RBUTTONUP"
  - "ON_WM_PALETTECHANGED"
  - "ON_WM_RBUTTONDBLCLK"
  - "ON_WM_QUERYENDSESSION"
  - "ON_WM_PARENTNOTIFY"
  - "ON_WM_PALETTEISCHANGING"
  - "ON_WM_QUERYOPEN"
  - "ON_WM_PAINT"
  - "ON_WM_QUERYNEWPALETTE"
  - "ON_WM_RBUTTONDOWN"
  - "ON_WM_RENDERALLFORMATS"
  - "ON_WM_PAINTCLIPBOARD"
  - "ON_WM_RENDERFORMAT"
  - "ON_WM_QUERYDRAGICON"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ON_WM_PAINT"
  - "ON_WM_PAINTCLIPBOARD"
  - "ON_WM_PALETTECHANGED"
  - "ON_WM_PALETTEISCHANGING"
  - "ON_WM_PARENTNOTIFY"
  - "ON_WM_QUERYDRAGICON"
  - "ON_WM_QUERYENDSESSION"
  - "ON_WM_QUERYNEWPALETTE"
  - "ON_WM_QUERYOPEN"
  - "ON_WM_RBUTTONDBLCLK"
  - "ON_WM_RBUTTONDOWN"
  - "ON_WM_RBUTTONUP"
  - "ON_WM_RENDERALLFORMATS"
  - "ON_WM_RENDERFORMAT"
  - "WM_-Meldungen"
ms.assetid: f46962e5-8329-4f1f-9b4d-fdad2a5ce1f8
caps.latest.revision: 15
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# WM_-Meldungen: P - R
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Einträge die folgende Zuordnung entsprechen den Funktionsprototypen:  
  
|Zuordnungseintrag|Funktionsprototyp|  
|-----------------------|-----------------------|  
|ON\_WM\_PAINT\(\)|afx\_msg void [OnPaint](../Topic/CWnd::OnPaint.md)\(\);|  
|ON\_WM\_PAINTCLIPBOARD\(\)|afx\_msg void [OnPaintClipboard](../Topic/CWnd::OnPaintClipboard.md)\(CWnd\*, HANDLE\);|  
|ON\_WM\_PALETTECHANGED\(\)|afx\_msg void [OnPaletteChanged](../Topic/CWnd::OnPaletteChanged.md)\(CWnd\*\);|  
|ON\_WM\_PALETTEISCHANGING\(\)|afx\_msg void [OnPaletteIsChanging](../Topic/CWnd::OnPaletteIsChanging.md)\(CWnd\*\);|  
|ON\_WM\_PARENTNOTIFY\(\)|afx\_msg void [OnParentNotify](../Topic/CWnd::OnParentNotify.md)\(UINT, LONG\);|  
|ON\_WM\_POWERBROADCAST\(\)|afx\_msg UINT [OnPowerBroadcast](../Topic/CWnd::OnPowerBroadcast.md)\(UINT, UINT\);|  
|ON\_WM\_QUERYDRAGICON\(\)|afx\_msg HCURSOR [OnQueryDragIcon](../Topic/CWnd::OnQueryDragIcon.md)\(\)\(\);|  
|ON\_WM\_QUERYENDSESSION\(\)|afx\_msg BOOL [OnQueryEndSession](../Topic/CWnd::OnQueryEndSession.md)\(\)\(\);|  
|ON\_WM\_QUERYNEWPALETTE\(\)|afx\_msg BOOL [OnQueryNewPalette](../Topic/CWnd::OnQueryNewPalette.md)\(\)\(\);|  
|ON\_WM\_QUERYOPEN\(\)|afx\_msg BOOL [OnQueryOpen](../Topic/CWnd::OnQueryOpen.md)\(\)\(\);|  
|ON\_WM\_RBUTTONDBLCLK\(\)|afx\_msg void [OnRButtonDblClk](../Topic/CWnd::OnRButtonDblClk.md)\(UINT, CPoint\);|  
|ON\_WM\_RBUTTONDOWN\(\)|afx\_msg void [OnRButtonDown](../Topic/CWnd::OnRButtonDown.md)\(UINT, CPoint\);|  
|ON\_WM\_RBUTTONUP\(\)|afx\_msg void [OnRButtonUp](../Topic/CWnd::OnRButtonUp.md)\(UINT, CPoint\);|  
|ON\_WM\_RENDERALLFORMATS\(\)|afx\_msg void [OnRenderAllFormats](../Topic/CWnd::OnRenderAllFormats.md)\(\);|  
|ON\_WM\_RENDERFORMAT\(\)|afx\_msg void [OnRenderFormat](../Topic/CWnd::OnRenderFormat.md)\(UINT\);|  
  
## Siehe auch  
 [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)   
 [Handler für WM\_\-Meldungen](../../mfc/reference/handlers-for-wm-messages.md)