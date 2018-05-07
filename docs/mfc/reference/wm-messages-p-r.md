---
title: 'WM_-Meldungen: P - R | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- ON_WM_RBUTTONUP
- ON_WM_PALETTECHANGED
- ON_WM_RBUTTONDBLCLK
- ON_WM_QUERYENDSESSION
- ON_WM_PARENTNOTIFY
- ON_WM_PALETTEISCHANGING
- ON_WM_QUERYOPEN
- ON_WM_PAINT
- ON_WM_QUERYNEWPALETTE
- ON_WM_RBUTTONDOWN
- ON_WM_RENDERALLFORMATS
- ON_WM_PAINTCLIPBOARD
- ON_WM_RENDERFORMAT
- ON_WM_QUERYDRAGICON
dev_langs:
- C++
helpviewer_keywords:
- ON_WM_RENDERFORMAT [MFC]
- ON_WM_QUERYOPEN [MFC]
- ON_WM_RBUTTONDOWN [MFC]
- ON_WM_PAINTCLIPBOARD [MFC]
- ON_WM_QUERYNEWPALETTE [MFC]
- ON_WM_RBUTTONUP [MFC]
- ON_WM_PARENTNOTIFY [MFC]
- ON_WM_RBUTTONDBLCLK [MFC]
- ON_WM_PALETTECHANGED [MFC]
- ON_WM_PALETTEISCHANGING [MFC]
- ON_WM_QUERYDRAGICON [MFC]
- ON_WM_PAINT [MFC]
- ON_WM_RENDERALLFORMATS [MFC]
- ON_WM_QUERYENDSESSION [MFC]
- WM_ messages
ms.assetid: f46962e5-8329-4f1f-9b4d-fdad2a5ce1f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d37189490a955b2837fa974dfaad3efba0c615bd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="wm-messages-p---r"></a>WM_-Meldungen: P - R
Die folgenden Zuordnungseinträge entsprechen der Funktionsprototypen:  
  
|Eintrag für die Zuordnung|Funktionsprototyp|  
|---------------|------------------------|  
|ON_WM_PAINT()|Afx_msg "void" [OnPaint](../../mfc/reference/cwnd-class.md#onpaint)(;)|  
|ON_WM_PAINTCLIPBOARD()|Afx_msg "void" [OnPaintClipboard](../../mfc/reference/cwnd-class.md#onpaintclipboard)(CWnd *, HANDLE);|  
|ON_WM_PALETTECHANGED()|Afx_msg "void" [OnPaletteChanged](../../mfc/reference/cwnd-class.md#onpalettechanged)(CWnd *);|  
|ON_WM_PALETTEISCHANGING()|Afx_msg "void" [OnPaletteIsChanging](../../mfc/reference/cwnd-class.md#onpaletteischanging)(CWnd *);|  
|ON_WM_PARENTNOTIFY()|Afx_msg "void" [OnParentNotify](../../mfc/reference/cwnd-class.md#onparentnotify)(UINT, LONG);|  
|ON_WM_POWERBROADCAST()|Afx_msg "uint" [OnPowerBroadcast](../../mfc/reference/cwnd-class.md#onpowerbroadcast)("uint", "uint");|  
|ON_WM_QUERYDRAGICON()|Afx_msg HCURSOR [OnQueryDragIcon](../../mfc/reference/cwnd-class.md#onquerydragicon)() ();|  
|ON_WM_QUERYENDSESSION()|Afx_msg BOOL [OnQueryEndSession](../../mfc/reference/cwnd-class.md#onqueryendsession)() ();|  
|ON_WM_QUERYNEWPALETTE()|Afx_msg BOOL [OnQueryNewPalette](../../mfc/reference/cwnd-class.md#onquerynewpalette)() ();|  
|ON_WM_QUERYOPEN()|Afx_msg BOOL [OnQueryOpen](../../mfc/reference/cwnd-class.md#onqueryopen)() ();|  
|ON_WM_RBUTTONDBLCLK()|Afx_msg "void" [OnRButtonDblClk](../../mfc/reference/cwnd-class.md#onrbuttondblclk)("uint", CPoint);|  
|ON_WM_RBUTTONDOWN()|Afx_msg "void" [OnRButtonDown](../../mfc/reference/cwnd-class.md#onrbuttondown)("uint", CPoint);|  
|ON_WM_RBUTTONUP()|Afx_msg "void" [OnRButtonUp](../../mfc/reference/cwnd-class.md#onrbuttonup)("uint", CPoint);|  
|ON_WM_RENDERALLFORMATS()|Afx_msg "void" [OnRenderAllFormats](../../mfc/reference/cwnd-class.md#onrenderallformats)(;)|  
|ON_WM_RENDERFORMAT()|Afx_msg "void" [OnRenderFormat](../../mfc/reference/cwnd-class.md#onrenderformat)("uint");|  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)   
 [Handler für WM_-Meldungen](../../mfc/reference/handlers-for-wm-messages.md)

