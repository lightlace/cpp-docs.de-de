---
title: CMFCToolBarEditBoxButton-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CanBeStretched
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::CopyFrom
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetByCmd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetContentsAll
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetContextMenuID
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetEditBorder
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetHwnd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::GetInvalidateRect
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::HaveHotBorder
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::IsFlatMode
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::NotifyCommand
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnAddToCustomizePage
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnChangeParentWnd
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnClick
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnCtlColor
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnGlobalFontsChanged
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnMove
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnShow
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnSize
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::OnUpdateToolTip
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::SetContextMenuID
- AFXTOOLBAREDITBOXBUTTON/CMFCToolBarEditBoxButton::SetFlatMode
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarEditBoxButton [MFC], CMFCToolBarEditBoxButton
- CMFCToolBarEditBoxButton [MFC], CanBeStretched
- CMFCToolBarEditBoxButton [MFC], CopyFrom
- CMFCToolBarEditBoxButton [MFC], GetByCmd
- CMFCToolBarEditBoxButton [MFC], GetContentsAll
- CMFCToolBarEditBoxButton [MFC], GetContextMenuID
- CMFCToolBarEditBoxButton [MFC], GetEditBorder
- CMFCToolBarEditBoxButton [MFC], GetHwnd
- CMFCToolBarEditBoxButton [MFC], GetInvalidateRect
- CMFCToolBarEditBoxButton [MFC], HaveHotBorder
- CMFCToolBarEditBoxButton [MFC], IsFlatMode
- CMFCToolBarEditBoxButton [MFC], NotifyCommand
- CMFCToolBarEditBoxButton [MFC], OnAddToCustomizePage
- CMFCToolBarEditBoxButton [MFC], OnChangeParentWnd
- CMFCToolBarEditBoxButton [MFC], OnClick
- CMFCToolBarEditBoxButton [MFC], OnCtlColor
- CMFCToolBarEditBoxButton [MFC], OnGlobalFontsChanged
- CMFCToolBarEditBoxButton [MFC], OnMove
- CMFCToolBarEditBoxButton [MFC], OnShow
- CMFCToolBarEditBoxButton [MFC], OnSize
- CMFCToolBarEditBoxButton [MFC], OnUpdateToolTip
- CMFCToolBarEditBoxButton [MFC], SetContextMenuID
- CMFCToolBarEditBoxButton [MFC], SetFlatMode
ms.assetid: b21d9b67-6bf7-4ca9-bd62-b237756e0ab3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 928e2845321ad12a92e4ba3f42838b3f468dce70
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215514"
---
# <a name="cmfctoolbareditboxbutton-class"></a>CMFCToolBarEditBoxButton-Klasse
Eine Symbolleisten-Schaltfläche, die ein Bearbeitungssteuerelement enthält ( [CEdit-Klasse](../../mfc/reference/cedit-class.md)).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCToolBarEditBoxButton : public CMFCToolBarButton  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton](#cmfctoolbareditboxbutton)|Erstellt ein `CMFCToolBarEditBoxButton`-Objekt.|  
|`CMFCToolBarEditBoxButton::~CMFCToolBarEditBoxButton`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarEditBoxButton::CanBeStretched](#canbestretched)|Gibt an, ob ein Benutzer während der Anpassung die Schaltfläche gestreckt werden kann. (Überschreibt [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched).)|  
|[CMFCToolBarEditBoxButton::CopyFrom](#copyfrom)|Kopiert die Eigenschaften von einer anderen Symbolleistenschaltfläche, auf die Schaltfläche "aktuelle". (Überschreibt [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::CreateEdit](#createedit)|Erstellt ein neues Bearbeitungssteuerelement in der Schaltfläche.|  
|`CMFCToolBarEditBoxButton::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCToolBarEditBoxButton::GetByCmd](#getbycmd)|Ruft das erste `CMFCToolBarEditBoxButton` Objekt in der Anwendung, die die angegebene Befehls-ID|  
|[CMFCToolBarEditBoxButton::GetContentsAll](#getcontentsall)|Ruft den Text des ersten bearbeiten Symbolleisten-Steuerelements, die die angegebene Befehls-ID ab|  
|[CMFCToolBarEditBoxButton::GetContextMenuID](#getcontextmenuid)|Ruft ab, die Ressourcen-ID des Kontextmenüs, die mit der Schaltfläche zugeordnet ist.|  
|[CMFCToolBarEditBoxButton::GetEditBorder](#geteditborder)|Ruft das umschließende Rechteck des Teils der Schaltfläche "Bearbeiten-Feld" Bearbeiten.|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::GetEditBox](#geteditbox)|Gibt einen Zeiger auf das Steuerelement zum Bearbeiten, das in der Schaltfläche eingebettet ist.|  
|[CMFCToolBarEditBoxButton::GetHwnd](#gethwnd)|Ruft das Fensterhandle, das die Symbolleisten-Schaltfläche zugeordnet ist. (Überschreibt [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).)|  
|[CMFCToolBarEditBoxButton::GetInvalidateRect](#getinvalidaterect)|Ruft ab, die Region des Clientbereichs der Schaltfläche, die neu gezeichnet werden muss. (Überschreibt [CMFCToolBarButton::GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect).)|  
|`CMFCToolBarEditBoxButton::GetThisClass`|Durch das Framework verwendet wird, einen Zeiger zum Abrufen der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|[CMFCToolBarEditBoxButton::HaveHotBorder](#havehotborder)|Bestimmt, ob ein Rahmen der Schaltfläche angezeigt wird, wenn ein Benutzer die Schaltfläche klickt. (Überschreibt [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|  
|[CMFCToolBarEditBoxButton::IsFlatMode](#isflatmode)|Bestimmt, ob bearbeiten Schaltflächen flach haben.|  
|[CMFCToolBarEditBoxButton::NotifyCommand](#notifycommand)|Gibt an, ob die Schaltfläche mit der verarbeitet die [WM_COMMAND](/windows/desktop/menurc/wm-command) Nachricht. (Überschreibt [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).)|  
|[CMFCToolBarEditBoxButton::OnAddToCustomizePage](#onaddtocustomizepage)|Vom Framework aufgerufen, wenn die Schaltfläche hinzugefügt wird eine **anpassen** Dialogfeld. (Überschreibt [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|  
|`CMFCToolBarEditBoxButton::OnCalculateSize`|Wird aufgerufen, durch das Framework die Größe der Schaltfläche für den angegebenen Gerätekontext und Andockstatus berechnet. (Überschreibt [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|  
|[CMFCToolBarEditBoxButton::OnChangeParentWnd](#onchangeparentwnd)|Vom Framework aufgerufen, wenn die Schaltfläche mit der in eine neue Symbolleiste eingefügt wird. (Überschreibt [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|  
|[CMFCToolBarEditBoxButton::OnClick](#onclick)|Vom Framework aufgerufen, wenn der Benutzer die Maustaste klickt. (Überschreibt [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|  
|[CMFCToolBarEditBoxButton::OnCtlColor](#onctlcolor)|Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste WM_CTLCOLOR-Meldung verarbeitet. (Überschreibt [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).)|  
|`CMFCToolBarEditBoxButton::OnDraw`|Wird aufgerufen, durch das Framework zum Zeichnen der Schaltfläche mit der angegebenen Formate und -Optionen. (Überschreibt [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|  
|`CMFCToolBarEditBoxButton::OnDrawOnCustomizeList`|Wird aufgerufen, durch das Framework zum Zeichnen der Schaltfläche der **Befehle** im Bereich der **anpassen** im Dialogfeld. (Überschreibt [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|  
|[CMFCToolBarEditBoxButton::OnGlobalFontsChanged](#onglobalfontschanged)|Vom Framework aufgerufen, wenn die globale Schriftart geändert hat. (Überschreibt [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged).)|  
|[CMFCToolBarEditBoxButton::OnMove](#onmove)|Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste verschoben wird. (Überschreibt [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|  
|[CMFCToolBarEditBoxButton::OnShow](#onshow)|Vom Framework aufgerufen, wird die Schaltfläche mit der ein- oder ausgeblendet. (Überschreibt [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|  
|[CMFCToolBarEditBoxButton::OnSize](#onsize)|Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste die Größe ändert oder Position und diese Änderung führt dazu, dass die Schaltfläche, um die Größe zu ändern. (Überschreibt [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|  
|[CMFCToolBarEditBoxButton::OnUpdateToolTip](#onupdatetooltip)|Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste den QuickInfotext aktualisiert. (Überschreibt [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|  
|`CMFCToolBarEditBoxButton::Serialize`|Dieses Objekt aus einem Archiv liest oder schreibt dieses in ein Archiv. (Überschreibt [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|  
|`CMFCToolBarEditBoxButton::SetACCData`|Füllt die angegebene `CAccessibilityData` Objekt mit Zugriff auf Daten aus der Symbolleisten-Schaltfläche. (Überschreibt [CMFCToolBarButton::SetACCData](../../mfc/reference/cmfctoolbarbutton-class.md#setaccdata).)|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetContents](#setcontents)|Legt den Text im Bearbeitungssteuerelement der Schaltfläche fest.|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetContentsAll](#setcontentsall)|Sucht nach der Schaltfläche "Bearbeiten-Steuerelement", die eine angegebene Befehls-ID, und legt den Text in das Steuerelement zum Bearbeiten der Schaltfläche.|  
|[CMFCToolBarEditBoxButton::SetContextMenuID](#setcontextmenuid)|Gibt an, die Ressourcen-ID des Kontextmenüs, die mit der Schaltfläche zugeordnet ist.|  
|[CMFCToolBarEditBoxButton::SetFlatMode](#setflatmode)|Gibt die flache Darstellung der Bearbeitungsschaltflächen in der Anwendung an.|  
|`CMFCToolBarEditBoxButton::` [CMFCToolBarEditBoxButton::SetStyle](#setstyle)|Gibt den Stil der Schaltfläche. (Überschreibt [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|  
  
## <a name="remarks"></a>Hinweise  
 Um eine Bearbeiten-Box-Schaltfläche einer Symbolleiste hinzuzufügen, gehen Sie folgendermaßen vor:  
  
 1. Reservieren Sie eine Platzhalterressourcen-ID für die Schaltfläche in der übergeordneten Symbolleistenressource.  
  
 2. Konstruieren Sie ein `CMFCToolBarEditBoxButton`-Objekt.  
  
 3. Ersetzen Sie in der Message-Handler, die die AFX_WM_RESETTOOLBAR-Nachricht verarbeitet, die Schaltfläche "dummy" mit der neuen kombinationsfeldschaltfläche mit [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).  
  
 Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Einfügen von Steuerelementen auf Symbolleisten](../../mfc/walkthrough-putting-controls-on-toolbars.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCToolBarEditBoxButton` Klasse. Das Beispiel veranschaulicht, um anzugeben, dass ein Benutzer kann Dehnen die Schaltfläche mit den während der Anpassung, anzugeben, dass ein Rahmen der Schaltfläche angezeigt wird, wenn ein Benutzer die Schaltfläche klickt, legen Sie den Text in das Textfeld-Steuerelement, geben Sie die flache Darstellung der Bearbeitungsschaltflächen, in der anwendungse Speicherort, und geben Sie den Stil einer Symbolleiste bearbeiten-Steuerelement.  
  
 [!code-cpp[NVC_MFC_RibbonApp#40](../../mfc/reference/codesnippet/cpp/cmfctoolbareditboxbutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 `CMFCToolBarEditBoxButton` 
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtoolbareditboxbutton.h  
  
##  <a name="canbestretched"></a>  CMFCToolBarEditBoxButton::CanBeStretched  
 Gibt an, ob ein Benutzer während der Anpassung die Schaltfläche gestreckt werden kann.  
  
```  
virtual BOOL CanBeStretched() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt "true" zurück.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig lässt sich das Framework nicht auf den Benutzer eine Symbolleisten-Schaltfläche gestreckt wird, während der Anpassung aus. Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)) von dem der Benutzer eine Bearbeiten-Box-Symbolleisten-Schaltfläche gestreckt wird, während der Anpassung.  
  
##  <a name="cmfctoolbareditboxbutton"></a>  CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton  
 Erstellt eine [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md) Objekt.  
  
```  
CMFCToolBarEditBoxButton(
    UINT uiID,  
    int iImage,  
    DWORD dwStyle=ES_AUTOHSCROLL,  
    int iWidth=0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *UiID*  
 Gibt an, die Steuerelement-ID.  
  
 [in] *iImage*  
 Gibt den nullbasierten Index des ein Symbolleistenbild an. Das Image befindet sich in der [CMFCToolBarImages-Klasse](../../mfc/reference/cmfctoolbarimages-class.md) -Objekt, [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md) -Klasse verwaltet.  
  
 [in] *DwStyle*  
 Gibt die Art der Edit-Steuerelement.  
  
 [in] *iWidth*  
 Gibt die Breite in Pixel des Edit-Steuerelements.  
  
### <a name="remarks"></a>Hinweise  
 Der Standardkonstruktor legt den Stil des bearbeiten-Steuerelement fest, um die folgende Kombination:  
  
 WS_CHILD | WS_VISIBLE | ES_AUTOHSCROLL  
  
 Die Standardbreite des Steuerelements ist 150 Pixel.  
  
##  <a name="copyfrom"></a>  CMFCToolBarEditBoxButton::CopyFrom  
 Kopiert die Eigenschaften von einer anderen Symbolleistenschaltfläche, auf die Schaltfläche "aktuelle".  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *Src*  
 Ein Verweis auf die Schaltfläche "Quelle", aus dem kopiert werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Kopieren von einer anderen Symbolleistenschaltfläche diese Symbolleisten-Schaltfläche auf. *Src* muss vom Typ `CMFCToolBarEditBoxButton`.  
  
##  <a name="createedit"></a>  CMFCToolBarEditBoxButton::CreateEdit  
 Erstellt ein neues Bearbeitungssteuerelement in der Schaltfläche.  
  
```  
virtual CEdit* CreateEdit(
    CWnd* pWndParent,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pWndParent*  
 Gibt das übergeordnete Fenster des Edit-Steuerelements an. Es darf nicht NULL sein.  
  
 [in] *Rect*  
 Gibt an, des Steuerelements zum Bearbeiten der Größe und Position.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das neu erstellte Bearbeitungssteuerelement; Es ist NULL, wenn Erstellung und das Anfügen des Steuerelements ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CMFCToolBarEditBoxButton` Objekt in zwei Schritten. Rufen Sie zunächst den Konstruktor, und rufen dann `CreateEdit`, die das Steuerelement zum Bearbeiten von Windows erstellt, und fügt es der `CMFCToolBarEditBoxButton` Objekt.  
  
##  <a name="getbycmd"></a>  CMFCToolBarEditBoxButton::GetByCmd  
 Ruft das erste `CMFCToolBarEditBoxButton` Objekt in der Anwendung, die die angegebene Befehls-ID  
  
```  
static CMFCToolBarEditBoxButton* __stdcall GetByCmd(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *UiCmd*  
 Die Befehls-ID der Schaltfläche zum Abrufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste `CMFCToolBarEditBoxButton` Objekt in der Anwendung, die der angegebenen Befehls-ID oder NULL, wenn kein entsprechendes Objekt vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese gemeinsam genutzte Dienstprogramme-Methode wird von Methoden verwendet, z. B. [CMFCToolBarEditBoxButton::SetContentsAll](#setcontentsall) und [CMFCToolBarEditBoxButton::GetContentsAll](#getcontentsall) festlegen oder Abrufen des Texts von der Symbolleiste des ersten bearbeiten -Steuerelement mit der angegebenen Befehls-ID.  
  
##  <a name="getcontentsall"></a>  CMFCToolBarEditBoxButton::GetContentsAll  
 Ruft den Text des ersten bearbeiten Symbolleisten-Steuerelements, die die angegebene Befehls-ID ab  
  
```  
static CString __stdcall GetContentsAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *UiCmd*  
 Die Befehls-ID der Schaltfläche aus dem Inhalt abgerufen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` Objekt, das den Text des ersten bearbeiten Symbolleisten-Steuerelements enthält, die die angegebene Befehls-ID  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt die leere Zeichenfolge zurück, wenn kein `CMFCToolBarEditBoxButton` Objekte verfügen über die angegebene Befehls-ID  
  
##  <a name="getcontextmenuid"></a>  CMFCToolBarEditBoxButton::GetContextMenuID  
 Ruft ab, die Ressourcen-ID des Kontextmenüs, die mit der Schaltfläche zugeordnet ist.  
  
```  
UINT GetContextMenuID();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Ressourcen-ID des Kontextmenüs, die auf die Schaltfläche oder 0 zugeordnet ist, wenn die Schaltfläche "keine zugeordnete Kontextmenü verfügt.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verwendet die Ressourcen-ID, um im Kontextmenü den Befehl zu erstellen, wenn der Benutzer auf die Schaltfläche klickt.  
  
##  <a name="geteditborder"></a>  CMFCToolBarEditBoxButton::GetEditBorder  
 Ruft das umschließende Rechteck des Teils der Schaltfläche "Bearbeiten-Feld" Bearbeiten.  
  
```  
virtual void GetEditBorder(CRect& rectBorder);
```  
  
### <a name="parameters"></a>Parameter  
 [out] *RectBorder*  
 Ein Verweis auf die `CRect` Objekt, das das umschließende Rechteck empfängt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft das umschließende Rechteck des Edit-Steuerelements in Clientkoordinaten ab. Es erweitert die Größe des Rechtecks in jede Richtung um ein Pixel.  
  
 Die [CMFCVisualManager::OnDrawEditBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondraweditborder) -Methode ruft diese Methode auf, wenn es sich um Rahmens zeichnet eine `CMFCToolBarEditBoxButton` Objekt.  
  
##  <a name="geteditbox"></a>  CMFCToolBarEditBoxButton::GetEditBox  
 Gibt einen Zeiger auf die [CEdit-Klasse](../../mfc/reference/cedit-class.md) -Steuerelement, das in der Schaltfläche eingebettet ist.  
  
```  
CEdit* GetEditBox() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die [CEdit-Klasse](../../mfc/reference/cedit-class.md) -Steuerelement, das die Schaltfläche enthält. Ist NULL, wenn die `CEdit` Steuerelement noch nicht erstellt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen die `CEdit` Steuerelement durch Aufrufen von [CMFCToolBarEditBoxButton::CreateEdit](#createedit).  
  
##  <a name="gethwnd"></a>  CMFCToolBarEditBoxButton::GetHwnd  
 Ruft das Fensterhandle, das die Symbolleisten-Schaltfläche zugeordnet ist.  
  
```  
virtual HWND GetHwnd();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Fensterhandle, das die Schaltfläche zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) Methode, indem Sie das Fensterhandle des bearbeiten-Steuerelement Teils der Schaltfläche "Bearbeiten-Feld" zurückgeben.  
  
##  <a name="getinvalidaterect"></a>  CMFCToolBarEditBoxButton::GetInvalidateRect  
 Ruft ab, die Region des Clientbereichs der Schaltfläche, die neu gezeichnet werden muss.  
  
```  
virtual const CRect GetInvalidateRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CRect` -Objekt, das die Region gibt an, der neu gezeichnet werden muss.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die basisklassenimplementierung [CMFCToolBarButton::GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect), durch einschließlich in der Region des Bereichs der textbezeichnung.  
  
##  <a name="havehotborder"></a>  CMFCToolBarEditBoxButton::HaveHotBorder  
 Bestimmt, ob ein Rahmen der Schaltfläche angezeigt wird, wenn ein Benutzer die Schaltfläche klickt.  
  
```  
virtual BOOL HaveHotBorder() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn eine Schaltfläche anzeigt, dessen Rahmen aus, wenn ausgewählt wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die basisklassenimplementierung [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder), durch einen Wert ungleich NULL zurückgeben, wenn das Steuerelement sichtbar ist.  
  
##  <a name="isflatmode"></a>  CMFCToolBarEditBoxButton::IsFlatMode  
 Bestimmt, ob bearbeiten Schaltflächen flach haben.  
  
```  
static BOOL __stdcall IsFlatMode();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL ist, wenn Schaltflächen flach sind; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig haben bearbeiten Schaltflächen flach. Verwenden der [CMFCToolBarEditBoxButton::SetFlatMode](#setflatmode) Methode, um die flache Darstellung für Ihre Anwendung zu ändern.  
  
##  <a name="notifycommand"></a>  CMFCToolBarEditBoxButton::NotifyCommand  
 Gibt an, ob die Schaltfläche mit der verarbeitet die [WM_COMMAND](/windows/desktop/menurc/wm-command) Nachricht.  
  
```  
virtual BOOL NotifyCommand(int iNotifyCode);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *iNotifyCode*  
 Die Benachrichtigung, die mit dem Befehl zugeordnet ist.  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE, wenn die Schaltfläche mit der verarbeitet die WM_COMMAND-Meldung oder "false" um anzugeben, dass die Nachricht vom übergeordneten Symbolleiste verarbeitet werden muss.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode aus, wenn es zu senden ist ein [WM_COMMAND](/windows/desktop/menurc/wm-command) Nachricht für das übergeordnete Fenster.  
  
 Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)) durch die Verarbeitung der [EN_UPDATE](/windows/desktop/Controls/en-update) Benachrichtigung. Für jedes Bearbeitungsfeld mit derselben Befehls-ID wie dieses Objekt festgelegt dessen Bezeichnung auf die textbezeichnung des Objekts.  
  
##  <a name="onaddtocustomizepage"></a>  CMFCToolBarEditBoxButton::OnAddToCustomizePage  
 Vom Framework aufgerufen, wenn die Schaltfläche hinzugefügt wird eine **anpassen** Dialogfeld.  
  
```  
virtual void OnAddToCustomizePage();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage)) durch das Bearbeiten-Steuerelement in die Symbolleisten, die derselben Befehls-ID wie dieses Objekt verfügt über die Eigenschaften kopieren. Diese Methode bewirkt nichts, wenn keine Symbolleiste ein Steuerelement mit Eingabefeld mit derselben Befehls-ID wie dieses Objekt besitzt.  
  
 Weitere Informationen zu den **anpassen** im Dialogfeld finden Sie unter [CMFCToolBarsCustomizeDialog-Klasse](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).  
  
##  <a name="onchangeparentwnd"></a>  CMFCToolBarEditBoxButton::OnChangeParentWnd  
 Vom Framework aufgerufen, wenn die Schaltfläche mit der in eine neue Symbolleiste eingefügt wird.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pWndParent*  
 Ein Zeiger auf das neue übergeordnete Fenster.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die basisklassenimplementierung ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) durch Neuerstellen der internen `CEdit` Objekt.  
  
##  <a name="onclick"></a>  CMFCToolBarEditBoxButton::OnClick  
 Vom Framework aufgerufen, wenn der Benutzer die Maustaste klickt.  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *aufnehmen*  
 Nicht verwendet.  
  
 [in] *bDelay*  
 Nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL ist, wenn die Schaltfläche, die auf-Nachricht verarbeitet; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die basisklassenimplementierung ( [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)) durch einen Wert ungleich NULL zurückgeben, wenn die interne `CEdit` Objekt sichtbar ist.  
  
##  <a name="onctlcolor"></a>  CMFCToolBarEditBoxButton::OnCtlColor  
 Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste WM_CTLCOLOR-Meldung verarbeitet.  
  
```  
virtual HBRUSH OnCtlColor(
    CDC* pDC,  
    UINT nCtlColor);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDC*  
 Der Gerätekontext, in dem die Schaltfläche angezeigt.  
  
 [in] *nCtlColor*  
 Nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für den globalen Fenster Pinsel.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die basisklassenimplementierung ( [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)) durch die Text- und Hintergrundfarben des Gerätekontexts bereitgestellten bzw. auf den globalen Text und die Hintergrundfarben, festlegen.  
  
 Weitere Informationen zu globalen Optionen, die für Ihre Anwendung verfügbar sind, finden Sie unter [AFX_GLOBAL_DATA-Struktur](../../mfc/reference/afx-global-data-structure.md).  
  
##  <a name="onglobalfontschanged"></a>  CMFCToolBarEditBoxButton::OnGlobalFontsChanged  
 Vom Framework aufgerufen, wenn die globale Schriftart geändert hat.  
  
```  
virtual void OnGlobalFontsChanged();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)) durch Ändern der Schriftart des Steuerelements mit der globalen Schriftart.  
  
 Weitere Informationen zu globalen Optionen, die für Ihre Anwendung verfügbar sind, finden Sie unter [AFX_GLOBAL_DATA-Struktur](../../mfc/reference/afx-global-data-structure.md).  
  
