---
title: CHtmlEditCtrl Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl::CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl::Create
- AFXHTML/CHtmlEditCtrl::GetDHtmlDocument
- AFXHTML/CHtmlEditCtrl::GetStartDocument
dev_langs:
- C++
helpviewer_keywords:
- CHtmlEditCtrl [MFC], CHtmlEditCtrl
- CHtmlEditCtrl [MFC], Create
- CHtmlEditCtrl [MFC], GetDHtmlDocument
- CHtmlEditCtrl [MFC], GetStartDocument
ms.assetid: 0fc4a238-b05f-4874-9edc-6a6701f064d9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f3ea794bfcb3d7e62a53ed8423918e5448990dae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="chtmleditctrl-class"></a>CHtmlEditCtrl-Klasse
Stellt die Funktionalität des WebBrowser-ActiveX-Steuerelements in einem MFC-Fenster bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CHtmlEditCtrl: public CWnd,   
    public CHtmlEditCtrlBase<CHtmlEditCtrl>  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHtmlEditCtrl::CHtmlEditCtrl](#chtmleditctrl)|Erstellt ein `CHtmlEditCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHtmlEditCtrl::Create](#create)|Erstellt ein WebBrowser ActiveX-Steuerelement, und fügt es der `CHtmlEditCtrl` Objekt. Diese Funktion setzt automatisch das WebBrowser ActiveX-Steuerelement in den Bearbeitungsmodus.|  
|[CHtmlEditCtrl::GetDHtmlDocument](#getdhtmldocument)|Ruft die [IHTMLDocument2](https://msdn.microsoft.com/library/aa752574.aspx) Schnittstelle für das Dokument ist derzeit im WebBrowser-Steuerelement enthaltene geladen.|  
|[CHtmlEditCtrl::GetStartDocument](#getstartdocument)|Ruft die URL zu Standarddokument und Laden Sie in das enthaltene WebBrowser-Steuerelement ab.|  
  
## <a name="remarks"></a>Hinweise  
 Die gehostete WebBrowser, die Steuerelement automatisch abgelegt wird Bearbeitungsmodus, nachdem er erstellt wurde.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHtmlEditCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxhtml.h  
  
##  <a name="chtmleditctrl"></a>CHtmlEditCtrl::CHtmlEditCtrl  
 Erstellt ein `CHtmlEditCtrl`-Objekt.  
  
```  
CHtmlEditCtrl();
```  
  
##  <a name="create"></a>CHtmlEditCtrl::Create  
 Erstellt ein WebBrowser ActiveX-Steuerelement, und fügt es der `CHtmlEditCtrl` Objekt. Der WebBrowser ActiveX Steuerelement automatisch zu einem Standarddokument navigiert, und klicken Sie dann in eingefügt Bearbeitungsmodus von dieser Funktion.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszWindowName`  
 Dieser Parameter wird nicht verwendet.  
  
 `dwStyle`  
 Dieser Parameter wird nicht verwendet.  
  
 `rect`  
 Gibt die Größe und Position des Steuerelements.  
  
 `pParentWnd`  
 Gibt die übergeordnete Fenster des Steuerelements an. Es muss nicht **NULL**.  
  
 `nID`  
 Gibt das Steuerelement-ID an.  
  
 `pContext`  
 Dieser Parameter wird nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** bei Erfolg **"false"** bei einem Fehler.  
  
##  <a name="getdhtmldocument"></a>CHtmlEditCtrl::GetDHtmlDocument  
 Ruft die [IHTMLDocument2](https://msdn.microsoft.com/library/aa752574.aspx) Schnittstelle für das Dokument derzeit geladen, in das enthaltene WebBrowser-Steuerelement  
  
```  
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `ppDocument`  
 Der Dokumentschnittstelle.  
  
##  <a name="getstartdocument"></a>CHtmlEditCtrl::GetStartDocument  
 Ruft die URL zu Standarddokument und Laden Sie in das enthaltene WebBrowser-Steuerelement ab.  
  
```  
virtual LPCTSTR GetStartDocument();
```  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)

