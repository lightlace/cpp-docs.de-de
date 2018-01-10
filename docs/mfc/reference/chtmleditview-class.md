---
title: CHtmlEditView Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHtmlEditView
- AFXHTML/CHtmlEditView
- AFXHTML/CHtmlEditView::CHtmlEditView
- AFXHTML/CHtmlEditView::Create
- AFXHTML/CHtmlEditView::GetDHtmlDocument
- AFXHTML/CHtmlEditView::GetStartDocument
dev_langs: C++
helpviewer_keywords:
- CHtmlEditView [MFC], CHtmlEditView
- CHtmlEditView [MFC], Create
- CHtmlEditView [MFC], GetDHtmlDocument
- CHtmlEditView [MFC], GetStartDocument
ms.assetid: 166c8ba8-3fb5-4dd7-a9ea-5bca662d00f6
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 98964a48be8b8c36a3d6d5bd708a51b9963ae105
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="chtmleditview-class"></a>CHtmlEditView-Klasse
Stellt die Funktionalität der WebBrowser-Bearbeitungsplattform im Kontext der MFC-Dokument-/Ansichtarchitektur bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CHtmlEditView : public CHtmlView, public CHtmlEditCtrlBase<CHtmlEditView>  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHtmlEditView::CHtmlEditView](#chtmleditview)|Erstellt ein `CHtmlEditView`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHtmlEditView::Create](#create)|Erstellt ein neues Fensterobjekt.|  
|[CHtmlEditView::GetDHtmlDocument](#getdhtmldocument)|Gibt die **IHTMLDocument2** Schnittstelle für das aktuelle Dokument.|  
|[CHtmlEditView::GetStartDocument](#getstartdocument)|Ruft den Namen der Standarddokument für diese Ansicht ab.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 [CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)  
  
 [CHtmlView](../../mfc/reference/chtmlview-class.md)  
  
 `CHtmlEditView`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxhtml.h  
  
##  <a name="chtmleditview"></a>CHtmlEditView::CHtmlEditView  
 Erstellt ein `CHtmlEditView`-Objekt.  
  
```  
CHtmlEditView();
```  
  
##  <a name="create"></a>CHtmlEditView::Create  
 Erstellt ein neues Fensterobjekt.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszClassName`  
 Verweist auf eine Null-terminierte Zeichenfolge, die den Namen die Windows-Klasse. Der Klassenname kann einen beliebigen Namen registriert die [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) globale Funktion oder die **RegisterClass** Windows-Funktion. Wenn **NULL**, verwendet die vordefinierten Standardwerte [CFrameWnd](../../mfc/reference/cframewnd-class.md) Attribute.  
  
 `lpszWindowName`  
 Verweist auf eine Null-terminierte Zeichenfolge, die den Fensternamen darstellt.  
  
 `dwStyle`  
 Gibt an, die Fenster-Stilattribute. Wird standardmäßig die **WS_VISIBLE** und **WS_CHILD** Fensterstile festgelegt sind.  
  
 `rect`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die Größe und Position des Fensters angibt. Die `rectDefault` Wert ermöglicht es Windows, um die Größe und Position des neuen Fensters festzulegen.  
  
 `pParentWnd`  
 Ein Zeiger auf das übergeordnete Fenster des Steuerelements.  
  
 `nID`  
 Die ID der Sicht. Standardmäßig festgelegt, um **AFX_IDW_PANE_FIRST**.  
  
 `pContext`  
 Ein Zeiger auf eine [angegeben ist und](../../mfc/reference/ccreatecontext-structure.md). **NULL** standardmäßig.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird auch die eigenständigen WebBrowser Aufrufen **navigieren** -Methode zum Laden von ein Standarddokument (finden Sie unter [CHtmlEditView::GetStartDocument](#getstartdocument)).  
  
##  <a name="getdhtmldocument"></a>CHtmlEditView::GetDHtmlDocument  
 Gibt die **IHTMLDocument2** Schnittstelle für das aktuelle Dokument.  
  
```  
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `ppDocument`  
 Die [IHTMLDocument2](https://msdn.microsoft.com/library/aa752574.aspx) Schnittstelle.  
  
##  <a name="getstartdocument"></a>CHtmlEditView::GetStartDocument  
 Ruft den Namen der Standarddokument für diese Ansicht ab.  
  
```  
virtual LPCTSTR GetStartDocument();
```  
  
## <a name="see-also"></a>Siehe auch  
 [HTMLEdit-Beispiel](../../visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)