##  <a name="onmove"></a>  CMFCToolBarEditBoxButton::OnMove  
 Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste verschoben wird.  
  
```  
virtual void OnMove();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die standardmäßige Klasse-Implementierung ( [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)) durch Aktualisieren der Position des internen `CEdit` Objekt  
  
##  <a name="onshow"></a>  CMFCToolBarEditBoxButton::OnShow  
 Vom Framework aufgerufen, wird die Schaltfläche mit der ein- oder ausgeblendet.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bShow*  
 Gibt an, ob die Schaltfläche sichtbar ist. Wenn dieser Parameter TRUE ist, ist die Schaltfläche sichtbar. Andernfalls ist die Schaltfläche nicht sichtbar.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)) durch Anzeigen der Schaltfläche aus, wenn *bShow* ist "true". Diese Methode ist, andernfalls die Schaltfläche ausgeblendet.  
  
##  <a name="onsize"></a>  CMFCToolBarEditBoxButton::OnSize  
 Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste die Größe ändert oder Position und diese Änderung führt dazu, dass die Schaltfläche, um die Größe zu ändern.  
  
```  
virtual void OnSize(int iSize);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *iSize*  
 Die neue Breite der Schaltfläche in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die standardmäßige Klasse-Implementierung, [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize), indem Sie aktualisieren die Größe und Position des internen `CEdit` Objekt.  
  
