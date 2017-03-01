---
title: Klasse CMFCToolBarEditBoxButton | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- OnDrawOnCustomizeList
- OnDraw
- CMFCToolBarEditBoxButton::OnDrawOnCustomizeList
- CMFCToolBarEditBoxButton.SetACCData
- CMFCToolBarEditBoxButton::OnDraw
- OnCalculateSize
- SetACCData
- CMFCToolBarEditBoxButton
- CMFCToolBarEditBoxButton::SetACCData
- CMFCToolBarEditBoxButton::Serialize
- CMFCToolBarEditBoxButton.OnDraw
- CMFCToolBarEditBoxButton.OnDrawOnCustomizeList
- CMFCToolBarEditBoxButton::OnCalculateSize
- Serialize
- CMFCToolBarEditBoxButton.Serialize
- CMFCToolBarEditBoxButton.OnCalculateSize
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarEditBoxButton class
- SetACCData method
- OnCalculateSize method
- OnDraw method
- OnDrawOnCustomizeList method
- Serialize method
ms.assetid: b21d9b67-6bf7-4ca9-bd62-b237756e0ab3
caps.latest.revision: 28
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
ms.openlocfilehash: 7f79c69c9f370f2d79752ed141affac3f97ce716
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbareditboxbutton-class"></a>CMFCToolBarEditBoxButton-Klasse
Eine Symbolleisten-Schaltfläche, die ein Bearbeitungssteuerelement enthält ( [CEdit Class](../../mfc/reference/cedit-class.md)).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCToolBarEditBoxButton : public CMFCToolBarButton  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton](#cmfctoolbareditboxbutton)|Erstellt ein `CMFCToolBarEditBoxButton`-Objekt.|  
|`CMFCToolBarEditBoxButton::~CMFCToolBarEditBoxButton`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarEditBoxButton::CanBeStretched](#canbestretched)|Gibt an, ob ein Benutzer während der Anpassung der Schaltfläche gestreckt werden kann. (Überschreibt [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched).)|  
|[CMFCToolBarEditBoxButton::CopyFrom](#copyfrom)|Kopiert die Eigenschaften des aktuellen Schaltfläche eine andere Symbolleisten-Schaltfläche. (Überschreibt [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|  
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton::CreateEdit](#createedit)|Erstellt ein neues Edit-Steuerelement die Schaltfläche.|  
|`CMFCToolBarEditBoxButton::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCToolBarEditBoxButton::GetByCmd](#getbycmd)|Ruft die erste `CMFCToolBarEditBoxButton` Objekt in der Anwendung mit der angegebenen Befehls-ID.|  
|[CMFCToolBarEditBoxButton::GetContentsAll](#getcontentsall)|Ruft den Text des ersten bearbeiten im Feld Symbolleisten-Steuerelements, die die angegebene Befehls-ID.|  
|[CMFCToolBarEditBoxButton::GetContextMenuID](#getcontextmenuid)|Ruft die Ressourcen-ID des Kontextmenüs, die der Schaltfläche zugeordnet ist.|  
|[CMFCToolBarEditBoxButton::GetEditBorder](#geteditborder)|Ruft das umschließende Rechteck des Teils bearbeiten die Bearbeitungsschaltfläche.|  
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton::GetEditBox](#geteditbox)|Gibt einen Zeiger auf das Edit-Steuerelement, das auf der Schaltfläche eingebettet ist.|  
|[CMFCToolBarEditBoxButton::GetHwnd](#gethwnd)|Ruft das Fensterhandle, das dem die Symbolleisten-Schaltfläche zugeordnet ist. (Überschreibt [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).)|  
|[CMFCToolBarEditBoxButton::GetInvalidateRect](#getinvalidaterect)|Ruft den Bereich des Clientbereichs der Schaltfläche, die neu gezeichnet werden muss. (Überschreibt [CMFCToolBarButton::GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect).)|  
|`CMFCToolBarEditBoxButton::GetThisClass`|Vom Framework verwendet werden, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das Klassentyp zugeordnet ist.|  
|[CMFCToolBarEditBoxButton::HaveHotBorder](#havehotborder)|Bestimmt, ob ein Rahmen der Schaltfläche angezeigt wird, wenn ein Benutzer auf die Schaltfläche klickt. (Überschreibt [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|  
|[CMFCToolBarEditBoxButton::IsFlatMode](#isflatmode)|Bestimmt, ob bearbeiten Schaltflächen flach haben.|  
|[CMFCToolBarEditBoxButton::NotifyCommand](#notifycommand)|Gibt an, ob die Schaltfläche verarbeitet die [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Nachricht. (Überschreibt [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).)|  
|[CMFCToolBarEditBoxButton::OnAddToCustomizePage](#onaddtocustomizepage)|Vom Framework aufgerufen, wenn die Schaltfläche hinzugefügt wird ein **anpassen** Dialogfeld. (Überschreibt [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|  
|`CMFCToolBarEditBoxButton::OnCalculateSize`|Aufgerufen, um die Größe der Schaltfläche für den angegebenen Gerätekontext und Andockstatus berechnen. (Überschreibt [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|  
|[CMFCToolBarEditBoxButton::OnChangeParentWnd](#onchangeparentwnd)|Wird vom Framework aufgerufen, wenn eine neue Symbolleiste die Schaltfläche eingefügt wird. (Überschreibt [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|  
|[CMFCToolBarEditBoxButton::OnClick](#onclick)|Vom Framework aufgerufen, wenn der Benutzer die Maustaste klickt. (Überschreibt [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|  
|[CMFCToolBarEditBoxButton::OnCtlColor](#onctlcolor)|Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste behandelt eine `WM_CTLCOLOR` Nachricht. (Überschreibt [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).)|  
|`CMFCToolBarEditBoxButton::OnDraw`|Vom Framework aufgerufen wird die Schaltfläche gezeichnet werden soll, mithilfe der angegebenen Formate und -Optionen. (Überschreibt [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|  
|`CMFCToolBarEditBoxButton::OnDrawOnCustomizeList`|Aufgerufen, um das Zeichnen der Schaltfläche die **Befehle** im Bereich der **anpassen** Dialogfeld. (Überschreibt [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|  
|[CMFCToolBarEditBoxButton::OnGlobalFontsChanged](#onglobalfontschanged)|Wird vom Framework aufgerufen, wenn die globale Schriftart geändert hat. (Überschreibt [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged).)|  
|[CMFCToolBarEditBoxButton::OnMove](#onmove)|Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste verschoben wird. (Überschreibt [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|  
|[CMFCToolBarEditBoxButton::OnShow](#onshow)|Vom Framework aufgerufen, wenn die Schaltfläche wird sichtbar oder unsichtbar. (Überschreibt [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|  
|[CMFCToolBarEditBoxButton::OnSize](#onsize)|Wird vom Framework aufgerufen, wenn die übergeordneten Symbolleiste seine Größe ändert oder Position und diese Änderung bewirkt, dass die Schaltfläche, um die Größe zu ändern. (Überschreibt [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|  
|[CMFCToolBarEditBoxButton::OnUpdateToolTip](#onupdatetooltip)|Wird vom Framework aufgerufen, wenn die übergeordneten Symbolleiste den QuickInfotext aktualisiert. (Überschreibt [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|  
|`CMFCToolBarEditBoxButton::Serialize`|Dieses Objekt aus dem Archiv liest oder schreibt dieses in ein Archiv. (Überschreibt [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|  
|`CMFCToolBarEditBoxButton::SetACCData`|Füllt die angegebene `CAccessibilityData` Objekt mit Zugriff auf Daten aus der Symbolleisten-Schaltfläche. (Überschreibt [CMFCToolBarButton::SetACCData](../../mfc/reference/cmfctoolbarbutton-class.md#setaccdata).)|  
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton::SetContents](#setcontents)|Legt den Text in das Steuerelement zum Bearbeiten der Schaltfläche fest.|  
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton::SetContentsAll](#setcontentsall)|Sucht die Steuerelement-Schaltfläche, die eine angegebene Befehls-ID, und legt den Text in das Steuerelement zum Bearbeiten dieser Schaltfläche.|  
|[CMFCToolBarEditBoxButton::SetContextMenuID](#setcontextmenuid)|Gibt die Ressourcen-ID des Kontextmenüs, die der Schaltfläche zugeordnet ist.|  
|[CMFCToolBarEditBoxButton::SetFlatMode](#setflatmode)|Gibt die flache Darstellung des Bearbeitungsschaltflächen in der Anwendung an.|  
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton::SetStyle](#setstyle)|Gibt den Stil der Schaltfläche. (Überschreibt [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|  
  
## <a name="remarks"></a>Hinweise  
 Um eine Symbolleiste eine Schaltfläche zum Bearbeiten im Feld hinzuzufügen, gehen Sie folgendermaßen vor:  
  
 1. Reservieren Sie eine Platzhalterressourcen-ID für die Schaltfläche in der übergeordneten Symbolleistenressource.  
  
 2. Konstruieren Sie ein `CMFCToolBarEditBoxButton`-Objekt.  
  
 3. In den Message-Handler, verarbeitet die `AFX_WM_RESETTOOLBAR` angezeigt wird, ersetzen Sie die platzhalterschaltfläche mithilfe von mit der neuen kombinationsfeldschaltfläche [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).  
  
 Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Einfügen von Steuerelementen auf Symbolleisten](../../mfc/walkthrough-putting-controls-on-toolbars.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCToolBarEditBoxButton` Klasse. Das Beispiel zeigt, wie ein Benutzer kann Dehnen die Schaltfläche während der Anpassung, angeben, dass ein Rahmen der Schaltfläche angezeigt wird, wenn ein Benutzer auf die Schaltfläche klickt, legen Sie den Text in das Textfeld-Steuerelement, geben Sie die flache Darstellung des Bearbeitungsschaltflächen in der Anwendung und gibt den Stil eines Steuerelements Symbolleiste bearbeiten.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#40;](../../mfc/reference/codesnippet/cpp/cmfctoolbareditboxbutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 `CMFCToolBarEditBoxButton` 
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtoolbareditboxbutton.h  
  
##  <a name="a-namecanbestretcheda--cmfctoolbareditboxbuttoncanbestretched"></a><a name="canbestretched"></a>CMFCToolBarEditBoxButton::CanBeStretched  
 Gibt an, ob ein Benutzer während der Anpassung der Schaltfläche gestreckt werden kann.  
  
```  
virtual BOOL CanBeStretched() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt `TRUE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig lässt das Framework nicht den Benutzer eine Symbolleisten-Schaltfläche während der Anpassung ausdehnen. Diese Methode erweitert die Implementierung der Basisklasse ( [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)), weil der Benutzer eine Bearbeitungsschaltfläche im Feld Symbolleiste während der Anpassung gestreckt.  
  
##  <a name="a-namecmfctoolbareditboxbuttona--cmfctoolbareditboxbuttoncmfctoolbareditboxbutton"></a><a name="cmfctoolbareditboxbutton"></a>CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton  
 Erstellt eine [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md) Objekt.  
  
```  
CMFCToolBarEditBoxButton(
    UINT uiID,  
    int iImage,  
    DWORD dwStyle=ES_AUTOHSCROLL,  
    int iWidth=0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiID`  
 Gibt die Steuerelement-ID an.  
  
 [in] `iImage`  
 Gibt den nullbasierten Index des Bildes einer Symbolleisten an. Das Bild befindet sich in der [CMFCToolBarImages Klasse](../../mfc/reference/cmfctoolbarimages-class.md) Objekt, [CMFCToolBar Klasse](../../mfc/reference/cmfctoolbar-class.md) -Klasse verwaltet.  
  
 [in] `dwStyle`  
 Gibt das Format des Steuerelements bearbeiten.  
  
 [in] `iWidth`  
 Gibt die Breite des Edit-Steuerelements in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Der Standardkonstruktor legt das Format des Steuerelements bearbeiten, auf die folgende Kombination:  
  
 `WS_CHILD | WS_VISIBLE | ES_AUTOHSCROLL`  
  
 Die Standardbreite des Steuerelements beträgt 150 Pixel.  
  
##  <a name="a-namecopyfroma--cmfctoolbareditboxbuttoncopyfrom"></a><a name="copyfrom"></a>CMFCToolBarEditBoxButton::CopyFrom  
 Kopiert die Eigenschaften des aktuellen Schaltfläche eine andere Symbolleisten-Schaltfläche.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `src`  
 Ein Verweis auf die Schaltfläche "Quelle" aus dem kopiert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Kopieren von einem anderen Symbolleisten-Schaltfläche auf diese Schaltfläche. `src`muss vom Typ `CMFCToolBarEditBoxButton`.  
  
##  <a name="a-namecreateedita--cmfctoolbareditboxbuttoncreateedit"></a><a name="createedit"></a>CMFCToolBarEditBoxButton::CreateEdit  
 Erstellt ein neues Edit-Steuerelement die Schaltfläche.  
  
```  
virtual CEdit* CreateEdit(
    CWnd* pWndParent,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Parameter  
 `[in] pWndParent`  
 Gibt das übergeordnete Fenster des Bearbeitungssteuerelements. Er darf nicht NULL sein.  
  
 `[in] rect`  
 Gibt des Bearbeitungssteuerelements Größe und Position.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das neu erstellte Bearbeitungssteuerelement; Es ist `NULL` Wenn Erstellung und Anlage des Steuerelements ausführen können.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen ein `CMFCToolBarEditBoxButton`Objekt in zwei Schritten. Zuerst rufen Sie den Konstruktor aus, und rufen dann `CreateEdit,` der Windows-Edit-Steuerelement erstellt, und fügt es der `CMFCToolBarEditBoxButton` Objekt.  
  
##  <a name="a-namegetbycmda--cmfctoolbareditboxbuttongetbycmd"></a><a name="getbycmd"></a>CMFCToolBarEditBoxButton::GetByCmd  
 Ruft die erste `CMFCToolBarEditBoxButton` Objekt in der Anwendung mit der angegebenen Befehls-ID.  
  
```  
static CMFCToolBarEditBoxButton* __stdcall GetByCmd(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmd`  
 Die Befehls-ID der Schaltfläche abrufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste `CMFCToolBarEditBoxButton` Objekt in der Anwendung mit der angegebenen Befehls-ID oder `NULL` , wenn kein solches Objekt vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese gemeinsam genutzte Dienstprogramme-Methode wird von Methoden verwendet, z. B. [CMFCToolBarEditBoxButton::SetContentsAll](#setcontentsall) und [CMFCToolBarEditBoxButton::GetContentsAll](#getcontentsall) festlegen oder den Text des ersten bearbeiten im Feld Symbolleisten-Steuerelements, die die angegebene Befehls-ID.  
  
##  <a name="a-namegetcontentsalla--cmfctoolbareditboxbuttongetcontentsall"></a><a name="getcontentsall"></a>CMFCToolBarEditBoxButton::GetContentsAll  
 Ruft den Text des ersten bearbeiten im Feld Symbolleisten-Steuerelements, die die angegebene Befehls-ID.  
  
```  
static CString __stdcall GetContentsAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmd`  
 Die Befehls-ID der Schaltfläche aus dem Inhalt abgerufen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` -Objekt, das den Text des ersten bearbeiten im Feld Symbolleisten-Steuerelements enthält, die die angegebenen Befehls-ID.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt die leere Zeichenfolge zurück, wenn kein `CMFCToolBarEditBoxButton` Objekte verfügen über die angegebene Befehls-ID.  
  
##  <a name="a-namegetcontextmenuida--cmfctoolbareditboxbuttongetcontextmenuid"></a><a name="getcontextmenuid"></a>CMFCToolBarEditBoxButton::GetContextMenuID  
 Ruft die Ressourcen-ID des Kontextmenüs, die der Schaltfläche zugeordnet ist.  
  
```  
UINT GetContextMenuID();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Ressourcen-ID des Kontextmenüs, die 0 oder die Schaltfläche zugeordnet ist, verfügt die Schaltfläche keine zugeordnete Kontextmenü.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verwendet die Ressourcen-ID, um das Kontextmenü zu erstellen, wenn der Benutzer auf die Schaltfläche klickt.  
  
##  <a name="a-namegeteditbordera--cmfctoolbareditboxbuttongeteditborder"></a><a name="geteditborder"></a>CMFCToolBarEditBoxButton::GetEditBorder  
 Ruft das umschließende Rechteck des Teils bearbeiten die Bearbeitungsschaltfläche.  
  
```  
virtual void GetEditBorder(CRect& rectBorder);
```  
  
### <a name="parameters"></a>Parameter  
 [out] `rectBorder`  
 Ein Verweis auf die `CRect` -Objekt, das das umschließende Rechteck empfängt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft das umschließende Rechteck des Bearbeitungssteuerelements in Clientkoordinaten. Es erweitert die Größe des Rechtecks in jede Richtung um ein Pixel.  
  
 Die [CMFCVisualManager::OnDrawEditBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondraweditborder) -Methode ruft diese Methode auf, wenn sie den Rahmen um zeichnet ein `CMFCToolBarEditBoxButton` Objekt.  
  
##  <a name="a-namegeteditboxa--cmfctoolbareditboxbuttongeteditbox"></a><a name="geteditbox"></a>CMFCToolBarEditBoxButton::GetEditBox  
 Gibt einen Zeiger auf die [CEdit Class](../../mfc/reference/cedit-class.md) -Steuerelement, das auf der Schaltfläche eingebettet ist.  
  
```  
CEdit* GetEditBox() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die [CEdit Class](../../mfc/reference/cedit-class.md) -Steuerelement, das die Schaltfläche enthält. Es ist `NULL` Wenn das `CEdit` Steuerelement noch nicht erstellt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Erstellen Sie die `CEdit` durch Aufrufen [CMFCToolBarEditBoxButton::CreateEdit](#createedit).  
  
##  <a name="a-namegethwnda--cmfctoolbareditboxbuttongethwnd"></a><a name="gethwnd"></a>CMFCToolBarEditBoxButton::GetHwnd  
 Ruft das Fensterhandle, das dem die Symbolleisten-Schaltfläche zugeordnet ist.  
  
```  
virtual HWND GetHwnd();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Fensterhandle, das der Schaltfläche zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) -Methode des Fensterhandles des Teils der Bearbeitungsschaltfläche im Feld bearbeiten.  
  
##  <a name="a-namegetinvalidaterecta--cmfctoolbareditboxbuttongetinvalidaterect"></a><a name="getinvalidaterect"></a>CMFCToolBarEditBoxButton::GetInvalidateRect  
 Ruft den Bereich des Clientbereichs der Schaltfläche, die neu gezeichnet werden muss.  
  
```  
virtual const CRect GetInvalidateRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CRect` -Objekt, das den Bereich angibt, der neu gezeichnet werden muss.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die Implementierung der Basisklasse [CMFCToolBarButton::GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect), indem einschließlich in der Region des Bereichs, der die Beschriftung.  
  
##  <a name="a-namehavehotbordera--cmfctoolbareditboxbuttonhavehotborder"></a><a name="havehotborder"></a>CMFCToolBarEditBoxButton::HaveHotBorder  
 Bestimmt, ob ein Rahmen der Schaltfläche angezeigt wird, wenn ein Benutzer auf die Schaltfläche klickt.  
  
```  
virtual BOOL HaveHotBorder() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn eine Schaltfläche eine Rahmenlinie bei Auswahl angezeigt; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die Implementierung der Basisklasse [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder), indem Sie einen Wert ungleich NULL zurückgeben, wenn das Steuerelement sichtbar ist.  
  
##  <a name="a-nameisflatmodea--cmfctoolbareditboxbuttonisflatmode"></a><a name="isflatmode"></a>CMFCToolBarEditBoxButton::IsFlatMode  
 Bestimmt, ob bearbeiten Schaltflächen flach haben.  
  
```  
static BOOL __stdcall IsFlatMode();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn alle Schaltflächen flach sind; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig haben die Schaltflächen Bearbeiten flach. Verwenden der [CMFCToolBarEditBoxButton::SetFlatMode](#setflatmode) Methode, um die flache Darstellung für Ihre Anwendung zu ändern.  
  
##  <a name="a-namenotifycommanda--cmfctoolbareditboxbuttonnotifycommand"></a><a name="notifycommand"></a>CMFCToolBarEditBoxButton::NotifyCommand  
 Gibt an, ob die Schaltfläche verarbeitet die [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Nachricht.  
  
```  
virtual BOOL NotifyCommand(int iNotifyCode);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iNotifyCode`  
 Die Nachricht, die mit dem Befehl zugeordnet ist.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Schaltfläche verarbeitet die `WM_COMMAND` Nachricht oder `FALSE` an, dass die Nachricht von der übergeordneten Symbolleiste verarbeitet werden muss.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode aus, wenn es senden möchten, ist ein [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Nachricht an das übergeordnete Fenster.  
  
 Diese Methode erweitert die Implementierung der Basisklasse ( [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)) durch die Verarbeitung der [EN_UPDATE](http://msdn.microsoft.com/library/windows/desktop/bb761687) Benachrichtigung. Für jedes Bearbeitungsfeld mit derselben Befehls-ID wie dieses Objekt festgelegt dessen Bezeichnung auf die Beschriftung für dieses Objekt.  
  
##  <a name="a-nameonaddtocustomizepagea--cmfctoolbareditboxbuttononaddtocustomizepage"></a><a name="onaddtocustomizepage"></a>CMFCToolBarEditBoxButton::OnAddToCustomizePage  
 Vom Framework aufgerufen, wenn die Schaltfläche hinzugefügt wird ein **anpassen** Dialogfeld.  
  
```  
virtual void OnAddToCustomizePage();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die Implementierung der Basisklasse ( [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage)) durch Kopieren der Eigenschaften vom Bearbeitungssteuerelement in eine Symbolleiste, die derselben Befehls-ID wie dieses Objekt verfügt. Diese Methode bewirkt nichts, wenn keine Symbolleiste ein Steuerelement mit Eingabefeld mit derselben Befehls-ID wie dieses Objekt besitzt.  
  
 Weitere Informationen zu den **anpassen** Dialogfeld finden Sie unter [CMFCToolBarsCustomizeDialog Klasse](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).  
  
##  <a name="a-nameonchangeparentwnda--cmfctoolbareditboxbuttononchangeparentwnd"></a><a name="onchangeparentwnd"></a>CMFCToolBarEditBoxButton::OnChangeParentWnd  
 Wird vom Framework aufgerufen, wenn eine neue Symbolleiste die Schaltfläche eingefügt wird.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndParent`  
 Ein Zeiger auf den neuen übergeordneten Fenster.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die Implementierung der Basisklasse ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) durch Neuerstellen der internen `CEdit` Objekt.  
  
##  <a name="a-nameonclicka--cmfctoolbareditboxbuttononclick"></a><a name="onclick"></a>CMFCToolBarEditBoxButton::OnClick  
 Vom Framework aufgerufen, wenn der Benutzer die Maustaste klickt.  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 Nicht verwendet.  
  
 [in] `bDelay`  
 Nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Schaltfläche, die auf-Nachricht verarbeitet; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die Implementierung der Basisklasse ( [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)) durch einen Wert ungleich NULL zurückgeben, wenn die interne `CEdit` -Objekt sichtbar ist.  
  
##  <a name="a-nameonctlcolora--cmfctoolbareditboxbuttononctlcolor"></a><a name="onctlcolor"></a>CMFCToolBarEditBoxButton::OnCtlColor  
 Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste behandelt eine `WM_CTLCOLOR` Nachricht.  
  
```  
virtual HBRUSH OnCtlColor(
    CDC* pDC,  
    UINT nCtlColor);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Der Gerätekontext, der die Schaltfläche angezeigt.  
  
 [in] `nCtlColor`  
 Nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für den globalen Fenster Pinsel.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die Implementierung der Basisklasse ( [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)) durch die Text- und Hintergrundfarben des Gerätekontexts bereitgestellten auf die globale Text- und Hintergrundfarben, bzw. festlegen.  
  
 Weitere Informationen zu globalen Optionen, die für Ihre Anwendung verfügbar sind, finden Sie unter [AFX_GLOBAL_DATA-Struktur](../../mfc/reference/afx-global-data-structure.md).  
  
##  <a name="a-nameonglobalfontschangeda--cmfctoolbareditboxbuttononglobalfontschanged"></a><a name="onglobalfontschanged"></a>CMFCToolBarEditBoxButton::OnGlobalFontsChanged  
 Wird vom Framework aufgerufen, wenn die globale Schriftart geändert hat.  
  
```  
virtual void OnGlobalFontsChanged();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die Implementierung der Basisklasse ( [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)) durch Ändern der Schriftart des Steuerelements mit der globalen Schriftart.  
  
 Weitere Informationen zu globalen Optionen, die für Ihre Anwendung verfügbar sind, finden Sie unter [AFX_GLOBAL_DATA-Struktur](../../mfc/reference/afx-global-data-structure.md).  
  
##  <a name="a-nameonmovea--cmfctoolbareditboxbuttononmove"></a><a name="onmove"></a>CMFCToolBarEditBoxButton::OnMove  
 Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste verschoben wird.  
  
```  
virtual void OnMove();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die Implementierung der Klasse ( [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)) aktualisieren Sie die Position des internen `CEdit` Objekt  
  
##  <a name="a-nameonshowa--cmfctoolbareditboxbuttononshow"></a><a name="onshow"></a>CMFCToolBarEditBoxButton::OnShow  
 Vom Framework aufgerufen, wenn die Schaltfläche wird sichtbar oder unsichtbar.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bShow`  
 Gibt an, ob die Schaltfläche sichtbar ist. Wenn dieser Parameter ist `TRUE`, die Schaltfläche sichtbar ist. Andernfalls ist die Schaltfläche nicht angezeigt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die Implementierung der Basisklasse ( [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)) durch die Schaltfläche anzeigen, wenn `bShow` ist `TRUE`. Diese Methode ist, andernfalls die Schaltfläche ausgeblendet.  
  
##  <a name="a-nameonsizea--cmfctoolbareditboxbuttononsize"></a><a name="onsize"></a>CMFCToolBarEditBoxButton::OnSize  
 Wird vom Framework aufgerufen, wenn die übergeordneten Symbolleiste seine Größe ändert oder Position und diese Änderung bewirkt, dass die Schaltfläche, um die Größe zu ändern.  
  
```  
virtual void OnSize(int iSize);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iSize`  
 Die neue Breite der Schaltfläche in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die standardmäßige Implementierung der Klasse [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize), durch die Aktualisierung der Größe und Position des internen `CEdit` Objekt.  
  
##  <a name="a-nameonupdatetooltipa--cmfctoolbareditboxbuttononupdatetooltip"></a><a name="onupdatetooltip"></a>CMFCToolBarEditBoxButton::OnUpdateToolTip  
 Wird vom Framework aufgerufen, wenn die übergeordneten Symbolleiste den QuickInfotext aktualisiert.  
  
```  
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,  
    int iButtonIndex,  
    CToolTipCtrl& wndToolTip,  
    CString& str);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndParent`  
 Nicht verwendet.  
  
 [in] `iButtonIndex`  
 Nicht verwendet.  
  
 [in] `wndToolTip`  
 Das Steuerelement, das den QuickInfo-Text anzeigt.  
  
 [out] `str`  
 Ein `CString` -Objekt, das den aktualisierten QuickInfo-Text erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Methode den QuickInfo-Text aktualisiert; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die Implementierung der Basisklasse ( [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)) durch Anzeigen des QuickInfo-Texts, der den Teil "Bearbeiten" die Schaltfläche zugeordnet ist. Wenn das interne `CEdit` Objekt `NULL` oder das Fensterhandle der `CEdit` Objekt ein vorhandenes Fenster nicht identifiziert, die diese Methode führt keine Aktion aus und gibt `FALSE`.  
  
##  <a name="a-namesetcontentsa--cmfctoolbareditboxbuttonsetcontents"></a><a name="setcontents"></a>CMFCToolBarEditBoxButton::SetContents  
 Legt den Text in das Textfeld-Steuerelement.  
  
```  
virtual void SetContents(const CString& sContents);
```  
  
### <a name="parameters"></a>Parameter  
 `[in] sContents`  
 Gibt den neuen Text festgelegt.  
  
##  <a name="a-namesetcontentsalla--cmfctoolbareditboxbuttonsetcontentsall"></a><a name="setcontentsall"></a>CMFCToolBarEditBoxButton::SetContentsAll  
 Sucht nach einem [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md) -Objekt, das eine angegebene Befehls-ID hat und legt den angegebenen Text in ein Textfeld.  
  
```  
static BOOL SetContentsAll(
    UINT uiCmd,  
    const CString& strContents);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmd`  
 Gibt die Befehls-ID des Steuerelements für die der Text geändert werden.  
  
 [in] `strContents`  
 Gibt den neuen Text festgelegt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn der Text festgelegt wurde; 0, wenn die `CMFCToolBarEditBoxButton` Steuerelement mit der angegebenen Befehls-ID ist nicht vorhanden.  
  
##  <a name="a-namesetcontextmenuida--cmfctoolbareditboxbuttonsetcontextmenuid"></a><a name="setcontextmenuid"></a>CMFCToolBarEditBoxButton::SetContextMenuID  
 Gibt die Ressourcen-ID des Kontextmenüs, die der Schaltfläche zugeordnet ist.  
  
```  
void SetContextMenuID(UINT uiResID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmd`  
 Die Ressourcen-ID des Kontextmenüs.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verwendet die Ressourcen-ID, um das Kontextmenü zu erstellen, wenn der Benutzer die Symbolleisten-Schaltfläche klickt.  
  
##  <a name="a-namesetflatmodea--cmfctoolbareditboxbuttonsetflatmode"></a><a name="setflatmode"></a>CMFCToolBarEditBoxButton::SetFlatMode  
 Gibt die flache Darstellung des Bearbeitungsschaltflächen in der Anwendung an.  
  
```  
static void __stdcall SetFlatMode(BOOL bFlat = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bFlat`  
 Die flache Darstellung für Bearbeitungsschaltflächen. Wenn dieser Parameter ist `TRUE`, die flache Darstellung aktiviert ist; andernfalls die flache Darstellung deaktiviert ist.  
  
### <a name="remarks"></a>Hinweise  
 Wird von der flachen Standardstil für Bearbeitungsschaltflächen `TRUE`. Verwenden der [CMFCToolBarEditBoxButton::IsFlatMode](#isflatmode) Methode, um die flache Darstellung für Ihre Anwendung abzurufen.  
  
##  <a name="a-namesetstylea--cmfctoolbareditboxbuttonsetstyle"></a><a name="setstyle"></a>CMFCToolBarEditBoxButton::SetStyle  
 Gibt den Stil Symbolleisten-Steuerelement zu bearbeiten.  
  
```  
virtual void SetStyle(UINT nStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nStyle`  
 Eine neue Formatvorlage festgelegt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode legt [CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle) auf `nStyle` es auch im Textfeld deaktiviert, wenn die Anwendung befindet sich im Modus anpassen und es, ermöglicht Wenn die Anwendung nicht im Modus anpassen (finden Sie unter [CMFCToolBar::SetCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#setcustomizemode) und [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)). Finden Sie unter [Steuerelementtypen für die Symbolleiste](../../mfc/reference/toolbar-control-styles.md) eine Liste der gültigen Formatflags.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CEdit-Klasse](../../mfc/reference/cedit-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [Exemplarische Vorgehensweise: Einfügen von Steuerelementen in Symbolleisten](../../mfc/walkthrough-putting-controls-on-toolbars.md)




