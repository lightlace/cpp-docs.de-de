---
title: Klasse CMFCColorPopupMenu | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::CreateTearOffBar
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::GetMenuBar
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::SetPropList
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorPopupMenu class
ms.assetid: 0bf9efe8-aed5-4ab7-b23b-eb284b4668be
caps.latest.revision: 19
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
ms.openlocfilehash: 14076d78eaf86ef01e68656685dd2fd102d96311
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccolorpopupmenu-class"></a>CMFCColorPopupMenu-Klasse
Stellt ein Popup-Menü, mit denen Benutzer wählen Sie Farben in einem Dokument oder einer Anwendung dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCColorPopupMenu : public CMFCPopupMenu  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CMFCColorPopupMenu::CMFCColorPopupMenu](#cmfccolorpopupmenu)|Erstellt ein `CMFCColorPopupMenu`-Objekt.|  
|`CMFCColorPopupMenu::~CMFCColorPopupMenu`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CMFCColorPopupMenu::CreateTearOffBar](#createtearoffbar)|Erstellt eine andockbare Farbleiste abtrennbare. (Überschreibt [CMFCPopupMenu::CreateTearOffBar](../../mfc/reference/cmfcpopupmenu-class.md#createtearoffbar).)|  
|[CMFCColorPopupMenu::GetMenuBar](#getmenubar)|Gibt die [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) , in dem Popupmenü eingebettet ist. (Überschreibt [CMFCPopupMenu::GetMenuBar](../../mfc/reference/cmfcpopupmenu-class.md#getmenubar).)|  
|`CMFCColorPopupMenu::GetThisClass`|Vom Framework verwendet werden, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das Klassentyp zugeordnet ist.|  
|[CMFCColorPopupMenu::SetPropList](#setproplist)|Legt die Eigenschaft Raster-Steuerelementobjekt der eingebetteten `CMFCColorBar` Objekt.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|Name|Beschreibung|  
|`m_bEnabledInCustomizeMode`|Ein boolescher Wert, der bestimmt, ob der Farbleiste angezeigt.|  
|`m_wndColorBar`|Das `CMFCColorBar` Objekt, das die Farbauswahl bereitstellt.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Klasse erbt die Funktionalität im Popupmenü die `CMFCPopupMenu` Klasse und verwaltet ein `CMFCColorBar` Objekt, das die Farbauswahl bereitstellt. Wenn die Symbolleiste Framework ist im Anpassungsmodus und `m_bEnabledInCustomizeMode` Elementgruppe zu `FALSE`, die Farbleiste-Objekt wird nicht angezeigt. Weitere Informationen zu den Anpassungsmodus, finden Sie unter [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)  
  
 Weitere Informationen zu `CMFCColorBar`, finden Sie unter [CMFCColorBar Klasse](../../mfc/reference/cmfccolorbar-class.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)  
  
 [CMFCColorPopupMenu](../../mfc/reference/cmfccolorpopupmenu-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcolorpopupmenu.h  
  
##  <a name="cmfccolorpopupmenu"></a>CMFCColorPopupMenu::CMFCColorPopupMenu  
 Erstellt ein `CMFCColorPopupMenu`-Objekt.  
  
```  
CMFCColorPopupMenu(
    const CArray<COLORREF, COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,  
    int nColumns,  
    int nHorzDockRows,  
    int nVertDockColumns,  
    COLORREF colorAutomatic,  
    UINT uiCommandID,  
    BOOL bStdColorDlg = FALSE);

 
CMFCColorPopupMenu(
    CMFCColorButton* pParentBtn,  
    const CArray<COLORREF, COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,  
    int nColumns,  
    COLORREF colorAutomatic);

 
CMFCColorPopupMenu(
    CMFCRibbonColorButton* pParentBtn,  
    const CArray<COLORREF, COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,  
    int nColumns,  
    COLORREF colorAutomatic,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `colors`  
 Ein Array von Farben, die vom Framework im Popupmenü angezeigt wird.  
  
 [in] `color`  
 Die standardmäßig ausgewählten Farbe.  
  
 [in] `lpszAutoColor`  
 Die Beschriftung für die *automatische* Farbschaltfläche (Standard), oder `NULL`.  
  
 Ist die Bezeichnung für "automatisch" **automatische**.  
  
 [in] `lpszOtherColor`  
 Die Beschriftung für die *andere* Schaltfläche Weitere Farben angezeigt werden, oder `NULL`.  
  
 Die Bezeichnung für die andere Schaltfläche wird **Weitere Farben... **.  
  
 [in] `lpszDocColors`  
 Die Beschriftung der Schaltfläche Farben Dokument. Die Dokument-Farben-Palette Listet alle Farben, die das Dokument zurzeit verwendet.  
  
 [in] `lstDocColors`  
 Eine Liste der Farben, die das Dokument zurzeit verwendet.  
  
 [in] `nColumns`  
 Die Anzahl der Spalten, die das Array von Farben aufweist.  
  
 [in] `nHorzDockRows`  
 Die Anzahl der Zeilen, die die Farbleiste hat, wenn es horizontal angedockt ist.  
  
 [in] `nVertDockColumns`  
 Die Anzahl der Spalten, die auf die Farbleiste hat, wenn es vertikal angedockt ist.  
  
 [in] `colorAutomatic`  
 Die Standardfarbe, die das Framework gilt, wenn Sie auf "Automatische" klicken.  
  
 [in] `uiCommandID`  
 Der Befehl der Farbleiste Control-ID.  
  
 [in] `bStdColorDlg`  
 Ein boolescher Wert, der angibt, ob das Dialogfeld Farbe Standardbetriebssystem anzeigen oder die [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) das Dialogfeld.  
  
 [in] `pParentBtn`  
 Ein Zeiger auf eine übergeordnete-Schaltfläche.  
  
 [in] `nID`  
 Die Befehls-ID.  
  
### <a name="remarks"></a>Hinweise  
 Jede überladene Konstruktor legt die `m_bEnabledInCustomizeMode` Element `FALSE`.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen einer `CMFCColorPopupMenu` Objekt.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#34;](../../mfc/reference/codesnippet/cpp/cmfccolorpopupmenu-class_1.cpp)]  
  
##  <a name="createtearoffbar"></a>CMFCColorPopupMenu::CreateTearOffBar  
 Erstellt eine andockbare Farbleiste abtrennbare.  
  
```  
virtual CPane* CreateTearOffBar(
    CFrameWnd* pWndMain,  
    UINT uiID,  
    LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `pWndMain`|Ein Zeiger auf das übergeordnete Fenster des Balkens abtrennbare.|  
|[in] `uiID`|Die Befehls-ID des Balkens abtrennbare.|  
|[in] `lpszName`|Der Text des Balkens abtrennbare aus.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das neue abtrennbare Steuerelement Bar-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erstellt eine [CMFCColorBar Klasse](../../mfc/reference/cmfccolorbar-class.md) -Objekt und wandelt es zu einer [CPane-Klasse](../../mfc/reference/cpane-class.md) Zeiger. Wandeln Sie diesen Wert an eine [CMFCColorBar Klasse](../../mfc/reference/cmfccolorbar-class.md) Zeiger mithilfe einer Umwandlung Makros in beschriebenen [Typ umwandeln von MFC-Klasse von Objekten](../../mfc/reference/type-casting-of-mfc-class-objects.md).  
  
##  <a name="getmenubar"></a>CMFCColorPopupMenu::GetMenuBar  
 Gibt die [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) , in dem Popupmenü eingebettet ist.  
  
```  
virtual CMFCPopupMenuBar* GetMenuBar();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das eingebettete `CMFCPopupMenuBar`.  
  
### <a name="remarks"></a>Hinweise  
 Das Popupmenü Farbe ist ein eingebetteter [CMFCPopupMenuBar Klasse](../../mfc/reference/cmfcpopupmenubar-class.md) Objekt. Überschreiben Sie diese Methode in einer abgeleiteten Klasse, wenn Ihre Anwendung einen anderen eingebetteten Typ verwendet.  
  
##  <a name="setproplist"></a>CMFCColorPopupMenu::SetPropList  
 Legt die Eigenschaft Raster-Steuerelementobjekt der eingebetteten `CMFCColorBar` Objekt.  
  
```  
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndList`  
 Ein Zeiger auf ein Objekt Grid-Steuerelement.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)

