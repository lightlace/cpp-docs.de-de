---
title: CMFCColorPopupMenu-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: b32317f4fd67a627a272ea8eefcc949d1b0e63c8
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37852993"
---
# <a name="cmfccolorpopupmenu-class"></a>CMFCColorPopupMenu-Klasse
Stellt ein Popup-Menü, das Benutzer verwenden, um die Farben in einem Dokument oder die Anwendung auswählen.  
  
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
|[CMFCColorPopupMenu::CreateTearOffBar](#createtearoffbar)|Erstellt eine andockbare abtrennbare-Farbleiste an. (Überschreibt [CMFCPopupMenu::CreateTearOffBar](../../mfc/reference/cmfcpopupmenu-class.md#createtearoffbar).)|  
|[CMFCColorPopupMenu::GetMenuBar](#getmenubar)|Gibt die [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) , in dem Popupmenü eingebettet ist. (Überschreibt [CMFCPopupMenu::GetMenuBar](../../mfc/reference/cmfcpopupmenu-class.md#getmenubar).)|  
|`CMFCColorPopupMenu::GetThisClass`|Durch das Framework verwendet wird, einen Zeiger zum Abrufen der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|[CMFCColorPopupMenu::SetPropList](#setproplist)|Legt das Grid-Steuerelement-Eigenschaftenobjekt der eingebetteten `CMFCColorBar` Objekt.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|name|Beschreibung|  
|`m_bEnabledInCustomizeMode`|Ein boolescher Wert, der bestimmt, ob der Farbleiste angezeigt.|  
|`m_wndColorBar`|Die `CMFCColorBar` Objekt, das die Farbauswahl bereitstellt.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Klasse erbt die Funktionalität im Popupmenü die `CMFCPopupMenu` Klasse und verwaltet eine `CMFCColorBar` Objekt, das die Farbauswahl bereitstellt. Wenn die Symbolleiste Framework ist im Anpassungsmodus und `m_bEnabledInCustomizeMode` Member auf "false" festgelegt ist, die Farbleiste-Objekt wird nicht angezeigt. Weitere Informationen zu den Anpassungsmodus, finden Sie unter [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)  
  
 Weitere Informationen zu `CMFCColorBar`, finden Sie unter [CMFCColorBar-Klasse](../../mfc/reference/cmfccolorbar-class.md).  
  
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
 Ein Array von Farben, die das Framework auf dem Popup-Menü angezeigt werden soll.  
  
 [in] *Farbe*  
 Die standardmäßig ausgewählten Farbe.  
  
 [in] *LpszAutoColor*  
 Die textbezeichnung des der *automatische* farbenschaltfläche (Standard), oder NULL.  
  
 Die standardmäßige Bezeichnung für die automatische Schaltfläche ist **automatische**.  
  
 [in] *LpszOtherColor*  
 Die textbezeichnung des der *andere* Schaltfläche, welche zeigt weitere Farben, oder NULL.  
  
 Die standardmäßige Bezeichnung für die andere Schaltfläche ist **Weitere Farben...** .  
  
 [in] *LpszDocColors*  
 Die Beschriftung der Schaltfläche Dokument Farben. Die Farben (Palette) Dokument Listet alle Farben, die das Dokument derzeit verwendet.  
  
 [in] *LstDocColors*  
 Eine Liste von Farben, die das Dokument derzeit verwendet werden soll.  
  
 [in] *nColumns*  
 Die Anzahl der Spalten, die das Array von Farben aufweist.  
  
 [in] *nHorzDockRows*  
 Die Anzahl der Zeilen, die über der Farbleiste verfügt, wenn er horizontal angedockt ist.  
  
 [in] *nVertDockColumns*  
 Die Anzahl der Spalten, die der Farbleiste hat, wenn sie vertikal angedockt wird.  
  
 [in] *ColorAutomatic*  
 Die Standardfarbe, die das Framework gilt, wenn Sie die automatische Schaltfläche klicken.  
  
 [in] *UiCommandID*  
 Der Befehl der Farbleiste-Control-ID.  
  
 [in] *bStdColorDlg*  
 Ein boolescher Wert, der angibt, ob das Dialogfeld Farbe standardsystembenachrichtigung angezeigt oder [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) Dialogfeld.  
  
 [in] *pParentBtn*  
 Ein Zeiger auf eine Schaltfläche "übergeordneten".  
  
 [in] *nID*  
 Die Befehls-ID.  
  
### <a name="remarks"></a>Hinweise  
 Jede überladene Konstruktor legt die `m_bEnabledInCustomizeMode` Member auf "false".  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen einer `CMFCColorPopupMenu` Objekt.  
  
 [!code-cpp[NVC_MFC_RibbonApp#34](../../mfc/reference/codesnippet/cpp/cmfccolorpopupmenu-class_1.cpp)]  
  
##  <a name="createtearoffbar"></a>  CMFCColorPopupMenu::CreateTearOffBar  
 Erstellt eine andockbare abtrennbare-Farbleiste an.  
  
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
|[in] *pWndMain*|Zeiger auf das übergeordnete Fenster der abtrennbarer Leiste.|  
|[in] *UiID*|Die Befehls-ID der abtrennbarer Leiste.|  
|[in] *Wert*|Der Fenstertext im der abtrennbarer Leiste.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die neue abtrennbare Steuerleistenobjekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erstellt eine [CMFCColorBar-Klasse](../../mfc/reference/cmfccolorbar-class.md) -Objekt und wandelt es zu einem [CPane-Klasse](../../mfc/reference/cpane-class.md) Zeiger. Sie können diesen Wert umwandeln an eine [CMFCColorBar-Klasse](../../mfc/reference/cmfccolorbar-class.md) Zeiger mit einem der die Umwandlung-Makros in [Typ umwandeln von MFC-Klasse von Objekten](../../mfc/reference/type-casting-of-mfc-class-objects.md).  
  
##  <a name="getmenubar"></a>  CMFCColorPopupMenu::GetMenuBar  
 Gibt die [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) , in dem Popupmenü eingebettet ist.  
  
```  
virtual CMFCPopupMenuBar* GetMenuBar();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die eingebettete `CMFCPopupMenuBar`.  
  
### <a name="remarks"></a>Hinweise  
 Im Popupmenü "Farbe" verfügt über ein eingebettetes [CMFCPopupMenuBar-Klasse](../../mfc/reference/cmfcpopupmenubar-class.md) Objekt. Überschreiben Sie diese Methode in einer abgeleiteten Klasse an, wenn Ihre Anwendung einen anderen eingebetteten Typ verwendet.  
  
##  <a name="setproplist"></a>  CMFCColorPopupMenu::SetPropList  
 Legt das Grid-Steuerelement-Eigenschaftenobjekt der eingebetteten `CMFCColorBar` Objekt.  
  
```  
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pWndList*  
 Zeiger auf ein Eigenschaftenobjekt der Grid-Steuerelement.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)
