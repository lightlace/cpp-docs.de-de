---
title: 'WM_-Meldungen: S | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ON_WM_SYSDEADCHAR
- ON_WM_SYSKEYDOWN
- ON_WM_STYLECHANGING
- ON_WM_STYLECHANGED
- ON_WM_SPOOLERSTATUS
- ON_WM_SYSCHAR
- ON_WM_SETFOCUS
- ON_WM_SIZE
- ON_WM_SIZING
- ON_WM_SETCURSOR
- ON_WM_SYSCOMMAND
- ON_WM_SETTINGCHANGE
- ON_WM_SHOWWINDOW
- ON_WM_SYSKEYUP
- ON_WM_SIZECLIPBOARD
- ON_WM_SYSCOLORCHANGE
dev_langs:
- C++
helpviewer_keywords:
- ON_WM_SIZE [MFC]
- ON_WM_SETFOCUS [MFC]
- ON_WM_SIZING [MFC]
- ON_WM_SYSCHAR [MFC]
- ON_WM_SETTINGCHANGE [MFC]
- ON_WM_SYSDEADCHAR [MFC]
- ON_WM_SHOWWINDOW [MFC]
- ON_WM_STYLECHANGING [MFC]
- ON_WM_SYSCOMMAND [MFC]
- ON_WM_STYLECHANGED [MFC]
- ON_WM_SPOOLERSTATUS [MFC]
- ON_WM_SYSCOLORCHANGE [MFC]
- ON_WM_SETCURSOR [MFC]
- ON_WM_SIZECLIPBOARD [MFC]
- ON_WM_SYSKEYUP [MFC]
- ON_WM_SYSKEYDOWN [MFC]
- WM_ messages
ms.assetid: 4b9aec79-a98f-4aa0-a3d9-110941b6dcbc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2ddc99b2aa360e35224f24920d6a8ae3de920c6c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="wm-messages-s"></a>WM_-Meldungen: S
Die folgenden Zuordnungseinträge entsprechen der Funktionsprototypen.  
  
|Eintrag für die Zuordnung|Funktionsprototyp|  
|---------------|------------------------|  
|ON_WM_SETCURSOR)|Afx_msg BOOL [OnSetCursor](../../mfc/reference/cwnd-class.md#onsetcursor)(CWnd *, "uint", "uint");|  
|ON_WM_SETFOCUS)|Afx_msg "void" [OnSetFocus](../../mfc/reference/cwnd-class.md#onsetfocus)(CWnd *);|  
|ON_WM_SETTINGCHANGE)|Afx_msg "void" [OnSettingChange](../../mfc/reference/cwnd-class.md#onsettingchange)("uint" uFlags, LPCTSTR LpszSection);|  
|ON_WM_SHOWWINDOW)|Afx_msg "void" [OnShowWindow](../../mfc/reference/cwnd-class.md#onshowwindow)(BOOL, "uint");|  
|ON_WM_SIZE)|Afx_msg "void" [OnSize](../../mfc/reference/cwnd-class.md#onsize)("uint", Int, Int);|  
|ON_WM_SIZECLIPBOARD)|Afx_msg "void" [OnSizeClipboard](../../mfc/reference/cwnd-class.md#onsizeclipboard)(CWnd *, HANDLE);|  
|ON_WM_SIZING)|Afx_msg "void" [OnSizing](../../mfc/reference/cwnd-class.md#onsizing)("uint", LPRECT);|  
|ON_WM_SPOOLERSTATUS)|Afx_msg "void" [OnSpoolerStatus](../../mfc/reference/cwnd-class.md#onspoolerstatus)("uint", "uint");|  
|ON_WM_STYLECHANGED)|Afx_msg "void" [OnStyleChanged](../../mfc/reference/cwnd-class.md#onstylechanged)(Int, LPSTYLESTRUCT);|  
|ON_WM_STYLECHANGING)|Afx_msg "void" [OnStyleChanging](../../mfc/reference/cwnd-class.md#onstylechanging)(Int, LPSTYLESTRUCT);|  
|ON_WM_SYSCHAR)|Afx_msg "void" [OnSysChar](../../mfc/reference/cwnd-class.md#onsyschar)("uint", "uint", "uint");|  
|ON_WM_SYSCOLORCHANGE)|Afx_msg "void" [OnSysColorChange](../../mfc/reference/cwnd-class.md#onsyscolorchange)();|  
|ON_WM_SYSCOMMAND)|Afx_msg "void" [OnSysCommand](../../mfc/reference/cwnd-class.md#onsyscommand)(UINT, LONG);|  
|ON_WM_SYSDEADCHAR)|Afx_msg "void" [OnSysDeadChar](../../mfc/reference/cwnd-class.md#onsysdeadchar)("uint", "uint", "uint");|  
|ON_WM_SYSKEYDOWN)|Afx_msg "void" [OnSysKeyDown](../../mfc/reference/cwnd-class.md#onsyskeydown)("uint", "uint", "uint");|  
|ON_WM_SYSKEYUP)|Afx_msg "void" [OnSysKeyUp](../../mfc/reference/cwnd-class.md#onsyskeyup)("uint", "uint", "uint");|  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)   
 [Handler für WM_-Meldungen](../../mfc/reference/handlers-for-wm-messages.md)