##  <a name="onupdatetooltip"></a>  CMFCToolBarEditBoxButton::OnUpdateToolTip  
 Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste den QuickInfotext aktualisiert.  
  
```  
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,  
    int iButtonIndex,  
    CToolTipCtrl& wndToolTip,  
    CString& str);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pWndParent*  
 Nicht verwendet.  
  
 [in] *iButtonIndex*  
 Nicht verwendet.  
  
 [in] *WndToolTip*  
 Das Steuerelement, das den QuickInfo-Text anzeigt.  
  
 [out] *str*  
 Ein `CString` Objekt, das den aktualisierten QuickInfo-Text empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Methode den QuickInfo-Text aktualisiert; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)) durch Anzeigen des QuickInfo-Texts, der den Teil "Bearbeiten" die Schaltfläche zugeordnet ist. Wenn die interne `CEdit` Objekt ist NULL oder das Fensterhandle des der `CEdit` Objekt ein vorhandenes Fenster nicht identifiziert, die diese Methode führt keine Aktion aus und gibt FALSE zurück.  
  
##  <a name="setcontents"></a>  CMFCToolBarEditBoxButton::SetContents  
 Legt den Text in das Textfeld-Steuerelement fest.  
  
```  
virtual void SetContents(const CString& sContents);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *sContents*  
 Gibt den neuen Text festlegen.  
  
