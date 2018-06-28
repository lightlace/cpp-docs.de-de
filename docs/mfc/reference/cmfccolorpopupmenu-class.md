---
title: CMFCColorPopupMenu Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CMFCColorPopupMenu [MFC], CMFCColorPopupMenu
- CMFCColorPopupMenu [MFC], CreateTearOffBar
- CMFCColorPopupMenu [MFC], GetMenuBar
- CMFCColorPopupMenu [MFC], SetPropList
ms.assetid: 0bf9efe8-aed5-4ab7-b23b-eb284b4668be
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 54999252af2ec55c67e1afc69c2788f96cfc640e
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37037303"
---
# <a name="cmfccolorpopupmenu-class"></a>CMFCColorPopupMenu-Klasse
Stellt ein Popupmenü aufrufen, die Benutzer verwenden, um Farben auszuwählen, in einem Dokument oder einer Anwendung dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCColorPopupMenu : public CMFCPopupMenu  
```  
  
## <a name="members"></a>Member  
  
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
|[CMFCColorPopupMenu::CreateTearOffBar](#createtearoffbar)|Erstellt eine andockbare Farbleiste abtrennbare an. (Überschreibt [CMFCPopupMenu::CreateTearOffBar](../../mfc/reference/cmfcpopupmenu-class.md#createtearoffbar).)|  
|[CMFCColorPopupMenu::GetMenuBar](#getmenubar)|Gibt die [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) , die im Menü Popupmenü eingebettet ist. (Überschreibt [CMFCPopupMenu::GetMenuBar](../../mfc/reference/cmfcpopupmenu-class.md#getmenubar).)|  
|`CMFCColorPopupMenu::GetThisClass`|Durch das Framework verwendet wird, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|[CMFCColorPopupMenu::SetPropList](#setproplist)|Legt die Eigenschaft Raster-Steuerelementobjekt der eingebetteten `CMFCColorBar` Objekt.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|name|Beschreibung|  
|`m_bEnabledInCustomizeMode`|Ein boolescher Wert, der bestimmt, ob der Farbleiste angezeigt.|  
|`m_wndColorBar`|Die `CMFCColorBar` Objekt, das die Farbauswahl bereitstellt.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Klasse erbt die Popupmenü-Funktionalität von der `CMFCPopupMenu` Klasse und verwaltet eine `CMFCColorBar` Objekt, das die Farbauswahl bereitstellt. Wenn die Symbolleiste-Framework ist im Anpassungsmodus und `m_bEnabledInCustomizeMode` Elementgruppe zu `FALSE`, die Farbleiste-Objekt wird nicht angezeigt. Weitere Informationen zu Anpassungsmodus, finden Sie unter [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)  
  
 Weitere Informationen zu `CMFCColorBar`, finden Sie unter [CMFCColorBar Klasse](../../mfc/reference/cmfccolorbar-class.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)  
  
 [CMFCColorPopupMenu](../../mfc/reference/cmfccolorpopupmenu-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcolorpopupmenu.h  
  
##  <a name="cmfccolorpopupmenu"></a>  CMFCColorPopupMenu::CMFCColorPopupMenu  
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
 [in] *Farben*  
 Ein Array von Farben aus, denen vom Framework im Popupmenü angezeigt wird.  
  
 [in] *Farbe*  
 Die standardmäßig ausgewählten Farbe.  
  
 [in] *LpszAutoColor*  
 Die Beschriftung für die *automatische* farbenschaltfläche (Standard), oder `NULL`.  
  
 Die standardmäßige Bezeichnung für die Schaltfläche "automatisch" ist **automatische**.  
  
 [in] *LpszOtherColor*  
 Die Beschriftung für die *andere* Schaltfläche, die weitere Farben angezeigt wird, oder `NULL`.  
  
 Der standard als Bezeichnung für die Schaltfläche "Sonstige" **Weitere Farben...** .  
  
 [in] *LpszDocColors*  
 Die Beschriftung der Schaltfläche Dokument Farben. Die Dokument-Farben-Palette Listet alle Farben, die das Dokument derzeit verwendet.  
  
 [in] *LstDocColors*  
 Eine Liste von Farben, die das Dokument derzeit verwendet.  
  
 [in] *nColumns*  
 Die Anzahl der Spalten, die das Array von Farben aufweist.  
  
 [in] *nHorzDockRows*  
 Die Anzahl der Zeilen, die die Farbleiste hat, wenn er horizontal angedockt ist.  
  
 [in] *nVertDockColumns*  
 Die Anzahl der Spalten, die die Farbleiste hat, wenn es vertikal angedockt ist.  
  
 [in] *ColorAutomatic*  
 Die Standardfarbe, die das Framework gilt, wenn Sie auf die Schaltfläche "Automatische" klicken.  
  
 [in] *UiCommandID*  
 Die Farbleiste steuerungsbefehls-ID.  
  
 [in] *bStdColorDlg*  
 Ein boolescher Wert, der angibt, ob das Dialogfeld Farbe Standardbetriebssystem angezeigt oder [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) (Dialogfeld).  
  
 [in] *pParentBtn*  
 Ein Zeiger auf eine übergeordnete Schaltfläche.  
  
 [in] *nID*  
 Die Befehls-ID.  
  
### <a name="remarks"></a>Hinweise  
 Jede überladenen Konstruktor legt die `m_bEnabledInCustomizeMode` Element `FALSE`.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen einer `CMFCColorPopupMenu` Objekt.  
  
 [!code-cpp[NVC_MFC_RibbonApp#34](../../mfc/reference/codesnippet/cpp/cmfccolorpopupmenu-class_1.cpp)]  
  
##  <a name="createtearoffbar"></a>  CMFCColorPopupMenu::CreateTearOffBar  
 Erstellt eine andockbare Farbleiste abtrennbare an.  
  
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
|[in] *pWndMain*|Ein Zeiger auf das übergeordnete Fenster eines abtrennbarer Leiste.|  
|[in] *UiID*|Die Befehls-ID des abtrennbarer Leiste.|  
|[in] *Wert*|Der Text der abtrennbarer Leiste aus.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die neue abtrennbare Steuerleistenobjekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erstellt eine [CMFCColorBar Klasse](../../mfc/reference/cmfccolorbar-class.md) -Objekt und wandelt es zu einer [CPane-Klasse](../../mfc/reference/cpane-class.md) Zeiger. Wandeln Sie diesen Wert an eine [CMFCColorBar-Klasse](../../mfc/reference/cmfccolorbar-class.md) Zeiger mithilfe einer Umwandlung-Makros, die in beschriebenen [Typ-Typumwandlung von MFC-Klassenobjekten](../../mfc/reference/type-casting-of-mfc-class-objects.md).  
  
##  <a name="getmenubar"></a>  CMFCColorPopupMenu::GetMenuBar  
 Gibt die [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) , die im Menü Popupmenü eingebettet ist.  
  
```  
virtual CMFCPopupMenuBar* GetMenuBar();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den eingebetteten `CMFCPopupMenuBar`.  
  
### <a name="remarks"></a>Hinweise  
 Das Popupmenü Farbe ist ein eingebetteter [CMFCPopupMenuBar-Klasse](../../mfc/reference/cmfcpopupmenubar-class.md) Objekt. Überschreiben Sie diese Methode in einer abgeleiteten Klasse, wenn Ihre Anwendung einen anderen eingebetteten Typ verwendet.  
  
##  <a name="setproplist"></a>  CMFCColorPopupMenu::SetPropList  
 Legt die Eigenschaft Raster-Steuerelementobjekt der eingebetteten `CMFCColorBar` Objekt.  
  
```  
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pWndList*  
 Ein Zeiger auf ein Eigenschaftenobjekt der Grid-Steuerelement.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)
