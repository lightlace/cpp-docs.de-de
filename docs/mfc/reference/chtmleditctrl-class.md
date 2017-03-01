---
title: Klasse CHtmlEditCtrl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHtmlEditCtrl
dev_langs:
- C++
helpviewer_keywords:
- CHtmlEditCtrl class
ms.assetid: 0fc4a238-b05f-4874-9edc-6a6701f064d9
caps.latest.revision: 22
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 4aca52508663e94ee9a1b55843ad05613aa40b0b
ms.lasthandoff: 02/24/2017

---
# <a name="chtmleditctrl-class"></a>CHtmlEditCtrl-Klasse
Stellt die Funktionalität des WebBrowser-ActiveX-Steuerelements in einem MFC-Fenster bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CHtmlEditCtrl: public CWnd,   
    public CHtmlEditCtrlBase<CHtmlEditCtrl>  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHtmlEditCtrl::CHtmlEditCtrl](#chtmleditctrl)|Erstellt ein `CHtmlEditCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHtmlEditCtrl::Create](#create)|Erstellt ein WebBrowser ActiveX-Steuerelement und fügt es der `CHtmlEditCtrl` Objekt. Diese Funktion stellt automatisch das WebBrowser ActiveX-Steuerelement in den Bearbeitungsmodus.|  
|[CHtmlEditCtrl::GetDHtmlDocument](#getdhtmldocument)|Ruft die [IHTMLDocument2](https://msdn.microsoft.com/library/aa752574.aspx) Schnittstelle für das Dokument im enthaltenen WebBrowser-Steuerelement geladen.|  
|[CHtmlEditCtrl::GetStartDocument](#getstartdocument)|Ruft die URL zu einem Standarddokument und in das enthaltene WebBrowser-Steuerelement geladen.|  
  
## <a name="remarks"></a>Hinweise  
 Die gehostete WebBrowser, das Steuerelement automatisch abgelegt ist Bearbeitungsmodus, nachdem es erstellt wurde.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHtmlEditCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxhtml.h  
  
##  <a name="a-namechtmleditctrla--chtmleditctrlchtmleditctrl"></a><a name="chtmleditctrl"></a>CHtmlEditCtrl::CHtmlEditCtrl  
 Erstellt ein `CHtmlEditCtrl`-Objekt.  
  
```  
CHtmlEditCtrl();
```  
  
##  <a name="a-namecreatea--chtmleditctrlcreate"></a><a name="create"></a>CHtmlEditCtrl::Create  
 Erstellt ein WebBrowser ActiveX-Steuerelement und fügt es der `CHtmlEditCtrl` Objekt. Der WebBrowser ActiveX Steuerelement navigiert automatisch zu einem Standarddokument und wird dann platziert den Bearbeitungsmodus von dieser Funktion.  
  
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
 Gibt die übergeordnete Fenster des Steuerelements. Er darf nicht sein **NULL**.  
  
 `nID`  
 Gibt die ID des Steuerelements an  
  
 `pContext`  
 Dieser Parameter wird nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** bei Erfolg **FALSE** bei einem Fehler.  
  
##  <a name="a-namegetdhtmldocumenta--chtmleditctrlgetdhtmldocument"></a><a name="getdhtmldocument"></a>CHtmlEditCtrl::GetDHtmlDocument  
 Ruft die [IHTMLDocument2](https://msdn.microsoft.com/library/aa752574.aspx) Schnittstelle für das Dokument in das WebBrowser-Steuerelement enthaltenen geladenen  
  
```  
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `ppDocument`  
 Die Dokumentschnittstelle.  
  
##  <a name="a-namegetstartdocumenta--chtmleditctrlgetstartdocument"></a><a name="getstartdocument"></a>CHtmlEditCtrl::GetStartDocument  
 Ruft die URL zu einem Standarddokument und in das enthaltene WebBrowser-Steuerelement geladen.  
  
```  
virtual LPCTSTR GetStartDocument();
```  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)


