---
title: Klasse CCtrlView | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCtrlView
dev_langs:
- C++
helpviewer_keywords:
- views, and common controls
- controls [MFC], common
- CCtrlView class
ms.assetid: ff488596-1e71-451f-8fec-b0831a7b44e0
caps.latest.revision: 20
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 569044de59dc3ccd73157abc86855beef57cb558
ms.lasthandoff: 02/24/2017

---
# <a name="cctrlview-class"></a>CCtrlView-Klasse
Passt die Dokument-/Ansichtarchitektur den allgemeinen Steuerelemente an, die von Windows 98 und Windows NT-Versionen 3,51 (und höher) unterstützt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CCtrlView : public CView  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCtrlView::CCtrlView](#cctrlview)|Erstellt ein `CCtrlView`-Objekt.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCtrlView::OnDraw](#ondraw)|Aufgerufen, um mit den angegebenen Gerätekontext zu zeichnen.|  
|[CCtrlView::PreCreateWindow](#precreatewindow)|Wird vor der Erstellung des an diesem `CCtrlView`-Objekt angefügten Windows-Fensters aufgerufen.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CCtrlView::m_dwDefaultStyle](#m_dwdefaultstyle)|Enthält das Standardformat für die Ansichtsklasse.|  
|[CCtrlView::m_strClass](#m_strclass)|Enthält den Namen des Windows-Klasse für die Ansichtsklasse.|  
  
## <a name="remarks"></a>Hinweise  
 Die Klasse `CCtrlView` und seine abgeleiteten [CEditView](../../mfc/reference/ceditview-class.md), [CListView](../../mfc/reference/clistview-class.md), [CTreeView](../../mfc/reference/ctreeview-class.md), und [CRichEditView](../../mfc/reference/cricheditview-class.md), Anpassen der Dokument-/ Ansichtarchitektur auf die neuen allgemeinen Steuerelemente von Windows 95/98 und Windows NT, Version 3.51 und höher unterstützt. Weitere Informationen zu den Dokument-/ Ansichtarchitektur, finden Sie unter [Dokument-/Ansichtarchitektur](../../mfc/document-view-architecture.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 `CCtrlView`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="a-namecctrlviewa--cctrlviewcctrlview"></a><a name="cctrlview"></a>CCtrlView::CCtrlView  
 Erstellt ein `CCtrlView`-Objekt.  
  
```  
CCtrlView(
    LPCTSTR lpszClass,  
    DWORD dwStyle);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszClass`  
 Windows-Klassennamen der Ansichtsklasse.  
  
 `dwStyle`  
 Die Art des View-Klasse.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft der Konstruktor auf, wenn ein neues Rahmenfenster erstellt wird, oder Teilen Sie ein Fenster ist. Überschreiben Sie [CView:: OnInitialUpdate](../../mfc/reference/cview-class.md#oninitialupdate) um die Ansicht zu initialisieren, nachdem das Dokument zugeordnet ist. Rufen Sie [CWnd:: Create](../../mfc/reference/cwnd-class.md#create) oder [CWnd::CreateEx](../../mfc/reference/cwnd-class.md#createex) zum Erstellen des Windows-Objekts.  
  
##  <a name="a-namemstrclassa--cctrlviewmstrclass"></a><a name="m_strclass"></a>CCtrlView::m_strClass  
 Enthält den Namen des Windows-Klasse für die Ansichtsklasse.  
  
```  
CString m_strClass;  
```  
  
##  <a name="a-namemdwdefaultstylea--cctrlviewmdwdefaultstyle"></a><a name="m_dwdefaultstyle"></a>CCtrlView::m_dwDefaultStyle  
 Enthält das Standardformat für die Ansichtsklasse.  
  
```  
DWORD m_dwDefaultStyle;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieses Format wird angewendet, wenn ein Fenster erstellt wird.  
  
##  <a name="a-nameondrawa--cctrlviewondraw"></a><a name="ondraw"></a>CCtrlView::OnDraw  
 Aufgerufen, um den Inhalt der Zeichnen die `CCtrlView` -Objekt mit den angegebenen Gerätekontext.  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Ein Zeiger auf den Gerätekontext, der in dem Zeichnung auftritt.  
  
### <a name="remarks"></a>Hinweise  
 `OnDraw`wird normalerweise aufgerufen, für die Bildschirmanzeige, übergeben einen Bildschirm-Gerätekontext, der durch angegebenen `pDC`.  
  
##  <a name="a-nameprecreatewindowa--cctrlviewprecreatewindow"></a><a name="precreatewindow"></a>CCtrlView::PreCreateWindow  
 Wird vor der Erstellung des an diesem `CWnd`-Objekt angefügten Windows-Fensters aufgerufen.  
  
```  
virtual BOOL PreCreateWindow(CREATESTRUCT& cs);
```  
  
### <a name="parameters"></a>Parameter  
 *cs*  
 Ein [CREATESTRUCT](http://msdn.microsoft.com/library/windows/desktop/ms632603) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Fenster erstellen fortgesetzt werden soll; 0, um Fehler beim Erstellen des anzugeben.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird nie direkt aufrufen.  
  
 Die standardmäßige Implementierung dieser Funktion sucht nach einem **NULL** Fensterklassennamen und einen geeigneten Standardwert ersetzt. Überschreiben Sie diese Memberfunktion zum Ändern der `CREATESTRUCT` -Struktur vor dem Erstellen des Fensters.  
  
 Jede Klasse abgeleitet `CCtrlView` eigene funktionell der Überschreibung von `PreCreateWindow`. Standardmäßig ist dieser Ableitung von `PreCreateWindow` nicht dokumentiert sind. Um die Stile, die für jede Klasse und die Wechselbeziehungen zwischen Stile zu ermitteln, können Sie die MFC-Quellcode für die Basisklasse für die Anwendung überprüfen. Wenn Sie überschreiben `PreCreateWindow`, können Sie bestimmen, ob die Stile in der Basisklasse für die Anwendung verwendet die Funktionalität bereitstellen, Sie mithilfe der Informationen aus den MFC-Quellcode müssen.  
  
 Weitere Informationen zum Ändern von Fensterstilen, finden Sie unter der [Ändern der Stile eines mit MFC erstellten Fensters](../../mfc/changing-the-styles-of-a-window-created-by-mfc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [CView-Klasse](../../mfc/reference/cview-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CTreeView-Klasse](../../mfc/reference/ctreeview-class.md)   
 [CListView-Klasse](../../mfc/reference/clistview-class.md)   
 [CRichEditView-Klasse](../../mfc/reference/cricheditview-class.md)