##  <a name="setcontentsall"></a>  CMFCToolBarEditBoxButton::SetContentsAll  
 Sucht nach einem [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md) Objekt, das eine angegebene Befehls-ID hat und legt den angegebenen Text in ein Textfeld.  
  
```  
static BOOL SetContentsAll(
    UINT uiCmd,  
    const CString& strContents);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *UiCmd*  
 Gibt an, die Befehls-ID des Steuerelements für die der Text geändert wird.  
  
 [in] *StrContents*  
 Gibt den neuen Text festlegen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Text festgelegt wurde; 0, wenn die `CMFCToolBarEditBoxButton` Steuerelement mit der angegebenen Befehls-ID ist nicht vorhanden.  
  
##  <a name="setcontextmenuid"></a>  CMFCToolBarEditBoxButton::SetContextMenuID  
 Gibt an, die Ressourcen-ID des Kontextmenüs, die mit der Schaltfläche zugeordnet ist.  
  
```  
void SetContextMenuID(UINT uiResID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *UiCmd*  
 Die Ressourcen-ID des Kontextmenüs.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verwendet die Ressourcen-ID, um das Kontextmenü zu erstellen, wenn der Benutzer die Symbolleisten-Schaltfläche klickt.  
  
##  <a name="setflatmode"></a>  CMFCToolBarEditBoxButton::SetFlatMode  
 Gibt die flache Darstellung der Bearbeitungsschaltflächen in der Anwendung an.  
  
```  
static void __stdcall SetFlatMode(BOOL bFlat = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bFlat*  
 Die flache für Bearbeitungsschaltflächen. Die flache Darstellung wird aktiviert, wenn dieser Parameter TRUE ist, ist. Andernfalls ist die flache Darstellung deaktiviert.  
  
### <a name="remarks"></a>Hinweise  
 Die flache Standardstil für Bearbeitungsschaltflächen, ist "true". Verwenden der [CMFCToolBarEditBoxButton::IsFlatMode](#isflatmode) Methode, um die flache Darstellung für Ihre Anwendung abzurufen.  
  
##  <a name="setstyle"></a>  CMFCToolBarEditBoxButton::SetStyle  
 Gibt an, den Stil einer Symbolleiste bearbeiten-Steuerelement.  
  
```  
virtual void SetStyle(UINT nStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nStyle*  
 Einen neuen Stil festlegen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode legt [CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle) zu *nStyle* auch deaktiviert das Textfeld ein, wenn die Anwendung befindet sich im Anpassungsmodus und es, ermöglicht Wenn die Anwendung nicht in den Anpassungsmodus (siehe ist[ CMFCToolBar::SetCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#setcustomizemode) und [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)). Finden Sie unter [ToolBar-Steuerelement-Stile](../../mfc/reference/toolbar-control-styles.md) für eine Liste der gültigen Stil-Flags.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CEdit-Klasse](../../mfc/reference/cedit-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [Exemplarische Vorgehensweise: Steuerelemente in eine Symbolleiste einfügen](../../mfc/walkthrough-putting-controls-on-toolbars.md)



