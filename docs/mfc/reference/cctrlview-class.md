---
title: CCtrlView-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCtrlView
- AFXWIN/CCtrlView
- AFXWIN/CCtrlView::CCtrlView
- AFXWIN/CCtrlView::OnDraw
- AFXWIN/CCtrlView::PreCreateWindow
- AFXWIN/CCtrlView::m_dwDefaultStyle
- AFXWIN/CCtrlView::m_strClass
dev_langs:
- C++
helpviewer_keywords:
- CCtrlView [MFC], CCtrlView
- CCtrlView [MFC], OnDraw
- CCtrlView [MFC], PreCreateWindow
- CCtrlView [MFC], m_dwDefaultStyle
- CCtrlView [MFC], m_strClass
ms.assetid: ff488596-1e71-451f-8fec-b0831a7b44e0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 80e89573e67113900db7b35ffe3f1189de1c524a
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2018
ms.locfileid: "37336331"
---
# <a name="cctrlview-class"></a>CCtrlView-Klasse
Passt die Dokument-/Ansichtarchitektur den allgemeinen Steuerelemente an, die von Windows 98 und Windows NT-Versionen 3,51 (und höher) unterstützt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CCtrlView : public CView  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCtrlView::CCtrlView](#cctrlview)|Erstellt ein `CCtrlView`-Objekt.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCtrlView::OnDraw](#ondraw)|Wird aufgerufen, durch das Framework, um mit den angegebenen Gerätekontext zu zeichnen.|  
|[CCtrlView::PreCreateWindow](#precreatewindow)|Wird vor der Erstellung des an diesem `CCtrlView`-Objekt angefügten Windows-Fensters aufgerufen.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CCtrlView::m_dwDefaultStyle](#m_dwdefaultstyle)|Enthält den Standardstil für die View-Klasse.|  
|[CCtrlView::m_strClass](#m_strclass)|Enthält den Namen des Windows-Klasse für die Ansichtsklasse.|  
  
## <a name="remarks"></a>Hinweise  
 Die Klasse `CCtrlView` und dessen Derivate, [CEditView](../../mfc/reference/ceditview-class.md), [CListView](../../mfc/reference/clistview-class.md), [CTreeView](../../mfc/reference/ctreeview-class.md), und [CRichEditView](../../mfc/reference/cricheditview-class.md), passen Sie die Dokument-/ Ansichtarchitektur den neuen allgemeinen Steuerelemente an, die von Windows 95/98 und Windows NT, Version 3.51 und höher unterstützt. Weitere Informationen zu den Dokument-/ Ansichtarchitektur, finden Sie unter [Dokument-/Ansichtarchitektur](../../mfc/document-view-architecture.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 `CCtrlView`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="cctrlview"></a>  CCtrlView::CCtrlView  
 Erstellt ein `CCtrlView`-Objekt.  
  
```  
CCtrlView(
    LPCTSTR lpszClass,  
    DWORD dwStyle);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszClass*  
 Windows-Klassenname der Ansichtsklasse.  
  
 *dwStyle*  
 Die Art der Ansichtsklasse.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework Ruft den Konstruktor, wenn ein neues Rahmenfensterobjekt erstellt wird, oder Teilen Sie ein Fenster ist. Außer Kraft setzen [CView:: OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) zum Initialisieren der Ansicht, nachdem das Dokument angefügt ist. Rufen Sie [CWnd:: Create](../../mfc/reference/cwnd-class.md#create) oder [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex) zum Erstellen des Windows-Objekts.  
  
##  <a name="m_strclass"></a>  CCtrlView::m_strClass  
 Enthält den Namen des Windows-Klasse für die Ansichtsklasse.  
  
```  
CString m_strClass;  
```  
  
##  <a name="m_dwdefaultstyle"></a>  CCtrlView::m_dwDefaultStyle  
 Enthält den Standardstil für die View-Klasse.  
  
```  
DWORD m_dwDefaultStyle;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Stil wird angewendet, wenn ein Fenster erstellt wird.  
  
##  <a name="ondraw"></a>  CCtrlView::OnDraw  
 Aufgerufen, um den Inhalt der Zeichnen die `CCtrlView` -Objekt mit den angegebenen Gerätekontext.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 *pDC*  
 Ein Zeiger auf den Gerätekontext, in dem das Zeichnen auftritt.  
  
### <a name="remarks"></a>Hinweise  
 `OnDraw` ist in der Regel für die Bildschirmanzeige, übergeben einen Bildschirm Gerätekontext, die anhand des Namens *pDC*.  
  
##  <a name="precreatewindow"></a>  CCtrlView::PreCreateWindow  
 Wird vor der Erstellung des an diesem `CWnd`-Objekt angefügten Windows-Fensters aufgerufen.  
  
```  
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```  
  
### <a name="parameters"></a>Parameter  
 *cs*  
 Ein [CREATESTRUCT](http://msdn.microsoft.com/library/windows/desktop/ms632603) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Legen Sie ungleich NULL, wenn es sich bei der fenstererstellung fortgesetzt werden soll; 0, um Fehler bei der wiederherstellungspunkterstellung anzugeben.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird nie direkt aufrufen.  
  
 Die Standardimplementierung dieser Funktion einen NULL-Fensterklassennamen überprüft und einen geeigneten Standardwert ersetzt. Überschreiben Sie diese Memberfunktion so ändern Sie die `CREATESTRUCT` strukturieren, bevor das Fenster erstellt wird.  
  
 Jede Klasse abgeleitet `CCtrlView` eigene funktionell die Überschreibung der `PreCreateWindow`. Programmbedingt diese ableitungen von `PreCreateWindow` nicht dokumentiert sind. Um die Stile, die für jede Klasse und die Abhängigkeiten zwischen der Stile zu ermitteln, können Sie die MFC-Quellcode für die Basisklasse von Ihrer Anwendung überprüfen. Wenn Sie außer Kraft setzen möchten `PreCreateWindow`, können Sie bestimmen, ob der Stile, die in Ihrer Anwendung Basisklasse verwendet die Funktionalität bereitstellen, Sie mithilfe der Informationen aus den MFC-Quellcode müssen.  
  
 Weitere Informationen zum Ändern von Window-Stile finden Sie unter den [Ändern der Stile eines mit MFC erstellten Fenster](../../mfc/changing-the-styles-of-a-window-created-by-mfc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [CView-Klasse](../../mfc/reference/cview-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CTreeView-Klasse](../../mfc/reference/ctreeview-class.md)   
 [CListView-Klasse](../../mfc/reference/clistview-class.md)   
 [CRichEditView-Klasse](../../mfc/reference/cricheditview-class.md)
