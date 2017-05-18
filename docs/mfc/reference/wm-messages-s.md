---
title: 'WM_-Meldungen: S | Microsoft-Dokumentation'
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
- ON_WM_SIZE
- ON_WM_SETFOCUS
- ON_WM_SIZING
- ON_WM_SYSCHAR
- ON_WM_SETTINGCHANGE
- ON_WM_SYSDEADCHAR
- ON_WM_SHOWWINDOW
- ON_WM_STYLECHANGING
- ON_WM_SYSCOMMAND
- ON_WM_STYLECHANGED
- ON_WM_SPOOLERSTATUS
- ON_WM_SYSCOLORCHANGE
- ON_WM_SETCURSOR
- ON_WM_SIZECLIPBOARD
- ON_WM_SYSKEYUP
- ON_WM_SYSKEYDOWN
- WM_ messages
ms.assetid: 4b9aec79-a98f-4aa0-a3d9-110941b6dcbc
caps.latest.revision: 14
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
ms.openlocfilehash: 339b03be41187ad0249ae38d36d4640401247a83
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="wm-messages-s"></a>WM_-Meldungen: S
Die folgenden Zuordnungseinträge entsprechen die Funktionsprototypen.  
  
|Eintrag für die Zuordnung|Funktionsprototyp|  
|---------------|------------------------|  
|ON_WM_SETCURSOR)|Afx_msg BOOL [OnSetCursor](../../mfc/reference/cwnd-class.md#onsetcursor)(CWnd *, "uint", "uint");|  
|ON_WM_SETFOCUS)|Afx_msg Void [OnSetFocus](../../mfc/reference/cwnd-class.md#onsetfocus)(CWnd *);|  
|ON_WM_SETTINGCHANGE)|Afx_msg Void [OnSettingChange](../../mfc/reference/cwnd-class.md#onsettingchange)(UINT uFlags, LPCTSTR LpszSection);|  
|ON_WM_SHOWWINDOW)|Afx_msg Void [OnShowWindow](../../mfc/reference/cwnd-class.md#onshowwindow)(BOOL, "uint");|  
|ON_WM_SIZE)|Afx_msg Void [OnSize](../../mfc/reference/cwnd-class.md#onsize)(UINT, Int, Int);|  
|ON_WM_SIZECLIPBOARD)|Afx_msg Void [OnSizeClipboard](../../mfc/reference/cwnd-class.md#onsizeclipboard)(CWnd *, HANDLE);|  
|ON_WM_SIZING)|Afx_msg Void [OnSizing](../../mfc/reference/cwnd-class.md#onsizing)(UINT, LPRECT);|  
|ON_WM_SPOOLERSTATUS)|Afx_msg Void [OnSpoolerStatus](../../mfc/reference/cwnd-class.md#onspoolerstatus)("uint", "uint");|  
|ON_WM_STYLECHANGED)|Afx_msg Void [OnStyleChanged](../../mfc/reference/cwnd-class.md#onstylechanged)(Int, LPSTYLESTRUCT);|  
|ON_WM_STYLECHANGING)|Afx_msg Void [OnStyleChanging](../../mfc/reference/cwnd-class.md#onstylechanging)(Int, LPSTYLESTRUCT);|  
|ON_WM_SYSCHAR)|Afx_msg Void [OnSysChar](../../mfc/reference/cwnd-class.md#onsyschar)("uint", "uint", "uint");|  
|ON_WM_SYSCOLORCHANGE)|Afx_msg Void [OnSysColorChange](../../mfc/reference/cwnd-class.md#onsyscolorchange)();|  
|ON_WM_SYSCOMMAND)|Afx_msg Void [OnSysCommand](../../mfc/reference/cwnd-class.md#onsyscommand)(UINT, LONG);|  
|ON_WM_SYSDEADCHAR)|Afx_msg Void [OnSysDeadChar](../../mfc/reference/cwnd-class.md#onsysdeadchar)("uint", "uint", "uint");|  
|ON_WM_SYSKEYDOWN)|Afx_msg Void [OnSysKeyDown](../../mfc/reference/cwnd-class.md#onsyskeydown)("uint", "uint", "uint");|  
|ON_WM_SYSKEYUP)|Afx_msg Void [OnSysKeyUp](../../mfc/reference/cwnd-class.md#onsyskeyup)("uint", "uint", "uint");|  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)   
 [Handler für WM_-Meldungen](../../mfc/reference/handlers-for-wm-messages.md)


