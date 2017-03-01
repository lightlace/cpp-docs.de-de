---
title: CHtmlEditView Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHtmlEditView
dev_langs:
- C++
helpviewer_keywords:
- CHtmlEditView class
ms.assetid: 166c8ba8-3fb5-4dd7-a9ea-5bca662d00f6
caps.latest.revision: 24
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
ms.openlocfilehash: d0194d48fe214d7c90b24ff8ce4ef10116cd536a
ms.lasthandoff: 02/24/2017

---
# <a name="chtmleditview-class"></a>CHtmlEditView-Klasse
Stellt die Funktionalität der WebBrowser-Bearbeitungsplattform im Kontext der MFC-Dokument-/Ansichtarchitektur bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CHtmlEditView : public CHtmlView, public CHtmlEditCtrlBase<CHtmlEditView>  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHtmlEditView::CHtmlEditView](#chtmleditview)|Erstellt ein `CHtmlEditView`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CHtmlEditView::Create](#create)|Erstellt ein neues Fensterobjekt.|  
|[CHtmlEditView::GetDHtmlDocument](#getdhtmldocument)|Gibt die **IHTMLDocument2** Schnittstelle auf das aktuelle Dokument.|  
|[CHtmlEditView::GetStartDocument](#getstartdocument)|Ruft den Namen des Dokuments Standard für diese Ansicht.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
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
  
##  <a name="a-namechtmleditviewa--chtmleditviewchtmleditview"></a><a name="chtmleditview"></a>CHtmlEditView::CHtmlEditView  
 Erstellt ein `CHtmlEditView`-Objekt.  
  
```  
CHtmlEditView();
```  
  
##  <a name="a-namecreatea--chtmleditviewcreate"></a><a name="create"></a>CHtmlEditView::Create  
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
 Zeigt auf eine Null-terminierte Zeichenfolge, die die Windows-Klasse bezeichnet. Der Name der Klasse kann einen beliebigen Namen registriert die [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) globale Funktion oder die **RegisterClass** Windows-Funktion. Wenn **NULL**, verwendet die vordefinierte [CFrameWnd](../../mfc/reference/cframewnd-class.md) Attribute.  
  
 `lpszWindowName`  
 Zeigt auf eine Null-terminierte Zeichenfolge, die den Namen des Fensters darstellt.  
  
 `dwStyle`  
 Gibt die Stilattribute Fenster an. In der Standardeinstellung die **WS_VISIBLE** und **WS_CHILD** Fensterstile festgelegt sind.  
  
 `rect`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die die Größe und Position des Fensters angibt. Die `rectDefault` Wert ermöglicht es Windows, um die Größe und Position des neuen Fensters festzulegen.  
  
 `pParentWnd`  
 Ein Zeiger auf das übergeordnete Fenster des Steuerelements.  
  
 `nID`  
 Die ID der Ansicht. Legen Sie in der Standardeinstellung auf **AFX_IDW_PANE_FIRST**.  
  
 `pContext`  
 Ein Zeiger auf eine [angegeben ist und](../../mfc/reference/ccreatecontext-structure.md). **NULL** standardmäßig.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft auch die enthaltenen WebBrowser **navigieren** Methode, um ein Standarddokument laden (finden Sie unter [CHtmlEditView::GetStartDocument](#getstartdocument)).  
  
##  <a name="a-namegetdhtmldocumenta--chtmleditviewgetdhtmldocument"></a><a name="getdhtmldocument"></a>CHtmlEditView::GetDHtmlDocument  
 Gibt die **IHTMLDocument2** Schnittstelle auf das aktuelle Dokument.  
  
```  
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `ppDocument`  
 Die [IHTMLDocument2](https://msdn.microsoft.com/library/aa752574.aspx) Schnittstelle.  
  
##  <a name="a-namegetstartdocumenta--chtmleditviewgetstartdocument"></a><a name="getstartdocument"></a>CHtmlEditView::GetStartDocument  
 Ruft den Namen des Dokuments Standard für diese Ansicht.  
  
```  
virtual LPCTSTR GetStartDocument();
```  
  
## <a name="see-also"></a>Siehe auch  
 [HTMLEdit-Beispiel](../../visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



