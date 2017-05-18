---
title: 'WM_-Meldungshandler: A - C | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ON_WM_CREATE
- ON_WM_COMPACTING
- ON_WM_CHARTOITEM
- ON_WM_ASKCBFORMATNAME
- ON_WM_CTLCOLOR
- ON_WM_COMPAREITEM
- ON_WM_CHILDACTIVATE
- ON_WM_CONTEXTMENU
- ON_WM_ACTIVATE
- ON_WM_CANCELMODE
- ON_WM_CLOSE
- ON_WM_CAPTURECHANGED
- ON_WM_ACTIVATEAPP
- ON_WM_CHAR
- ON_WM_CHANGECBCHAIN
dev_langs:
- C++
helpviewer_keywords:
- ON_WM_COMPACTING
- ON_WM_COMPAREITEM
- ON_WM_CLOSE
- ON_WM_CTLCOLOR
- ON_WM_CHAR
- ON_WM_CAPTURECHANGED
- ON_WM_CHARTOITEM
- ON_WM_CREATE
- ON_WM_ACTIVATE
- ON_WM_CONTEXTMENU
- ON_WM_CANCELMODE
- ON_WM_ASKCBFORMATNAME
- ON_WM_CHILDACTIVATE
- WM_ messages
- ON_WM_ACTIVATEAPP
- ON_WM_CHANGECBCHAIN
ms.assetid: 4e315896-d646-4b87-b0ab-41a4a753b045
caps.latest.revision: 16
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
ms.openlocfilehash: 4b8a6b0527758e8eff8f2ab3ece4a69927176e2c
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="wm-message-handlers-a---c"></a>WM_-Meldungshandler: A - C
Die folgenden Einträge der Karte auf der linken Seite entsprechen die Funktionsprototypen auf der rechten Seite:  
  
|Eintrag für die Zuordnung|Funktionsprototyp|  
|---------------|------------------------|  
|ON_WM_ACTIVATE()|Afx_msg Void [OnActivate](../../mfc/reference/cwnd-class.md#onactivate)(UINT, CWnd *, BOOL);|  
|ON_WM_ACTIVATEAPP()|Afx_msg Void [OnActivateApp](../../mfc/reference/cwnd-class.md#onactivateapp)(BOOL, DWORD);|  
|ON_WM_APPCOMMAND()|Afx_msg Void [OnAppCommand](../../mfc/reference/cwnd-class.md#onappcommand)(CWnd *, "uint", "uint", "uint");|  
|ON_WM_ASKCBFORMATNAME()|Afx_msg Void [OnAskCbFormatName](../../mfc/reference/cwnd-class.md#onaskcbformatname)(UINT, LPSTR);|  
|ON_WM_CANCELMODE()|Afx_msg Void [OnCancelMode](../../mfc/reference/cwnd-class.md#oncancelmode)();|  
|ON_WM_CAPTURECHANGED()|Afx_msg Void [OnCaptureChanged](../../mfc/reference/cwnd-class.md#oncapturechanged)(CWnd *);|  
|ON_WM_CHANGECBCHAIN()|Afx_msg Void [OnChangeCbChain](../../mfc/reference/cwnd-class.md#onchangecbchain)(HWND, HWND);|  
|ON_WM_CHAR()|Afx_msg Void [OnChar](../../mfc/reference/cwnd-class.md#onchar)("uint", "uint", "uint");|  
|ON_WM_CHARTOITEM()|Afx_msg Int [OnCharToItem](../../mfc/reference/cwnd-class.md#onchartoitem)(UINT, CWnd *, "uint");|  
|ON_WM_CHILDACTIVATE()|Afx_msg Void [OnChildActivate](../../mfc/reference/cwnd-class.md#onchildactivate)();|  
|ON_WM_CLIPBOARDUPDATE()|Afx_msg Void [OnClipboardUpdate](../../mfc/reference/cwnd-class.md#onclipboardupdate)();|  
|ON_WM_CLOSE()|Afx_msg Void [OnClose](../../mfc/reference/cwnd-class.md#onclose)();|  
|ON_WM_COMPACTING()|Afx_msg Void [OnCompacting](../../mfc/reference/cwnd-class.md#oncompacting)(UINT);|  
|ON_WM_COMPAREITEM()|Afx_msg Int [OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem)(LPCOMPAREITEMSTRUCT);|  
|ON_WM_CONTEXTMENU()|Afx_msg Void [OnContextMenu](../../mfc/reference/cwnd-class.md#oncontextmenu)(CWnd *, CPoint);|  
|ON_WM_COPYDATA()|Afx_msg BOOL [OnCopyData](../../mfc/reference/cwnd-class.md#oncopydata)(CWnd * aufnehmen, COPYDATASTRUCT\* pCopyDataStruct);|  
|ON_WM_CREATE()|Afx_msg Int [OnCreate](../../mfc/reference/cwnd-class.md#oncreate)(LPCREATESTRUCT);|  
|ON_WM_CTLCOLOR()|Afx_msg HBRUSH [OnCtlColor](../../mfc/reference/cwnd-class.md#onctlcolor)(CDC *, CWnd\*, "uint");|  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)   
 [Handler für WM_-Meldungen](../../mfc/reference/handlers-for-wm-messages.md)


