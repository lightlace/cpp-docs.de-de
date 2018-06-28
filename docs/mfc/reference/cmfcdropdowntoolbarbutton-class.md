---
title: CMFCDropDownToolbarButton Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::CMFCDropDownToolbarButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::CopyFrom
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::DropDownToolbar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::ExportToMenuButton
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::GetDropDownToolBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::IsDropDown
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::IsExtraSize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnCalculateSize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnChangeParentWnd
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnClick
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnClickUp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnContextHelp
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnCustomizeMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnDraw
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::OnDrawOnCustomizeList
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::Serialize
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::SetDefaultCommand
- AFXDROPDOWNTOOLBAR/CMFCDropDownToolbarButton::m_uiShowBarDelay
dev_langs:
- C++
helpviewer_keywords:
- CMFCDropDownToolbarButton [MFC], CMFCDropDownToolbarButton
- CMFCDropDownToolbarButton [MFC], CopyFrom
- CMFCDropDownToolbarButton [MFC], DropDownToolbar
- CMFCDropDownToolbarButton [MFC], ExportToMenuButton
- CMFCDropDownToolbarButton [MFC], GetDropDownToolBar
- CMFCDropDownToolbarButton [MFC], IsDropDown
- CMFCDropDownToolbarButton [MFC], IsExtraSize
- CMFCDropDownToolbarButton [MFC], OnCalculateSize
- CMFCDropDownToolbarButton [MFC], OnChangeParentWnd
- CMFCDropDownToolbarButton [MFC], OnClick
- CMFCDropDownToolbarButton [MFC], OnClickUp
- CMFCDropDownToolbarButton [MFC], OnContextHelp
- CMFCDropDownToolbarButton [MFC], OnCustomizeMenu
- CMFCDropDownToolbarButton [MFC], OnDraw
- CMFCDropDownToolbarButton [MFC], OnDrawOnCustomizeList
- CMFCDropDownToolbarButton [MFC], Serialize
- CMFCDropDownToolbarButton [MFC], SetDefaultCommand
- CMFCDropDownToolbarButton [MFC], m_uiShowBarDelay
ms.assetid: bc9d69e6-bd3e-4c15-9368-e80a504a0ba7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5c894ff57bbbee59842f56dbfef0ec06a6c7899f
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37041694"
---
# <a name="cmfcdropdowntoolbarbutton-class"></a>CMFCDropDownToolbarButton-Klasse
Ein Symbolleisten-Schaltflächentyp, der sich wie eine normale Schaltfläche verhält, wenn darauf geklickt wird. Allerdings eine Dropdown-Symbolleiste Eröffnung ( [CMFCDropDownToolBar Klasse](../../mfc/reference/cmfcdropdowntoolbar-class.md) Wenn der Benutzer die Symbolleisten-Schaltfläche gedrückt hält.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCDropDownToolbarButton : public CMFCToolBarButton  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](#cmfcdropdowntoolbarbutton)|Erstellt ein `CMFCDropDownToolbarButton`-Objekt.|  
|`CMFCDropDownToolbarButton::~CMFCDropDownToolbarButton`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCDropDownToolbarButton::CopyFrom](#copyfrom)|Kopiert die Eigenschaften von einer anderen Symbolleistenschaltfläche auf die Schaltfläche mit den aktuellen. (Überschreibt [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|  
|`CMFCDropDownToolbarButton::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar)|Öffnet eine Dropdown-Symbolleiste.|  
|[CMFCDropDownToolbarButton::ExportToMenuButton](#exporttomenubutton)|Kopiert den Text aus der Symbolleiste auf die Schaltfläche zu einem Menü. (Überschreibt [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton).)|  
|[CMFCDropDownToolbarButton::GetDropDownToolBar](#getdropdowntoolbar)|Ruft ab den Dropdown-Symbolleiste, die die Schaltfläche zugeordnet ist.|  
|`CMFCDropDownToolbarButton::GetThisClass`|Durch das Framework verwendet wird, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|[CMFCDropDownToolbarButton::IsDropDown](#isdropdown)|Bestimmt, ob die Dropdown-Symbolleiste derzeit geöffnet ist.|  
|[CMFCDropDownToolbarButton::IsExtraSize](#isextrasize)|Bestimmt, ob die Schaltfläche mit einem erweiterten Rahmen angezeigt werden kann. (Überschreibt [CMFCToolBarButton::IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize).)|  
|[CMFCDropDownToolbarButton::OnCalculateSize](#oncalculatesize)|Wird aufgerufen, durch das Framework die Größe der Schaltfläche für den angegebenen Gerätekontext und andockzustand berechnet. (Überschreibt [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|  
|`CMFCDropDownToolbarButton::OnCancelMode`|Wird aufgerufen, durch das Framework behandelt die [WM_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615) Nachricht. (Überschreibt `CMCToolBarButton::OnCancelMode`.)|  
|[CMFCDropDownToolbarButton::OnChangeParentWnd](#onchangeparentwnd)|Vom Framework aufgerufen, wenn die Schaltfläche "" in eine neue Symbolleiste eingefügt wird. (Überschreibt [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|  
|[CMFCDropDownToolbarButton::OnClick](#onclick)|Wird vom Framework aufgerufen, klickt der Benutzer die Maustaste los. (Überschreibt [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|  
|[CMFCDropDownToolbarButton::OnClickUp](#onclickup)|Vom Framework aufgerufen, wenn der Benutzer die Maustaste loslässt. (Überschreibt [CMFCToolBarButton::OnClickUp](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup).)|  
|[CMFCDropDownToolbarButton::OnContextHelp](#oncontexthelp)|Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste verarbeitet eine `WM_HELPHITTEST` Nachricht. (Überschreibt [CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp).)|  
|[CMFCDropDownToolbarButton::OnCustomizeMenu](#oncustomizemenu)|Das angegebene Menü ändert, wenn die Anwendung auf der übergeordneten Symbolleiste ein Kontextmenü angezeigt. (Überschreibt [CMFCToolBarButton::OnCustomizeMenu](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu).)|  
|[CMFCDropDownToolbarButton::OnDraw](#ondraw)|Wird aufgerufen, durch das Framework der Schaltfläche gezeichnet werden soll, mithilfe des angegebenen Stile und Optionen. (Überschreibt [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|  
|[CMFCDropDownToolbarButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|Wird aufgerufen, durch das Framework der Schaltfläche gezeichnet werden soll, der **Befehle** im Bereich der **anpassen** (Dialogfeld). (Überschreibt [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|  
|[CMFCDropDownToolbarButton::Serialize](#serialize)|Dieses Objekt aus einem Archiv liest oder schreibt sie in ein Archiv. (Überschreibt [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|  
|[CMFCDropDownToolbarButton::SetDefaultCommand](#setdefaultcommand)|Legt den Standardbefehl, den das Framework verwendet, wenn ein Benutzer die Schaltfläche klickt.|  
  
### <a name="data-members"></a>Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CMFCDropDownToolbarButton::m_uiShowBarDelay](#m_uishowbardelay)|Gibt die Zeitdauer, die ein Benutzer die Maustaste gedrückt halten muss, bevor die Dropdown-Symbolleiste angezeigt wird.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `CMFCDropDownToolBarButton` eine normale Schaltfläche unterscheidet sich insofern, dass es einen kleinen Pfeil in der unteren rechten Ecke der Schaltfläche hat. Nachdem der Benutzer aus der Dropdown-Symbolleiste eine Schaltfläche auswählt, zeigt das Framework das Symbol auf der obersten Ebene Symbolleisten-Schaltfläche (die Schaltfläche mit den kleinen Pfeil in der unteren rechten Ecke).  
  
 Weitere Informationen dazu, wie eine Dropdown-Symbolleiste implementieren, finden Sie unter [CMFCDropDownToolBar Klasse](../../mfc/reference/cmfcdropdowntoolbar-class.md).  
  
 Die `CMFCDropDownToolBarButton` Objekt exportiert werden kann, auf eine [CMFCToolBarMenuButton Klasse](../../mfc/reference/cmfctoolbarmenubutton-class.md) -Objekt und als eine Menüschaltfläche mit einem Popupmenü angezeigt.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdropdowntoolbar.h  
  
##  <a name="copyfrom"></a>  CMFCDropDownToolbarButton::CopyFrom  
 Kopiert die Eigenschaften von einer anderen Symbolleistenschaltfläche auf die Schaltfläche mit den aktuellen.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *Src*  
 Ein Verweis auf die Schaltfläche "Quelle" aus dem kopiert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Kopieren von einer anderen Symbolleistenschaltfläche diese Symbolleisten-Schaltfläche. *Src* muss vom Typ `CMFCDropDownToolbarButton`.  
  
##  <a name="cmfcdropdowntoolbarbutton"></a>  CMFCDropDownToolbarButton::CMFCDropDownToolbarButton  
 Erstellt ein `CMFCDropDownToolbarButton`-Objekt.  
  
```  
CMFCDropDownToolbarButton();

 
CMFCDropDownToolbarButton(
    LPCTSTR lpszName,  
    CMFCDropDownToolBar* pToolBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *Wert*  
 Der Standardtext der Schaltfläche.  
  
 [in] *pToolBar*  
 Ein Zeiger auf die `CMFCDropDownToolBar` -Objekt, das angezeigt wird, wenn der Benutzer die Schaltfläche drückt.  
  
### <a name="remarks"></a>Hinweise  
 Die zweite Überladung des Konstruktors kopiert der Dropdown-Schaltfläche für die erste Schaltfläche auf der Symbolleiste, *pToolBar* angibt.  
  
 In der Regel verwendet eine Dropdown-Symbolleisten-Schaltfläche den Text in der zuletzt verwendeten Schaltfläche auf der Symbolleiste, *pToolBar* angibt. Er verwendet den angegebenen Text *Wert* Wenn die Schaltfläche mit der in einer Menüschaltfläche konvertiert wird, oder wird angezeigt, der **Befehle** auf der Registerkarte die **anpassen** (Dialogfeld). Weitere Informationen zu den **anpassen** (Dialogfeld), finden Sie unter [CMFCToolBarsCustomizeDialog Klasse](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen von ein Objekt von der `CMFCDropDownToolbarButton` Klasse. Dieser Codeausschnitt ist Teil der [Visual Studio-Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#31](../../mfc/codesnippet/cpp/cmfcdropdowntoolbarbutton-class_1.cpp)]  
  
##  <a name="dropdowntoolbar"></a>  CMFCDropDownToolbarButton::DropDownToolbar  
 Öffnet eine Dropdown-Symbolleiste.  
  
```  
BOOL DropDownToolbar(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pWnd*  
 Das übergeordnete Fenster des Frames Dropdownelement oder `NULL` mithilfe des übergeordneten Fensters der Dropdown-Symbolleisten-Schaltfläche.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Methode erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die [CMFCDropDownToolbarButton::OnClick](#onclick) Methode ruft diese Methode, um die Dropdown-Symbolleiste zu öffnen, wenn der Benutzer drückt und wieder die Symbolleisten-Schaltfläche gedrückt hält.  
  
 Diese Methoden erstellt die Dropdown-Symbolleiste mit der [CMFCDropDownFrame::Create](../../mfc/reference/cmfcdropdownframe-class.md#create) Methode. Wenn die übergeordneten Symbolleiste vertikal angedockt wird, positioniert diese Methode der Dropdown-Symbolleiste entweder auf der linken oder rechten Seite der übergeordneten Symbolleiste, je nach dem anpassen. Diese Methode positioniert, andernfalls die Dropdown-Symbolleiste unterhalb der übergeordneten Symbolleiste.  
  
 Diese Methode schlägt fehl, wenn *pWnd* ist `NULL` und die Dropdown-Symbolleisten-Schaltfläche verfügt nicht über ein übergeordnetes Fenster.  
  
##  <a name="exporttomenubutton"></a>  CMFCDropDownToolbarButton::ExportToMenuButton  
 Kopiert den Text aus der Symbolleiste auf die Schaltfläche zu einem Menü.  
  
```  
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] *MenuButton*  
 Ein Verweis auf die Menüschaltfläche Ziel.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert ungleich 0 (null), wenn die Methode erfolgreich ausgeführt wird, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft die basisklassenimplementierung ( [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)) und fügt dann an die Ziel-Menüschaltfläche ein Popupmenü aufrufen, die jede Symbolleiste Menüelement in diese Schaltfläche enthält. Diese Methode fügt keinen Untermenüs zum Menü Popupmenü.  
  
 Diese Methode schlägt fehl, wenn der übergeordneten Symbolleiste `m_pToolBar`, ist `NULL` oder Implementierung der Basisklasse gibt `FALSE`.  
  
##  <a name="getdropdowntoolbar"></a>  CMFCDropDownToolbarButton::GetDropDownToolBar  
 Ruft ab den Dropdown-Symbolleiste, die die Schaltfläche zugeordnet ist.  
  
```  
CMFCToolBar* GetDropDownToolBar() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Dropdown-Symbolleiste, die die Schaltfläche zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt die `m_pToolBar` -Datenmember.  
  
##  <a name="isdropdown"></a>  CMFCDropDownToolbarButton::IsDropDown  
 Bestimmt, ob die Dropdown-Symbolleiste derzeit geöffnet ist.  
  
```  
BOOL IsDropDown() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Dropdown-Symbolleiste derzeit geöffnet ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework öffnet die Dropdown-Symbolleiste mithilfe der [CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar) Methode. Das Framework schließt die Dropdown-Symbolleiste aus, wenn der Benutzer die linke Maustaste drückt, die in den nicht-Clientbereich der Dropdown-Symbolleiste.  
  
##  <a name="isextrasize"></a>  CMFCDropDownToolbarButton::IsExtraSize  
 Bestimmt, ob die Schaltfläche mit einem erweiterten Rahmen angezeigt werden kann.  
  
```  
virtual BOOL IsExtraSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Symbolleisten-Schaltfläche mit einem erweiterten Rahmen angezeigt werden kann; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu erweiterten Rahmen, finden Sie unter [CMFCToolBarButton::IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize).  
  
##  <a name="m_uishowbardelay"></a>  CMFCDropDownToolbarButton::m_uiShowBarDelay  
 Gibt die Zeitdauer, die ein Benutzer die Maustaste gedrückt halten muss, bevor die Dropdown-Symbolleiste angezeigt wird.  
  
```  
static UINT m_uiShowBarDelay;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Verzögerung wird in Millisekunden gemessen. Der Standardwert ist 500. Sie können einen anderen Verzögerung durch Ändern des Werts dieses Elements freigegebene festlegen.  
  
##  <a name="oncalculatesize"></a>  CMFCDropDownToolbarButton::OnCalculateSize  
 Wird aufgerufen, durch das Framework die Größe der Schaltfläche für den angegebenen Gerätekontext und andockzustand berechnet.  
  
```  
virtual SIZE OnCalculateSize(
    CDC* pDC,  
    const CSize& sizeDefault,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDC*  
 Der Gerätekontext, in dem die Schaltfläche angezeigt.  
  
 [in] *SizeDefault*  
 Die Standardgröße der Schaltfläche.  
  
 [in] *bHorz*  
 Der Status der Andocken der übergeordneten Symbolleiste. Dieser Parameter ist `TRUE` , wenn die Symbolleiste horizontal angedockt oder unverankert ist, oder `FALSE` , wenn die Symbolleiste vertikal angedockt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `SIZE` -Struktur, die die Dimensionen der Schaltfläche in Pixel enthält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize)) durch die Breite des den Dropdown Pfeil auf die horizontale Abmessung die Größe der Schaltfläche hinzufügen.  
  
##  <a name="onchangeparentwnd"></a>  CMFCDropDownToolbarButton::OnChangeParentWnd  
 Vom Framework aufgerufen, wenn die Schaltfläche "" in eine neue Symbolleiste eingefügt wird.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pWndParent*  
 Das neue übergeordnete Fenster.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die basisklassenimplementierung ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) durch Deaktivieren der Beschriftung ( [CMFCToolBarButton::m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext)) verwendet wird und die [ CMFCToolBarButton::m_bText](../../mfc/reference/cmfctoolbarbutton-class.md#m_btext) und [CMFCToolBarButton::m_bUserButton](../../mfc/reference/cmfctoolbarbutton-class.md#m_buserbutton) Datenmember zu `FALSE`.  
  
##  <a name="onclick"></a>  CMFCDropDownToolbarButton::OnClick  
 Wird vom Framework aufgerufen, klickt der Benutzer die Maustaste los.  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pWnd*  
 Das übergeordnete Fenster des Symbolleisten-Schaltfläche.  
  
 [in] *bDelay*  
 `TRUE` Wenn die Nachricht mit einer Verzögerung behandelt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Schaltfläche, die auf-Nachricht verarbeitet; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die basisklassenimplementierung [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick), durch das Aktualisieren des Status der Dropdown-Symbolleiste.  
  
 Wenn ein Benutzer die Symbolleisten-Schaltfläche klickt, wird diese Methode erstellt einen Zeitgeber, der die Länge des angegebenen Zeitintervalls wartet der [CMFCDropDownToolbarButton::m_uiShowBarDelay](#m_uishowbardelay) -Datenmember aus und klicken Sie dann öffnet der Dropdown-Symbolleiste mit der [CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar) Methode. Diese Methode schließt den Dropdown-Symbolleiste das zweite Mal mit der Benutzer die Symbolleisten-Schaltfläche klickt.  
  
##  <a name="onclickup"></a>  CMFCDropDownToolbarButton::OnClickUp  
 Vom Framework aufgerufen, wenn der Benutzer die Maustaste loslässt.  
  
```  
virtual BOOL OnClickUp();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Schaltfläche, die auf-Nachricht verarbeitet; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die basisklassenimplementierung [CMFCToolBarButton::OnClickUp](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup), durch das Aktualisieren des Status der Dropdown-Symbolleiste.  
  
 Diese Methode beendet den Zeitgeber Dropdown-Symbolleiste aus, wenn er aktiv ist. Es schließt die Dropdown-Symbolleiste, falls er geöffnet ist.  
  
 Weitere Informationen über die Dropdown-Symbolleiste und der Timer Dropdown-Symbolleiste finden Sie unter [CMFCDropDownToolbarButton::OnClick](#onclick).  
  
##  <a name="oncontexthelp"></a>  CMFCDropDownToolbarButton::OnContextHelp  
 Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste verarbeitet eine `WM_HELPHITTEST` Nachricht.  
  
```  
virtual BOOL OnContextHelp(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pWnd*  
 Das übergeordnete Fenster des Symbolleisten-Schaltfläche.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Schaltfläche Hilfe Meldung verarbeitet; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp)) durch Aufrufen der [CMFCDropDownToolbarButton::OnClick](#onclick) Methode mit *bDelay*festgelegt `FALSE`. Diese Methode gibt den Wert, der zurückgegebene [CMFCDropDownToolbarButton::OnClick](#onclick).  
  
 Weitere Informationen zu den `WM_HELPHITTEST message, see` [TN028: kontextbezogene Hilfe Support](../../mfc/tn028-context-sensitive-help-support.md).  
  
##  <a name="oncustomizemenu"></a>  CMFCDropDownToolbarButton::OnCustomizeMenu  
 Das angegebene Menü ändert, wenn die Anwendung auf der übergeordneten Symbolleiste ein Kontextmenü angezeigt.  
  
```  
virtual BOOL OnCustomizeMenu(CMenu* pMenu);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pMenu*  
 Klicken Sie im Menü anpassen.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt `TRUE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::OnCustomizeMenu](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu)) durch das Deaktivieren der folgenden Punkte:  
  
- **Schaltflächenbild kopieren**  
  
- **Schaltfläche Darstellung**  
  
- **Image**  
  
- **Text**  
  
- **Bild und Text**  
  
 Überschreiben Sie diese Methode, um das Kontextmenü zu ändern, das vom Framework in Anpassungsmodus angezeigt.  
  
##  <a name="ondraw"></a>  CMFCDropDownToolbarButton::OnDraw  
 Wird aufgerufen, durch das Framework der Schaltfläche gezeichnet werden soll, mithilfe des angegebenen Stile und Optionen.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    CMFCToolBarImages* pImages,  
    BOOL bHorz = TRUE,  
    BOOL bCustomizeMode = FALSE,  
    BOOL bHighlight = FALSE,  
    BOOL bDrawBorder = TRUE,  
    BOOL bGrayDisabledButtons = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDC*  
 Der Gerätekontext, in dem die Schaltfläche angezeigt.  
  
 [in] *Rect*  
 Das umschließende Rechteck der Schaltfläche.  
  
 [in] *pImages*  
 Die Auflistung der Symbolleistenbilder, die die Schaltfläche zugeordnet ist.  
  
 [in] *bHorz*  
 Der Status der Andocken der übergeordneten Symbolleiste. Dieser Parameter ist `TRUE` Wenn die Schaltfläche horizontal angedockt und `FALSE` Wenn die Schaltfläche vertikal angedockt ist.  
  
 [in] *bCustomizeMode*  
 Gibt an, ob die Symbolleiste im Anpassungsmodus ist. Dieser Parameter ist `TRUE` Wenn die Symbolleiste wird im Anpassungsmodus und `FALSE` Wenn die Symbolleiste ist nicht im Anpassungsmodus.  
  
 [in] *bHighlight*  
 Gibt an, ob die Schaltfläche hervorgehoben ist. Dieser Parameter ist `TRUE` Wenn die Schaltfläche wird hervorgehoben und `FALSE` Wenn die Schaltfläche nicht hervorgehoben.  
  
 [in] *bDrawBorder*  
 Gibt an, ob die Schaltfläche eine Rahmenlinie anzeigen soll. Dieser Parameter ist `TRUE` Wann sollte die Schaltfläche eine Rahmenlinie anzeigen und `FALSE` Wann sollte die Schaltfläche nicht eine Rahmenlinie anzeigen.  
  
 [in] *bGrayDisabledButtons*  
 Gibt an, ob schattieren deaktivierte Schaltflächen, oder verwenden Sie die Auflistung der Bilder deaktiviert. Dieser Parameter ist `TRUE` wenn deaktivierte Schaltflächen schattiert werden sollte und `FALSE` bei Verwendung dieser Methode sollte die Auflistung der Bilder deaktiviert.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode zum Anpassen von Symbolleisten-Schaltfläche zeichnen.  
  
##  <a name="ondrawoncustomizelist"></a>  CMFCDropDownToolbarButton::OnDrawOnCustomizeList  
 Wird aufgerufen, durch das Framework der Schaltfläche gezeichnet werden soll, der **Befehle** im Bereich der **anpassen** (Dialogfeld).  
  
```  
virtual int OnDrawOnCustomizeList(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDC*  
 Der Gerätekontext, in dem die Schaltfläche angezeigt.  
  
 [in] *Rect*  
 Das umschließende Rechteck der Schaltfläche.  
  
 [in] *bSelected*  
 Gibt an, ob die Schaltfläche aktiviert ist. Wenn dieser Parameter ist `TRUE`, die Schaltfläche aktiviert ist. Wenn dieser Parameter ist `FALSE`, die nicht ausgewählt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Breite in Pixel der Schaltflächen auf den angegebenen Gerätekontext.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, durch die Anpassungsdialogfelds ( **Befehle** Registerkarte ") wann wird die Schaltfläche" "erforderlich, selbst auf dem Besitzer gezeichnetes Listenfeld angezeigt werden sollen.  
  
 Erweitert die basisklassenimplementierung dieser Methode ( [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist)) durch die Beschriftung der Schaltfläche auf den Namen der Schaltfläche ändern (d. h. auf den Wert des der `lpszName` Parameter, die Sie übergeben an den Konstruktor).  
  
##  <a name="serialize"></a>  CMFCDropDownToolbarButton::Serialize  
 Dieses Objekt aus einem Archiv liest oder schreibt sie in ein Archiv.  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *Ar*  
 Die `CArchive` Objekt aus dem oder auf die zu serialisieren.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize)) durch die Ressourcen-ID der übergeordneten Symbolleiste serialisieren. Beim Laden von das Archiv ( [CArchive::IsLoading](../../mfc/reference/carchive-class.md#isloading) gibt einen Wert ungleich null), mit dieser Methode wird die `m_pToolBar` -Datenmember auf der Symbolleiste, die die serialisierten Ressourcen-ID enthält.  
  
##  <a name="setdefaultcommand"></a>  CMFCDropDownToolbarButton::SetDefaultCommand  
 Legt den Standardbefehl, den das Framework verwendet, wenn ein Benutzer die Schaltfläche klickt.  
  
```  
void SetDefaultCommand(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *UiCmd*  
 Die ID des Standardbefehls.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um einen Standardbefehl angeben, den das Framework ausführt, wenn der Benutzer auf die Schaltfläche klickt. Ein Element mit der Befehls-ID gemäß *UiCmd* muss in der übergeordneten Dropdown-Symbolleiste befinden.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCDropDownToolBar-Klasse](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarMenuButton-Klasse](../../mfc/reference/cmfctoolbarmenubutton-class.md)   
 [Exemplarische Vorgehensweise: Steuerelemente in eine Symbolleiste einfügen](../../mfc/walkthrough-putting-controls-on-toolbars.md)



