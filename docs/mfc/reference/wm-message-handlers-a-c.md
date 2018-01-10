---
title: 'WM_-Meldungshandler: A - C | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- ON_WM_COMPACTING [MFC]
- ON_WM_COMPAREITEM [MFC]
- ON_WM_CLOSE [MFC]
- ON_WM_CTLCOLOR [MFC]
- ON_WM_CHAR [MFC]
- ON_WM_CAPTURECHANGED [MFC]
- ON_WM_CHARTOITEM [MFC]
- ON_WM_CREATE [MFC]
- ON_WM_ACTIVATE [MFC]
- ON_WM_CONTEXTMENU [MFC]
- ON_WM_CANCELMODE [MFC]
- ON_WM_ASKCBFORMATNAME [MFC]
- ON_WM_CHILDACTIVATE [MFC]
- WM_ messages [MFC]
- ON_WM_ACTIVATEAPP [MFC]
- ON_WM_CHANGECBCHAIN
ms.assetid: 4e315896-d646-4b87-b0ab-41a4a753b045
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9272b54be2717276825dd770bfa15865fea6e631
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="wm-message-handlers-a---c"></a>WM_-Meldungshandler: A - C
Die folgenden Zuordnungseinträge auf der linken Seite entsprechen auf der rechten Seite der Funktionsprototypen:  
  
|Eintrag für die Zuordnung|Funktionsprototyp|  
|---------------|------------------------|  
|ON_WM_ACTIVATE()|Afx_msg "void" [OnActivate](../../mfc/reference/cwnd-class.md#onactivate)("uint", CWnd * BOOL);|  
|ON_WM_ACTIVATEAPP()|Afx_msg "void" [OnActivateApp](../../mfc/reference/cwnd-class.md#onactivateapp)(BOOL, DWORD);|  
|ON_WM_APPCOMMAND()|Afx_msg "void" [OnAppCommand](../../mfc/reference/cwnd-class.md#onappcommand)(CWnd *, "uint", "uint", "uint");|  
|ON_WM_ASKCBFORMATNAME()|Afx_msg "void" [OnAskCbFormatName](../../mfc/reference/cwnd-class.md#onaskcbformatname)("uint", LPSTR);|  
|ON_WM_CANCELMODE()|Afx_msg "void" [OnCancelMode](../../mfc/reference/cwnd-class.md#oncancelmode)(;)|  
|ON_WM_CAPTURECHANGED()|Afx_msg "void" [OnCaptureChanged](../../mfc/reference/cwnd-class.md#oncapturechanged)(CWnd *);|  
|ON_WM_CHANGECBCHAIN()|Afx_msg "void" [OnChangeCbChain](../../mfc/reference/cwnd-class.md#onchangecbchain)(HWND, HWND);|  
|ON_WM_CHAR()|Afx_msg "void" [OnChar](../../mfc/reference/cwnd-class.md#onchar)("uint", "uint", "uint");|  
|ON_WM_CHARTOITEM()|Afx_msg Int [OnCharToItem](../../mfc/reference/cwnd-class.md#onchartoitem)("uint", CWnd *, "uint");|  
|ON_WM_CHILDACTIVATE()|Afx_msg "void" [OnChildActivate](../../mfc/reference/cwnd-class.md#onchildactivate)(;)|  
|ON_WM_CLIPBOARDUPDATE()|Afx_msg "void" [OnClipboardUpdate](../../mfc/reference/cwnd-class.md#onclipboardupdate)(;)|  
|ON_WM_CLOSE()|Afx_msg "void" [OnClose](../../mfc/reference/cwnd-class.md#onclose)(;)|  
|ON_WM_COMPACTING()|Afx_msg "void" [OnCompacting](../../mfc/reference/cwnd-class.md#oncompacting)("uint");|  
|ON_WM_COMPAREITEM()|Afx_msg Int [OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem)(LPCOMPAREITEMSTRUCT);|  
|ON_WM_CONTEXTMENU()|Afx_msg "void" [OnContextMenu](../../mfc/reference/cwnd-class.md#oncontextmenu)(CWnd *, CPoint);|  
|ON_WM_COPYDATA()|Afx_msg BOOL [OnCopyData](../../mfc/reference/cwnd-class.md#oncopydata)(CWnd * pWnd, COPYDATASTRUCT\* pCopyDataStruct);|  
|ON_WM_CREATE()|Afx_msg Int [OnCreate](../../mfc/reference/cwnd-class.md#oncreate)(LPCREATESTRUCT);|  
|ON_WM_CTLCOLOR()|Afx_msg HBRUSH [OnCtlColor](../../mfc/reference/cwnd-class.md#onctlcolor)(CDC *, CWnd\*, "uint");|  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)   
 [Handler für WM_-Meldungen](../../mfc/reference/handlers-for-wm-messages.md)

