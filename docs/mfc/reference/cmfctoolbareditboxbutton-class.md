---
title: CMFCToolBarEditBoxButton Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
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
caps.latest.revision: "28"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3b659ae9b1abfe98ba393e7252e79336b2bd3cfb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cmfctoolbareditboxbutton-class"></a>CMFCToolBarEditBoxButton-Klasse
Eine Symbolleisten-Schaltfläche, die ein Bearbeitungssteuerelement enthält ( [CEdit-Klasse](../../mfc/reference/cedit-class.md)).  
  
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
|[CMFCToolBarEditBoxButton::CanBeStretched](#canbestretched)|Gibt an, ob ein Benutzer die Schaltfläche mit den während der Anpassung gestreckt werden kann. (Überschreibt [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched).)|  
|[CMFCToolBarEditBoxButton::CopyFrom](#copyfrom)|Kopiert die Eigenschaften von einer anderen Symbolleistenschaltfläche auf die Schaltfläche mit den aktuellen. (Überschreibt [CMFCToolBarButton::CopyFrom](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom).)|  
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton::CreateEdit](#createedit)|Erstellt ein neue Edit-Steuerelement in der Schaltfläche.|  
|`CMFCToolBarEditBoxButton::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCToolBarEditBoxButton::GetByCmd](#getbycmd)|Ruft das erste `CMFCToolBarEditBoxButton` Objekt in der Anwendung mit der angegebenen Befehls-ID.|  
|[CMFCToolBarEditBoxButton::GetContentsAll](#getcontentsall)|Ruft den Text des ersten bearbeiten Feld Symbolleisten-Steuerelements, das die angegebenen Befehls-ID.|  
|[CMFCToolBarEditBoxButton::GetContextMenuID](#getcontextmenuid)|Ruft die Ressourcen-ID des Kontextmenüs, das der Schaltfläche zugeordnet ist.|  
|[CMFCToolBarEditBoxButton::GetEditBorder](#geteditborder)|Ruft das umschließende Rechteck des bearbeiten-Teils, der die Schaltfläche "Feld bearbeiten" ab.|  
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton::GetEditBox](#geteditbox)|Gibt einen Zeiger auf das Steuerelement zum Bearbeiten, das in der Schaltfläche eingebettet ist.|  
|[CMFCToolBarEditBoxButton::GetHwnd](#gethwnd)|Ruft das Fensterhandle, das die Symbolleisten-Schaltfläche zugeordnet ist. (Überschreibt [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd).)|  
|[CMFCToolBarEditBoxButton::GetInvalidateRect](#getinvalidaterect)|Ruft den Bereich des Clientbereichs der Schaltfläche, die neu gezeichnet werden muss. (Überschreibt [CMFCToolBarButton::GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect).)|  
|`CMFCToolBarEditBoxButton::GetThisClass`|Durch das Framework verwendet wird, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|[CMFCToolBarEditBoxButton::HaveHotBorder](#havehotborder)|Bestimmt, ob ein Rahmen der Schaltfläche angezeigt wird, wenn ein Benutzer die Schaltfläche klickt. (Überschreibt [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|  
|[CMFCToolBarEditBoxButton::IsFlatMode](#isflatmode)|Bestimmt, ob Schaltflächen Bearbeiten ein Flatfile-Format haben.|  
|[CMFCToolBarEditBoxButton::NotifyCommand](#notifycommand)|Gibt an, ob die Schaltfläche verarbeitet die [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Nachricht. (Überschreibt [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand).)|  
|[CMFCToolBarEditBoxButton::OnAddToCustomizePage](#onaddtocustomizepage)|Vom Framework aufgerufen, wenn die Schaltfläche "" hinzugefügt wird eine **anpassen** (Dialogfeld). (Überschreibt [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|  
|`CMFCToolBarEditBoxButton::OnCalculateSize`|Wird aufgerufen, durch das Framework die Größe der Schaltfläche für den angegebenen Gerätekontext und andockzustand berechnet. (Überschreibt [CMFCToolBarButton::OnCalculateSize](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|  
|[CMFCToolBarEditBoxButton::OnChangeParentWnd](#onchangeparentwnd)|Vom Framework aufgerufen, wenn die Schaltfläche "" in eine neue Symbolleiste eingefügt wird. (Überschreibt [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|  
|[CMFCToolBarEditBoxButton::OnClick](#onclick)|Wird vom Framework aufgerufen, klickt der Benutzer die Maustaste los. (Überschreibt [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|  
|[CMFCToolBarEditBoxButton::OnCtlColor](#onctlcolor)|Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste verarbeitet eine `WM_CTLCOLOR` Nachricht. (Überschreibt [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor).)|  
|`CMFCToolBarEditBoxButton::OnDraw`|Wird aufgerufen, durch das Framework der Schaltfläche gezeichnet werden soll, mithilfe des angegebenen Stile und Optionen. (Überschreibt [CMFCToolBarButton::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|  
|`CMFCToolBarEditBoxButton::OnDrawOnCustomizeList`|Wird aufgerufen, durch das Framework der Schaltfläche gezeichnet werden soll, der **Befehle** im Bereich der **anpassen** (Dialogfeld). (Überschreibt [CMFCToolBarButton::OnDrawOnCustomizeList](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist).)|  
|[CMFCToolBarEditBoxButton::OnGlobalFontsChanged](#onglobalfontschanged)|Vom Framework aufgerufen, wenn die globale Schriftart geändert hat. (Überschreibt [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged).)|  
|[CMFCToolBarEditBoxButton::OnMove](#onmove)|Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste bewegt wird. (Überschreibt [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|  
|[CMFCToolBarEditBoxButton::OnShow](#onshow)|Vom Framework aufgerufen, wenn die Schaltfläche wird ein- oder ausgeblendet. (Überschreibt [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|  
|[CMFCToolBarEditBoxButton::OnSize](#onsize)|Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste seine Größe ändert oder Position und diese Änderung bewirkt, dass die Schaltfläche, um die Größe zu ändern. (Überschreibt [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|  
|[CMFCToolBarEditBoxButton::OnUpdateToolTip](#onupdatetooltip)|Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste die QuickInfo-Text aktualisiert. (Überschreibt [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|  
|`CMFCToolBarEditBoxButton::Serialize`|Dieses Objekt aus einem Archiv liest oder schreibt sie in ein Archiv. (Überschreibt [CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|  
|`CMFCToolBarEditBoxButton::SetACCData`|Füllt die angegebene `CAccessibilityData` Objekt mit Zugriff auf Daten aus der Symbolleisten-Schaltfläche. (Überschreibt [CMFCToolBarButton::SetACCData](../../mfc/reference/cmfctoolbarbutton-class.md#setaccdata).)|  
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton::SetContents](#setcontents)|Legt den Text im Bearbeitungssteuerelement der Schaltfläche fest.|  
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton::SetContentsAll](#setcontentsall)|Sucht nach der Schaltfläche "Bearbeiten-Steuerelement", die eine angegebene Befehls-ID und legt den Text im Bearbeitungssteuerelement der Schaltfläche fest.|  
|[CMFCToolBarEditBoxButton::SetContextMenuID](#setcontextmenuid)|Gibt die Ressourcen-ID des Kontextmenüs, das der Schaltfläche zugeordnet ist.|  
|[CMFCToolBarEditBoxButton::SetFlatMode](#setflatmode)|Gibt die flache Darstellung des bearbeiten-Schaltflächen in der Anwendung an.|  
|`CMFCToolBarEditBoxButton::`[CMFCToolBarEditBoxButton::SetStyle](#setstyle)|Gibt die Art der Schaltfläche. (Überschreibt [CMFCToolBarButton::SetStyle](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|  
  
## <a name="remarks"></a>Hinweise  
 Um eine Symbolleiste eine Schaltfläche zum Bearbeiten im Feld hinzugefügt haben, gehen Sie folgendermaßen vor:  
  
 1. Reservieren Sie eine Platzhalterressourcen-ID für die Schaltfläche in der übergeordneten Symbolleistenressource.  
  
 2. Konstruieren Sie ein `CMFCToolBarEditBoxButton`-Objekt.  
  
 3. In der Message-Handler, der verarbeitet die `AFX_WM_RESETTOOLBAR` angezeigt wird, ersetzen Sie die Schaltfläche "dummy" mit der neuen kombinationsfeldschaltfläche mit [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).  
  
 Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Einfügen von Steuerelementen auf Symbolleisten](../../mfc/walkthrough-putting-controls-on-toolbars.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCToolBarEditBoxButton` Klasse. Im Beispiel veranschaulicht, um anzugeben, dass ein Benutzer kann Dehnen die Schaltfläche mit den während der Anpassung, anzugeben, dass ein Rahmen der Schaltfläche angezeigt wird, wenn ein Benutzer die Schaltfläche klickt, den Text in das Textfeld-Steuerelement festlegen, geben Sie in der anwe die flache Darstellung des Schaltflächen Bearbeiten Speicherort, und geben Sie den Stil Symbolleisten-Steuerelement zu bearbeiten.  
  
 [!code-cpp[NVC_MFC_RibbonApp#40](../../mfc/reference/codesnippet/cpp/cmfctoolbareditboxbutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 `CMFCToolBarEditBoxButton` 
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtoolbareditboxbutton.h  
  
##  <a name="canbestretched"></a>CMFCToolBarEditBoxButton::CanBeStretched  
 Gibt an, ob ein Benutzer die Schaltfläche mit den während der Anpassung gestreckt werden kann.  
  
```  
virtual BOOL CanBeStretched() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt `TRUE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig lässt das Framework nicht den Benutzer, eine Symbolleisten-Schaltfläche während der Anpassung zu Strecken. Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::CanBeStretched](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)) indem der Benutzer, eine Schaltfläche zum Bearbeiten im Feld Symbolleiste während der Anpassung zu Strecken.  
  
##  <a name="cmfctoolbareditboxbutton"></a>CMFCToolBarEditBoxButton::CMFCToolBarEditBoxButton  
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
 Gibt an, die Steuerelement-ID.  
  
 [in] `iImage`  
 Gibt den nullbasierten Index des ein Symbolleistenbild an. Image befindet sich der [CMFCToolBarImages Klasse](../../mfc/reference/cmfctoolbarimages-class.md) Objekt, mit [CMFCToolBar Klasse](../../mfc/reference/cmfctoolbar-class.md) -Klasse verwaltet.  
  
 [in] `dwStyle`  
 Gibt das Format des Steuerelements bearbeiten.  
  
 [in] `iWidth`  
 Gibt die Breite in Pixel des Bearbeitungssteuerelements an.  
  
### <a name="remarks"></a>Hinweise  
 Der Standardkonstruktor legt das Format des Steuerelements bearbeiten, um die folgende Kombination:  
  
 `WS_CHILD | WS_VISIBLE | ES_AUTOHSCROLL`  
  
 Die Standardbreite des Steuerelements beträgt 150 Pixel.  
  
##  <a name="copyfrom"></a>CMFCToolBarEditBoxButton::CopyFrom  
 Kopiert die Eigenschaften von einer anderen Symbolleistenschaltfläche auf die Schaltfläche mit den aktuellen.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `src`  
 Ein Verweis auf die Schaltfläche "Quelle" aus dem kopiert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Kopieren von einer anderen Symbolleistenschaltfläche diese Symbolleisten-Schaltfläche. `src`muss vom Typ `CMFCToolBarEditBoxButton`.  
  
##  <a name="createedit"></a>CMFCToolBarEditBoxButton::CreateEdit  
 Erstellt ein neue Edit-Steuerelement in der Schaltfläche.  
  
```  
virtual CEdit* CreateEdit(
    CWnd* pWndParent,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Parameter  
 `[in] pWndParent`  
 Gibt das übergeordnete Fenster des Bearbeitungssteuerelements an. Es darf nicht NULL sein.  
  
 `[in] rect`  
 Gibt des Bearbeitungssteuerelements Größe und Position.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das neu erstellte Bearbeitungssteuerelement; Es ist `NULL` Wenn Erstellung und der Anlage des Steuerelements ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CMFCToolBarEditBoxButton` Objekt in zwei Schritten. Rufen Sie zunächst den Konstruktor aus, und rufen Sie dann `CreateEdit`, die die Windows-Bearbeitungssteuerelements erstellt, und fügt es der `CMFCToolBarEditBoxButton` Objekt.  
  
##  <a name="getbycmd"></a>CMFCToolBarEditBoxButton::GetByCmd  
 Ruft das erste `CMFCToolBarEditBoxButton` Objekt in der Anwendung mit der angegebenen Befehls-ID.  
  
```  
static CMFCToolBarEditBoxButton* __stdcall GetByCmd(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmd`  
 Die Befehls-ID der Schaltfläche abgerufen.  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste `CMFCToolBarEditBoxButton` Objekt in der Anwendung mit der angegebenen Befehls-ID oder `NULL` Wenn kein solches Objekt vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese freigegebenen Utility-Methode wird von Methoden verwendet, z. B. [CMFCToolBarEditBoxButton::SetContentsAll](#setcontentsall) und [CMFCToolBarEditBoxButton::GetContentsAll](#getcontentsall) festlegen oder Abrufen des Texts von der Symbolleiste des ersten bearbeiten -Steuerelement mit der angegebenen Befehls-ID.  
  
##  <a name="getcontentsall"></a>CMFCToolBarEditBoxButton::GetContentsAll  
 Ruft den Text des ersten bearbeiten Feld Symbolleisten-Steuerelements, das die angegebenen Befehls-ID.  
  
```  
static CString __stdcall GetContentsAll(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmd`  
 Die Befehls-ID der Schaltfläche aus der Inhalt abgerufen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` -Objekt, das den Text des ersten bearbeiten Symbolleisten-Steuerelements enthält, die die angegebenen Befehls-ID.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt die leere Zeichenfolge zurück, wenn keine `CMFCToolBarEditBoxButton` Objekte verfügen über die angegebene Befehls-ID.  
  
##  <a name="getcontextmenuid"></a>CMFCToolBarEditBoxButton::GetContextMenuID  
 Ruft die Ressourcen-ID des Kontextmenüs, das der Schaltfläche zugeordnet ist.  
  
```  
UINT GetContextMenuID();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Ressourcen-ID des Kontextmenüs, die mit der Schaltfläche oder 0 verknüpft ist, wenn die Schaltfläche "" keine zugeordnete Kontextmenü umfasst.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verwendet die Ressourcen-ID, um das Kontextmenü zu erstellen, wenn der Benutzer auf die Schaltfläche klickt.  
  
##  <a name="geteditborder"></a>CMFCToolBarEditBoxButton::GetEditBorder  
 Ruft das umschließende Rechteck des bearbeiten-Teils, der die Schaltfläche "Feld bearbeiten" ab.  
  
```  
virtual void GetEditBorder(CRect& rectBorder);
```  
  
### <a name="parameters"></a>Parameter  
 [out] `rectBorder`  
 Ein Verweis auf die `CRect` Objekt, das das umschließende Rechteck empfängt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft das umschließende Rechteck des Bearbeitungssteuerelements in Clientkoordinaten ab. Es erweitert die Größe des Rechtecks in jede Richtung um ein Pixel.  
  
 Die [CMFCVisualManager::OnDrawEditBorder](../../mfc/reference/cmfcvisualmanager-class.md#ondraweditborder) Methode ruft diese Methode auf, wenn es sich um den Rahmen zeichnet einen `CMFCToolBarEditBoxButton` Objekt.  
  
##  <a name="geteditbox"></a>CMFCToolBarEditBoxButton::GetEditBox  
 Gibt einen Zeiger auf die [CEdit-Klasse](../../mfc/reference/cedit-class.md) Steuerelement, das in der Schaltfläche eingebettet ist.  
  
```  
CEdit* GetEditBox() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die [CEdit-Klasse](../../mfc/reference/cedit-class.md) Steuerelement, das die Schaltfläche enthält. Es ist `NULL` Wenn die `CEdit` Steuerelement noch nicht erstellt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen die `CEdit` Steuerelement durch Aufrufen von [CMFCToolBarEditBoxButton::CreateEdit](#createedit).  
  
##  <a name="gethwnd"></a>CMFCToolBarEditBoxButton::GetHwnd  
 Ruft das Fensterhandle, das die Symbolleisten-Schaltfläche zugeordnet ist.  
  
```  
virtual HWND GetHwnd();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Fensterhandle, das der Schaltfläche zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die [CMFCToolBarButton::GetHwnd](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd) Methode durch das Fensterhandle des bearbeiten-Steuerelement Teils der Schaltfläche "Feld bearbeiten" zurückgeben.  
  
##  <a name="getinvalidaterect"></a>CMFCToolBarEditBoxButton::GetInvalidateRect  
 Ruft den Bereich des Clientbereichs der Schaltfläche, die neu gezeichnet werden muss.  
  
```  
virtual const CRect GetInvalidateRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CRect` -Objekt, das den Bereich angibt, der neu gezeichnet werden muss.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die basisklassenimplementierung [CMFCToolBarButton::GetInvalidateRect](../../mfc/reference/cmfctoolbarbutton-class.md#getinvalidaterect), indem einschließlich in der Region des Bereichs der textbeschriftung.  
  
##  <a name="havehotborder"></a>CMFCToolBarEditBoxButton::HaveHotBorder  
 Bestimmt, ob ein Rahmen der Schaltfläche angezeigt wird, wenn ein Benutzer die Schaltfläche klickt.  
  
```  
virtual BOOL HaveHotBorder() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn eine Schaltfläche eine Rahmenlinie beim aktiviert angezeigt; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die basisklassenimplementierung [CMFCToolBarButton::HaveHotBorder](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder), indem Sie einen Wert ungleich NULL zurückgeben, wenn das Steuerelement sichtbar ist.  
  
##  <a name="isflatmode"></a>CMFCToolBarEditBoxButton::IsFlatMode  
 Bestimmt, ob Schaltflächen Bearbeiten ein Flatfile-Format haben.  
  
```  
static BOOL __stdcall IsFlatMode();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Schaltflächen flach haben; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig haben die Schaltflächen Bearbeiten ein Flatfile-Format. Verwenden der [CMFCToolBarEditBoxButton::SetFlatMode](#setflatmode) Methode, um die flache Darstellung für Ihre Anwendung zu ändern.  
  
##  <a name="notifycommand"></a>CMFCToolBarEditBoxButton::NotifyCommand  
 Gibt an, ob die Schaltfläche verarbeitet die [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Nachricht.  
  
```  
virtual BOOL NotifyCommand(int iNotifyCode);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iNotifyCode`  
 Die Benachrichtigung, die dem Befehl zugeordnet ist.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Taste verarbeitet die `WM_COMMAND` Nachricht oder `FALSE` um anzugeben, dass die Nachricht vom übergeordneten Symbolleiste verarbeitet werden muss.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode aus, wenn es zu senden ist ein [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Nachricht an das übergeordnete Fenster.  
  
 Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)) durch die Verarbeitung der [EN_UPDATE](http://msdn.microsoft.com/library/windows/desktop/bb761687) Benachrichtigung. Für jedes Eingabefeld mit derselben Befehls-ID wie dieses Objekt festgelegt dessen Bezeichnung auf die Beschriftung für dieses Objekt.  
  
##  <a name="onaddtocustomizepage"></a>CMFCToolBarEditBoxButton::OnAddToCustomizePage  
 Vom Framework aufgerufen, wenn die Schaltfläche "" hinzugefügt wird eine **anpassen** (Dialogfeld).  
  
```  
virtual void OnAddToCustomizePage();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage)) durch Kopieren die Eigenschaften aus den bearbeiten-Steuerelement in eine Symbolleiste, die derselben Befehls-ID wie dieses Objekt verfügt. Diese Methode bewirkt nichts, wenn keine Symbolleiste ein Bearbeitungssteuerelement für das Feld mit derselben Befehls-ID wie dieses Objekt besitzt.  
  
 Weitere Informationen zu den **anpassen** (Dialogfeld), finden Sie unter [CMFCToolBarsCustomizeDialog Klasse](../../mfc/reference/cmfctoolbarscustomizedialog-class.md).  
  
##  <a name="onchangeparentwnd"></a>CMFCToolBarEditBoxButton::OnChangeParentWnd  
 Vom Framework aufgerufen, wenn die Schaltfläche "" in eine neue Symbolleiste eingefügt wird.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndParent`  
 Ein Zeiger auf das neue übergeordnete Fenster.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die basisklassenimplementierung ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) durch das interne Neuerstellen `CEdit` Objekt.  
  
##  <a name="onclick"></a>CMFCToolBarEditBoxButton::OnClick  
 Wird vom Framework aufgerufen, klickt der Benutzer die Maustaste los.  
  
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
 Diese Methode überschreibt die basisklassenimplementierung ( [CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)) durch einen Wert ungleich NULL zurückgeben, wenn das interne `CEdit` -Objekts sichtbar ist.  
  
##  <a name="onctlcolor"></a>CMFCToolBarEditBoxButton::OnCtlColor  
 Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste verarbeitet eine `WM_CTLCOLOR` Nachricht.  
  
```  
virtual HBRUSH OnCtlColor(
    CDC* pDC,  
    UINT nCtlColor);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Der Gerätekontext, in dem die Schaltfläche angezeigt.  
  
 [in] `nCtlColor`  
 Nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für den globalen Fenster Pinsel.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die basisklassenimplementierung ( [CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)) durch die Text- und Hintergrundfarben des Gerätekontexts bereitgestellten auf die globale Text- und Hintergrundfarben, bzw. festlegen.  
  
 Weitere Informationen zu globalen Optionen, die für Ihre Anwendung verfügbar sind, finden Sie unter [AFX_GLOBAL_DATA-Struktur](../../mfc/reference/afx-global-data-structure.md).  
  
##  <a name="onglobalfontschanged"></a>CMFCToolBarEditBoxButton::OnGlobalFontsChanged  
 Vom Framework aufgerufen, wenn die globale Schriftart geändert hat.  
  
```  
virtual void OnGlobalFontsChanged();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)) durch Ändern der Schriftart des Steuerelements mit der globalen Schriftart.  
  
 Weitere Informationen zu globalen Optionen, die für Ihre Anwendung verfügbar sind, finden Sie unter [AFX_GLOBAL_DATA-Struktur](../../mfc/reference/afx-global-data-structure.md).  
  
##  <a name="onmove"></a>CMFCToolBarEditBoxButton::OnMove  
 Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste bewegt wird.  
  
```  
virtual void OnMove();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die standardmäßige Klasse-Implementierung ( [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)) durch Aktualisieren die Position des internen `CEdit` Objekt  
  
##  <a name="onshow"></a>CMFCToolBarEditBoxButton::OnShow  
 Vom Framework aufgerufen, wenn die Schaltfläche wird ein- oder ausgeblendet.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bShow`  
 Gibt an, ob die Schaltfläche sichtbar ist. Wenn dieser Parameter ist `TRUE`, die Schaltfläche sichtbar ist. Andernfalls ist die Schaltfläche nicht sichtbar.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)) durch die Schaltfläche anzeigen, wenn `bShow` ist `TRUE`. Diese Methode ist, andernfalls die Schaltfläche ausgeblendet.  
  
##  <a name="onsize"></a>CMFCToolBarEditBoxButton::OnSize  
 Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste seine Größe ändert oder Position und diese Änderung bewirkt, dass die Schaltfläche, um die Größe zu ändern.  
  
```  
virtual void OnSize(int iSize);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iSize`  
 Die neue Breite der Schaltfläche in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode überschreibt die standardmäßige Klasse-Implementierung [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize), indem Sie die Größe und Position des internen aktualisieren `CEdit` Objekt.  
  
##  <a name="onupdatetooltip"></a>CMFCToolBarEditBoxButton::OnUpdateToolTip  
 Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste die QuickInfo-Text aktualisiert.  
  
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
 Ein `CString` Objekt, das die aktualisierten QuickInfo-Text empfängt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Methode den QuickInfo-Text aktualisiert; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erweitert die basisklassenimplementierung ( [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)) durch Anzeigen des QuickInfo-Texts, der mit dem Webpart bearbeiten der Schaltfläche zugeordnet ist. Wenn das interne `CEdit` Objekt `NULL` oder das Fensterhandle des der `CEdit` Objekt ein vorhandenes Fenster nicht identifiziert, die diese Methode führt keine Aktion aus und gibt `FALSE`.  
  
##  <a name="setcontents"></a>CMFCToolBarEditBoxButton::SetContents  
 Legt den Text in das Textfeld-Steuerelement fest.  
  
```  
virtual void SetContents(const CString& sContents);
```  
  
### <a name="parameters"></a>Parameter  
 `[in] sContents`  
 Gibt den neuen Text festgelegt.  
  
##  <a name="setcontentsall"></a>CMFCToolBarEditBoxButton::SetContentsAll  
 Sucht nach einem [CMFCToolBarEditBoxButton](../../mfc/reference/cmfctoolbareditboxbutton-class.md) Objekt, das eine angegebene Befehls-ID hat und legt den angegebenen Text in ein Textfeld fest.  
  
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
  
##  <a name="setcontextmenuid"></a>CMFCToolBarEditBoxButton::SetContextMenuID  
 Gibt die Ressourcen-ID des Kontextmenüs, das der Schaltfläche zugeordnet ist.  
  
```  
void SetContextMenuID(UINT uiResID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiCmd`  
 Die Ressourcen-ID des Kontextmenüs.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verwendet die Ressourcen-ID, um das Kontextmenü zu erstellen, wenn der Benutzer die Symbolleisten-Schaltfläche klickt.  
  
##  <a name="setflatmode"></a>CMFCToolBarEditBoxButton::SetFlatMode  
 Gibt die flache Darstellung des bearbeiten-Schaltflächen in der Anwendung an.  
  
```  
static void __stdcall SetFlatMode(BOOL bFlat = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bFlat`  
 Die flache Darstellung für Schaltflächen bearbeiten. Wenn dieser Parameter ist `TRUE`, die unformatierte Darstellung aktiviert ist; andernfalls ist die flache Darstellung deaktiviert.  
  
### <a name="remarks"></a>Hinweise  
 Das Flatfile Standardformat für Schaltflächen Bearbeiten ist `TRUE`. Verwenden der [CMFCToolBarEditBoxButton::IsFlatMode](#isflatmode) Methode, um die flache Darstellung für Ihre Anwendung abzurufen.  
  
##  <a name="setstyle"></a>CMFCToolBarEditBoxButton::SetStyle  
 Gibt an, den Stil Symbolleisten-Steuerelement zu bearbeiten.  
  
```  
virtual void SetStyle(UINT nStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nStyle`  
 Eine neue Formatvorlage festgelegt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode legt [CMFCToolBarButton::m_nStyle](../../mfc/reference/cmfctoolbarbutton-class.md#m_nstyle) auf `nStyle` auch wird das Textfeld deaktiviert, wenn die Anwendung befindet sich im Modus anpassen und es, ermöglicht Wenn die Anwendung nicht im anpassen-Modus befindet (finden Sie unter [CMFCToolBar: : SetCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#setcustomizemode) und [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)). Finden Sie unter [Steuerelementtypen für die Symbolleiste](../../mfc/reference/toolbar-control-styles.md) eine Liste der gültigen Style Flags.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CEdit-Klasse](../../mfc/reference/cedit-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [Exemplarische Vorgehensweise: Steuerelemente in eine Symbolleiste einfügen](../../mfc/walkthrough-putting-controls-on-toolbars.md)



