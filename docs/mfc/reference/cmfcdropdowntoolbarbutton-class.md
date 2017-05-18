---
title: Klasse CMFCDropDownToolbarButton | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- CMFCDropDownToolbarButton class
- OnCancelMode method
ms.assetid: bc9d69e6-bd3e-4c15-9368-e80a504a0ba7
caps.latest.revision: 31
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 24398ddb605489bf9677bd493a1bc1f490d583b9
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcdropdowntoolbarbutton-class"></a>CMFCDropDownToolbarButton-Klasse
Ein Symbolleisten-Schaltflächentyp, der sich wie eine normale Schaltfläche verhält, wenn darauf geklickt wird. Allerdings eine Dropdown-Symbolleiste öffnen ( [CMFCDropDownToolBar Klasse](../../mfc/reference/cmfcdropdowntoolbar-class.md) , wenn der Benutzer drückt und die Symbolleisten-Schaltfläche gedrückt hält.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCDropDownToolbarButton : public CMFCToolBarButton  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCDropDownToolbarButton::CMFCDropDownToolbarButton](#cmfcdropdowntoolbarbutton)|Erstellt ein `CMFCDropDownToolbarButton`-Objekt.|  
|`CMFCDropDownToolbarButton::~CMFCDropDownToolbarButton`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCDropDownToolbarButton::CopyFrom](#copyfrom)|Kopiert die Eigenschaften des aktuellen Schaltfläche eine andere Symbolleisten-Schaltfläche. (Überschreibt [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|  
|`CMFCDropDownToolbarButton::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar)|Öffnet eine Dropdown-Symbolleiste.|  
|[CMFCDropDownToolbarButton::ExportToMenuButton](#exporttomenubutton)|Kopiert den Text aus der Symbolleisten-Schaltfläche ein Menü. (Überschreibt [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton).)|  
|[CMFCDropDownToolbarButton::GetDropDownToolBar](#getdropdowntoolbar)|Ruft die Dropdown-Liste-Symbolleiste, die die Schaltfläche zugeordnet ist.|  
|`CMFCDropDownToolbarButton::GetThisClass`|Vom Framework verwendet werden, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das Klassentyp zugeordnet ist.|  
|[CMFCDropDownToolbarButton::IsDropDown](#isdropdown)|Bestimmt, ob die Dropdown-Symbolleiste derzeit geöffnet ist.|  
|[CMFCDropDownToolbarButton::IsExtraSize](#isextrasize)|Bestimmt, ob die Schaltfläche mit einem erweiterten Rahmen angezeigt werden kann. (Überschreibt [CMFCToolBarButton::IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize).)|  
|[CMFCDropDownToolbarButton::OnCalculateSize](#oncalculatesize)|Aufgerufen, um die Größe der Schaltfläche für den angegebenen Gerätekontext und Andockstatus berechnen. (Überschreibt [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|  
|`CMFCDropDownToolbarButton::OnCancelMode`|Aufgerufen, behandelt der [WM_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615) Nachricht. (Überschreibt `CMCToolBarButton::OnCancelMode`.)|  
|[CMFCDropDownToolbarButton::OnChangeParentWnd](#onchangeparentwnd)|Wird vom Framework aufgerufen, wenn eine neue Symbolleiste die Schaltfläche eingefügt wird. (Überschreibt [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|  
|[CMFCDropDownToolbarButton::OnClick](#onclick)|Vom Framework aufgerufen, wenn der Benutzer die Maustaste klickt. (Überschreibt [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|  
|[CMFCDropDownToolbarButton::OnClickUp](#onclickup)|Wird vom Framework aufgerufen, wenn der Benutzer die Maustaste loslässt. (Überschreibt [CMFCToolBarButton::OnClickUp](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup).)|  
|[CMFCDropDownToolbarButton::OnContextHelp](#oncontexthelp)|Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste behandelt eine `WM_HELPHITTEST` Nachricht. (Überschreibt [CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp).)|  
|[CMFCDropDownToolbarButton::OnCustomizeMenu](#oncustomizemenu)|Klicken Sie im bereitgestellten ändert, wenn die Anwendung auf der übergeordneten Symbolleiste ein Kontextmenü angezeigt. (Überschreibt [CMFCToolBarButton::OnCustomizeMenu](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu).)|  
|[CMFCDropDownToolbarButton::OnDraw](#ondraw)|Vom Framework aufgerufen wird die Schaltfläche gezeichnet werden soll, mithilfe der angegebenen Formate und -Optionen. (Überschreibt [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|  
|[CMFCDropDownToolbarButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|Aufgerufen, um das Zeichnen der Schaltfläche die **Befehle** im Bereich der **anpassen** Dialogfeld. (Überschreibt [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|  
|[CMFCDropDownToolbarButton::Serialize](#serialize)|Dieses Objekt aus dem Archiv liest oder schreibt dieses in ein Archiv. (Überschreibt [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|  
|[CMFCDropDownToolbarButton::SetDefaultCommand](#setdefaultcommand)|Legt die Standardbefehl, den das Framework verwendet wird, wenn ein Benutzer auf die Schaltfläche klickt.|  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCDropDownToolbarButton::m_uiShowBarDelay](#m_uishowbardelay)|Gibt die Länge der Zeit, die ein Benutzer die Maustaste gedrückt halten muss, bevor die Dropdown-Symbolleiste angezeigt wird.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `CMFCDropDownToolBarButton` eine normale Schaltfläche besteht darin, dass es einen kleinen Pfeil in der unteren rechten Ecke der Schaltfläche hat. Nachdem der Benutzer aus der Dropdown-Symbolleiste eine Schaltfläche auswählt, zeigt das Framework das Symbol auf der obersten Ebene Symbolleisten-Schaltfläche (die Schaltfläche mit den kleinen Pfeil in der unteren rechten Ecke).  
  
 Informationen zum Implementieren einer Dropdown-Symbolleiste finden Sie unter [CMFCDropDownToolBar-Klasse](../../mfc/reference/cmfcdropdowntoolbar-class.md).  
  
 Die `CMFCDropDownToolBarButton` Objekt exportiert werden kann ein [CMFCToolBarMenuButton Klasse](../../mfc/reference/cmfctoolbarmenubutton-class.md) -Objekt und als eine Menüschaltfläche mit einem Popupmenü angezeigt.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCDropDownToolbarButton](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdropdowntoolbar.h  
  
##  <a name="copyfrom"></a>CMFCDropDownToolbarButton::CopyFrom  
 Kopiert die Eigenschaften des aktuellen Schaltfläche eine andere Symbolleisten-Schaltfläche.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `src`  
 Ein Verweis auf die Schaltfläche "Quelle" aus dem kopiert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Kopieren von einem anderen Symbolleisten-Schaltfläche auf diese Schaltfläche. `src`muss vom Typ `CMFCDropDownToolbarButton`.  
  
##  <a name="cmfcdropdowntoolbarbutton"></a>CMFCDropDownToolbarButton::CMFCDropDownToolbarButton  
 Erstellt ein `CMFCDropDownToolbarButton`-Objekt.  
  
```  
CMFCDropDownToolbarButton();

 
CMFCDropDownToolbarButton(
    LPCTSTR lpszName,  
    CMFCDropDownToolBar* pToolBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszName`  
 Der Standardtext der Schaltfläche.  
  
 [in] `pToolBar`  
 Ein Zeiger auf die `CMFCDropDownToolBar` -Objekt, das angezeigt wird, wenn der Benutzer die Taste drückt.  
  
### <a name="remarks"></a>Hinweise  
 Die zweite Überladung des Konstruktors kopiert die Dropdown-Schaltfläche die erste Schaltfläche auf der Symbolleiste, die `pToolBar` angibt.  
  
 In der Regel verwendet eine Dropdown-Symbolleisten-Schaltfläche den Text in der zuletzt verwendeten Schaltfläche in der Symbolleiste, die `pToolBar` angibt. Verwendet den angegebenen Text `lpszName` Wenn die Schaltfläche eine Schaltfläche konvertiert oder wird angezeigt, der **Befehle** auf der Registerkarte der **anpassen** Dialogfeld. Weitere Informationen zu den **anpassen** Dialogfeld finden Sie unter [CMFCToolBarsCustomizeDialog Klasse](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Objekt vom Erstellen der `CMFCDropDownToolbarButton` Klasse. Dieser Codeausschnitt ist Teil der [Demobeispiel für Visual Studio](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#31;](../../mfc/codesnippet/cpp/cmfcdropdowntoolbarbutton-class_1.cpp)]  
  
##  <a name="dropdowntoolbar"></a>CMFCDropDownToolbarButton::DropDownToolbar  
 Öffnet eine Dropdown-Symbolleiste.  
  
```  
BOOL DropDownToolbar(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 Das übergeordnete Fenster des Dropdown-Frame oder `NULL` mithilfe des übergeordneten Fensters der Dropdown-Symbolleisten-Schaltfläche.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Methode erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die [CMFCDropDownToolbarButton::OnClick](#onclick) -Methode ruft diese Methode, um die Dropdown-Symbolleiste zu öffnen, wenn der Benutzer drückt und die Symbolleisten-Schaltfläche gedrückt hält.  
  
 Diese Methode erstellt die Dropdown-Symbolleiste mithilfe der [CMFCDropDownFrame::Create](../../mfc/reference/cmfcdropdownframe-class.md#create) Methode. Wenn die übergeordneten Symbolleiste vertikal angedockt ist, wird diese Methode die Dropdown-Symbolleiste entweder auf der linken oder rechten Seite der übergeordneten Symbolleiste, abhängig von der Größe. Andernfalls wird diese Methode die Dropdown-Symbolleiste unterhalb der übergeordneten Symbolleiste.  
  
 Diese Methode schlägt fehl, wenn `pWnd` ist `NULL` und die Dropdown-Symbolleisten-Schaltfläche verfügt nicht über ein übergeordnetes Fenster.  
  
##  <a name="exporttomenubutton"></a>CMFCDropDownToolbarButton::ExportToMenuButton  
 Kopiert den Text aus der Symbolleisten-Schaltfläche ein Menü.  
  
```  
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `menuButton`  
 Ein Verweis auf die Schaltfläche Ziel.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert ungleich 0 (null), wenn die Methode erfolgreich ausgeführt wird, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft die Implementierung der Basisklasse ( [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)) und fügt dann an die Ziel-Schaltfläche ein Popupmenü, die jedes Menüelement Symbolleiste auf dieser Schaltfläche enthält. Diese Methode fügt keinen Untermenüs zu dem Popup-Menü.  
  
 Diese Methode schlägt fehl, wenn der übergeordneten Symbolleiste `m_pToolBar`, ist `NULL` oder Implementierung der Basisklasse gibt `FALSE`.  
  
##  <a name="getdropdowntoolbar"></a>CMFCDropDownToolbarButton::GetDropDownToolBar  
 Ruft die Dropdown-Liste-Symbolleiste, die die Schaltfläche zugeordnet ist.  
  
```  
CMFCToolBar* GetDropDownToolBar() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Dropdown-Liste-Symbolleiste, die die Schaltfläche zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt die `m_pToolBar` -Datenmember.  
  
##  <a name="isdropdown"></a>CMFCDropDownToolbarButton::IsDropDown  
 Bestimmt, ob die Dropdown-Symbolleiste derzeit geöffnet ist.  
  
```  
BOOL IsDropDown() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Dropdown-Symbolleiste geöffnet wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework öffnet die Dropdown-Symbolleiste mithilfe der [CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar) Methode. Das Framework schließt die Dropdown-Symbolleiste, wenn der Benutzer die linke Maustaste in den nicht-Clientbereich der Dropdown-Symbolleiste drückt.  
  
##  <a name="isextrasize"></a>CMFCDropDownToolbarButton::IsExtraSize  
 Bestimmt, ob die Schaltfläche mit einem erweiterten Rahmen angezeigt werden kann.  
  
```  
virtual BOOL IsExtraSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Symbolleisten-Schaltfläche mit einem erweiterten Rahmen angezeigt werden kann; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu erweiterten Rahmen, finden Sie unter [CMFCToolBarButton::IsExtraSize](../../mfc/reference/cmfctoolbarbutton-class.md#isextrasize).  
  
##  <a name="m_uishowbardelay"></a>CMFCDropDownToolbarButton::m_uiShowBarDelay  
 Gibt die Länge der Zeit, die ein Benutzer die Maustaste gedrückt halten muss, bevor die Dropdown-Symbolleiste angezeigt wird.  
  
```  
static UINT m_uiShowBarDelay;  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Verzögerungszeit wird in Millisekunden gemessen. Der Standardwert ist 500. Sie können einen anderen Verzögerung durch Ändern des Werts dieser freigegebene Member festlegen.  
  
##  <a name="oncalculatesize"></a>CMFCDropDownToolbarButton::OnCalculateSize  
 Aufgerufen, um die Größe der Schaltfläche für den angegebenen Gerätekontext und Andockstatus berechnen.  
  
```  
virtual SIZE OnCalculateSize(
    CDC* pDC,  
    const CSize& sizeDefault,  
    BOOL bHorz);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Der Gerätekontext, der die Schaltfläche angezeigt.  
  
 [in] `sizeDefault`  
 Die Standardgröße der Schaltfläche.  
  
 [in] `bHorz`  
 Der Status der Andocken der übergeordneten Symbolleiste. Dieser Parameter ist `TRUE` , wenn die Symbolleiste horizontal angedockt wird oder verankert ist, oder `FALSE` , wenn die Symbolleiste vertikal verankert ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `SIZE` -Struktur, die die Dimensionen der Schaltfläche in Pixel enthält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die Implementierung der Basisklasse ( [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize)) durch die Breite des den Dropdown Pfeil auf die horizontale Abmessung die Größe der Schaltfläche hinzufügen.  
  
##  <a name="onchangeparentwnd"></a>CMFCDropDownToolbarButton::OnChangeParentWnd  
 Wird vom Framework aufgerufen, wenn eine neue Symbolleiste die Schaltfläche eingefügt wird.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndParent`  
 Das neue übergeordnete Fenster.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die Implementierung der Basisklasse ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) durch Deaktivieren der Beschriftung ( [CMFCToolBarButton::m_strText](../../mfc/reference/cmfctoolbarbutton-class.md#m_strtext)) und die [CMFCToolBarButton::m_bText](../../mfc/reference/cmfctoolbarbutton-class.md#m_btext) und [CMFCToolBarButton::m_bUserButton](../../mfc/reference/cmfctoolbarbutton-class.md#m_buserbutton) Datenmember `FALSE`.  
  
##  <a name="onclick"></a>CMFCDropDownToolbarButton::OnClick  
 Vom Framework aufgerufen, wenn der Benutzer die Maustaste klickt.  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 Das übergeordnete Fenster der Symbolleisten-Schaltfläche.  
  
 [in] `bDelay`  
 `TRUE`Wenn die Nachricht mit einer Verzögerung behandelt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Schaltfläche, die auf-Nachricht verarbeitet; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die Implementierung der Basisklasse [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick), durch das Aktualisieren des Status der Dropdown-Symbolleiste.  
  
 Wenn ein Benutzer die Symbolleisten-Schaltfläche klickt, wird diese Methode erstellt einen Zeitgeber, der die Länge des angegebenen Zeitintervalls wartet der [CMFCDropDownToolbarButton::m_uiShowBarDelay](#m_uishowbardelay) -Datenmember aus und klicken Sie dann öffnet der Dropdown-Liste Symbolleiste mithilfe der [CMFCDropDownToolbarButton::DropDownToolbar](#dropdowntoolbar) Methode. Diese Methode schließt den Dropdown-Symbolleiste das zweite Mal mit der Benutzer die Symbolleisten-Schaltfläche klickt.  
  
##  <a name="onclickup"></a>CMFCDropDownToolbarButton::OnClickUp  
 Wird vom Framework aufgerufen, wenn der Benutzer die Maustaste loslässt.  
  
```  
virtual BOOL OnClickUp();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Schaltfläche, die auf-Nachricht verarbeitet; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die Implementierung der Basisklasse [CMFCToolBarButton::OnClickUp](../../mfc/reference/cmfctoolbarbutton-class.md#onclickup), durch das Aktualisieren des Status der Dropdown-Symbolleiste.  
  
 Diese Methode hält den Dropdown-Symbolleisten-Zeitgeber, wenn er aktiv ist. Die Dropdown-Symbolleiste wird geschlossen, wenn sie geöffnet ist.  
  
 Weitere Informationen zu den Dropdown-Symbolleiste und Dropdown-Symbolleisten-Zeitgeber, finden Sie unter [CMFCDropDownToolbarButton::OnClick](#onclick).  
  
##  <a name="oncontexthelp"></a>CMFCDropDownToolbarButton::OnContextHelp  
 Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste behandelt eine `WM_HELPHITTEST` Nachricht.  
  
```  
virtual BOOL OnContextHelp(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 Das übergeordnete Fenster der Symbolleisten-Schaltfläche.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Schaltfläche hilfemeldung verarbeitet; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die Implementierung der Basisklasse ( [CMFCToolBarButton::OnContextHelp](../../mfc/reference/cmfctoolbarbutton-class.md#oncontexthelp)) durch Aufrufen der [CMFCDropDownToolbarButton::OnClick](#onclick) -Methode mit `bDelay` festgelegt `FALSE`. Diese Methode gibt den Wert, der von zurückgegebene [CMFCDropDownToolbarButton::OnClick](#onclick).  
  
 Weitere Informationen zu den `WM_HELPHITTEST message, see` [TN028: kontextbezogene Hilfe Support](../../mfc/tn028-context-sensitive-help-support.md).  
  
##  <a name="oncustomizemenu"></a>CMFCDropDownToolbarButton::OnCustomizeMenu  
 Klicken Sie im bereitgestellten ändert, wenn die Anwendung auf der übergeordneten Symbolleiste ein Kontextmenü angezeigt.  
  
```  
virtual BOOL OnCustomizeMenu(CMenu* pMenu);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pMenu`  
 Klicken Sie im Menü anpassen.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt `TRUE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die Implementierung der Basisklasse ( [CMFCToolBarButton::OnCustomizeMenu](../../mfc/reference/cmfctoolbarbutton-class.md#oncustomizemenu)) deaktivieren Sie die folgenden Punkte:  
  
- **Schaltfläche Kopieren**  
  
- **Darstellung der Schaltfläche**  
  
- **Bild**  
  
- **Text**  
  
- **Bild und Text**  
  
 Überschreiben Sie diese Methode, um das Kontextmenü zu ändern, das vom Framework in den Anpassungsmodus angezeigt.  
  
##  <a name="ondraw"></a>CMFCDropDownToolbarButton::OnDraw  
 Vom Framework aufgerufen wird die Schaltfläche gezeichnet werden soll, mithilfe der angegebenen Formate und -Optionen.  
  
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
 [in] `pDC`  
 Der Gerätekontext, der die Schaltfläche angezeigt.  
  
 [in] `rect`  
 Das umschließende Rechteck der Schaltfläche.  
  
 [in] `pImages`  
 Die Auflistung der Symbolleistenbilder, die der Schaltfläche zugeordnet ist.  
  
 [in] `bHorz`  
 Der Status der Andocken der übergeordneten Symbolleiste. Dieser Parameter ist `TRUE` Wenn die Schaltfläche horizontal angedockt ist und `FALSE` Wenn die Schaltfläche vertikal angedockt ist.  
  
 [in] `bCustomizeMode`  
 Gibt an, ob die Symbolleiste im Anpassungsmodus ist. Dieser Parameter ist `TRUE` Wenn die Symbolleiste befindet sich im Anpassungsmodus und `FALSE` Wenn die Symbolleiste ist nicht im Anpassungsmodus.  
  
 [in] `bHighlight`  
 Gibt an, ob die Schaltfläche hervorgehoben ist. Dieser Parameter ist `TRUE` die Schaltfläche wird hervorgehoben, wenn und `FALSE` Wenn die Schaltfläche nicht hervorgehoben.  
  
 [in] `bDrawBorder`  
 Gibt an, ob den Rahmen der Schaltfläche angezeigt werden soll. Dieser Parameter ist `TRUE` Wenn sollte die Schaltfläche eine Rahmenlinie anzeigen und `FALSE` Wenn die Schaltfläche nicht angezeigt werden sollen den Rahmen.  
  
 [in] `bGrayDisabledButtons`  
 Gibt an, ob deaktivierte Schaltflächen schattieren, oder verwenden Sie die Auflistung der Bilder deaktiviert. Dieser Parameter ist `TRUE` wenn deaktivierte Schaltflächen schattiert werden sollen und `FALSE` bei Verwendung dieser Methode sollte die Auflistung der Bilder deaktiviert.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um die Symbolleiste Schaltfläche zeichnen angepasst.  
  
##  <a name="ondrawoncustomizelist"></a>CMFCDropDownToolbarButton::OnDrawOnCustomizeList  
 Aufgerufen, um das Zeichnen der Schaltfläche die **Befehle** im Bereich der **anpassen** Dialogfeld.  
  
```  
virtual int OnDrawOnCustomizeList(
    CDC* pDC,  
    const CRect& rect,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Der Gerätekontext, der die Schaltfläche angezeigt.  
  
 [in] `rect`  
 Das umschließende Rechteck der Schaltfläche.  
  
 [in] `bSelected`  
 Gibt an, ob die Schaltfläche aktiviert ist. Wenn dieser Parameter `TRUE`, ausgewählt ist. Wenn dieser Parameter ist `FALSE`, die nicht ausgewählt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Breite in Pixel der Schaltfläche auf den angegebenen Gerätekontext.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, durch das Dialogfeld Anpassen ( **Befehle** Registerkarte) Wenn die Schaltfläche erforderlich ist, selbst im Ownerdrawn-Listenfeld angezeigt.  
  
 Diese Methode erweitert die Implementierung der Basisklasse ( [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist)) durch die Beschriftung der Schaltfläche auf den Namen der Schaltfläche ändern (also auf den Wert der der `lpszName` -Parameter, der an den Konstruktor übergeben wurde).  
  
##  <a name="serialize"></a>CMFCDropDownToolbarButton::Serialize  
 Dieses Objekt aus dem Archiv liest oder schreibt dieses in ein Archiv.  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `ar`  
 Das `CArchive` Objekt aus dem oder in das Serialisieren.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die Implementierung der Basisklasse ( [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize)) serialisieren Sie die Ressourcen-ID der übergeordneten Symbolleiste. Das Archiv wird geladen, wenn ( [CArchive::IsLoading](../../mfc/reference/carchive-class.md#isloading) gibt einen Wert ungleich null), mit dieser Methode wird der `m_pToolBar` -Datenmember auf die Symbolleiste, die die serialisierte Ressource-ID enthält.  
  
##  <a name="setdefaultcommand"></a>CMFCDropDownToolbarButton::SetDefaultCommand  
 Legt die Standardbefehl, den das Framework verwendet wird, wenn ein Benutzer auf die Schaltfläche klickt.  
  
```  
void SetDefaultCommand(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmd`  
 Die ID des Standardbefehls.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um einen Standardwert anzugeben, die das Framework ausführt, wenn der Benutzer auf die Schaltfläche klickt. Ein Element mit der angegebenen Befehls-ID `uiCmd` , müssen sich im übergeordneten Dropdown-Symbolleiste.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCDropDownToolBar-Klasse](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarMenuButton-Klasse](../../mfc/reference/cmfctoolbarmenubutton-class.md)   
 [Exemplarische Vorgehensweise: Einfügen von Steuerelementen in Symbolleisten](../../mfc/walkthrough-putting-controls-on-toolbars.md)




