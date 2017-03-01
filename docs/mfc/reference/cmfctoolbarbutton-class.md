---
title: Klasse CMFCToolBarButton | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarButton
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarButton class
ms.assetid: 8a6ecffb-86b0-4f5c-8211-a9146b463efd
caps.latest.revision: 34
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
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: 0139779cd00a514684c20b2c589d96247a532733
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbarbutton-class"></a>CMFCToolBarButton-Klasse
Schaltfläche Funktionsumfang auf Symbolleisten.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCToolBarButton : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarButton::CMFCToolBarButton](#cmfctoolbarbutton)|Erstellt und initialisiert ein `CMFCToolBarButton`-Objekt.|  
|`CMFCToolBarButton::~CMFCToolBarButton`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarButton::CanBeDropped](#canbedropped)|Gibt an, ob ein Benutzer eine Schaltfläche auf einer Symbolleiste oder einem Menü während der Anpassung positionieren kann.|  
|[CMFCToolBarButton::CanBeStored](#canbestored)|Gibt an, ob die Schaltfläche gespeichert werden kann.|  
|[CMFCToolBarButton::CanBeStretched](#canbestretched)|Gibt an, ob ein Benutzer während der Anpassung der Schaltfläche gestreckt werden kann.|  
|[CMFCToolBarButton::CompareWith](#comparewith)|Vergleicht diese Instanz mit dem angegebenen `CMFCToolBarButton` Objekt.|  
|[CMFCToolBarButton::CopyFrom](#copyfrom)|Kopiert die Eigenschaften des aktuellen Schaltfläche eine andere Symbolleisten-Schaltfläche.|  
|[CMFCToolBarButton::CreateFromOleData](#createfromoledata)|Erstellt eine `CMFCToolBarButton` Objekt aus dem bereitgestellten `COleDataObject` Objekt.|  
|`CMFCToolBarButton::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCToolBarButton::EnableWindow](#enablewindow)|Aktiviert oder deaktiviert die Maus- und Tastatureingaben.|  
|[CMFCToolBarButton::ExportToMenuButton](#exporttomenubutton)|Kopiert den Text aus der Symbolleisten-Schaltfläche ein Menü.|  
|[CMFCToolBarButton::GetClipboardFormat](#getclipboardformat)|Ruft das globale Zwischenablageformat für die Anwendung ab.|  
|[CMFCToolBarButton::GetHwnd](#gethwnd)|Ruft das Fensterhandle, das dem die Symbolleisten-Schaltfläche zugeordnet ist.|  
|[CMFCToolBarButton::GetImage](#getimage)|Ruft den Index des Bildes der Schaltfläche ab.|  
|[CMFCToolBarButton::GetInvalidateRect](#getinvalidaterect)|Ruft den Bereich des Clientbereichs der Schaltfläche, die neu gezeichnet werden muss.|  
|[CMFCToolBarButton::GetParentWnd](#getparentwnd)|Ruft das übergeordnete Fenster der Schaltfläche ab.|  
|[CMFCToolBarButton::GetProtectedCommands](#getprotectedcommands)|Ruft die Liste der Befehle, die der Benutzer angepasst werden kann.|  
|[CMFCToolBarButton::GetTextSize](#gettextsize)|Ruft die Größe des Schaltflächentexts ab.|  
|[CMFCToolBarButton::HasFocus](#hasfocus)|Bestimmt, ob die Schaltfläche mit den aktuellen Eingabefokus hat.|  
|[CMFCToolBarButton::HaveHotBorder](#havehotborder)|Bestimmt, ob ein Rahmen der Schaltfläche angezeigt wird, wenn ein Benutzer die Schaltfläche auswählt.|  
|[CMFCToolBarButton::IsDrawImage](#isdrawimage)|Bestimmt, ob ein Bild auf der Schaltfläche angezeigt wird.|  
|[CMFCToolBarButton::IsDrawText](#isdrawtext)|Bestimmt, ob eine Beschriftung auf der Schaltfläche angezeigt wird.|  
|[CMFCToolBarButton::IsDroppedDown](#isdroppeddown)|Bestimmt, ob die Schaltfläche zeigt ein Untermenü an.|  
|[CMFCToolBarButton::IsEditable](#iseditable)|Bestimmt, ob die Schaltfläche angepasst werden kann.|  
|[CMFCToolBarButton::IsExtraSize](#isextrasize)|Bestimmt, ob die Schaltfläche mit einem erweiterten Rahmen angezeigt werden kann.|  
|[CMFCToolBarButton::IsFirstInGroup](#isfirstingroup)|Bestimmt, ob die Schaltfläche in der ersten Position in der Gruppe.|  
|[CMFCToolBarButton::IsHidden](#ishidden)|Bestimmt, ob die Schaltfläche ausgeblendet ist.|  
|[CMFCToolBarButton::IsHorizontal](#ishorizontal)|Bestimmt, ob die Schaltfläche auf einer horizontalen Symbolleiste befindet.|  
|[CMFCToolBarButton::IsLastInGroup](#islastingroup)|Gibt an, ob die Schaltfläche in der letzten Position in der Gruppe ist.|  
|[CMFCToolBarButton::IsLocked](#islocked)|Bestimmt, ob die Schaltfläche auf einer Symbolleiste (nicht anpassbaren) gesperrt ist.|  
|[CMFCToolBarButton::IsOwnerOf](#isownerof)|Bestimmt, ob die Schaltfläche der Besitzer das angegebene Fensterhandle.|  
|[CMFCToolBarButton::IsVisible](#isvisible)|Bestimmt, ob die Symbolleisten-Schaltfläche sichtbar ist.|  
|[CMFCToolBarButton::IsWindowVisible](#iswindowvisible)|Bestimmt, ob das zugrunde liegende Fensterhandle der Schaltfläche angezeigt wird.|  
|[CMFCToolBarButton::NotifyCommand](#notifycommand)|Gibt an, ob die Schaltfläche verarbeitet die [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Nachricht.|  
|[CMFCToolBarButton::OnAddToCustomizePage](#onaddtocustomizepage)|Vom Framework aufgerufen, wenn die Schaltfläche hinzugefügt wird ein **anpassen** Dialogfeld.|  
|[CMFCToolBarButton::OnBeforeDrag](#onbeforedrag)|Gibt an, ob die Schaltfläche gezogen werden kann.|  
|[CMFCToolBarButton::OnBeforeDrop](#onbeforedrop)|Gibt an, ob ein Benutzer die Schaltfläche auf der Symbolleiste des Ziels gelöscht werden kann.|  
|[CMFCToolBarButton::OnCalculateSize](#oncalculatesize)|Aufgerufen, um die Größe der Schaltfläche für den angegebenen Gerätekontext und Andockstatus berechnen.|  
|[CMFCToolBarButton::OnCancelMode](#oncancelmode)|Aufgerufen, behandelt der [WM_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615) Nachricht.|  
|[CMFCToolBarButton::OnChangeParentWnd](#onchangeparentwnd)|Wird vom Framework aufgerufen, wenn eine neue Symbolleiste die Schaltfläche eingefügt wird.|  
|[CMFCToolBarButton::OnClick](#onclick)|Vom Framework aufgerufen, wenn der Benutzer die Maustaste klickt.|  
|[CMFCToolBarButton::OnClickUp](#onclickup)|Wird vom Framework aufgerufen, wenn der Benutzer die Maustaste loslässt.|  
|[CMFCToolBarButton::OnContextHelp](#oncontexthelp)|Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste behandelt eine `WM_HELPHITTEST` Nachricht.|  
|[CMFCToolBarButton::OnCtlColor](#onctlcolor)|Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste behandelt eine `WM_CTLCOLOR` Nachricht.|  
|[CMFCToolBarButton::OnCustomizeMenu](#oncustomizemenu)|Können die Schaltfläche, um die bereitgestellte Menü ändern, wenn die Anwendung auf der Symbolleiste des übergeordneten ein Kontextmenü angezeigt.|  
|[CMFCToolBarButton::OnDblClk](#ondblclk)|Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste behandelt eine [WM_LBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms645606) Nachricht.|  
|[CMFCToolBarButton::OnDraw](#ondraw)|Vom Framework aufgerufen wird die Schaltfläche gezeichnet werden soll, mithilfe der angegebenen Formate und -Optionen.|  
|[CMFCToolBarButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|Aufgerufen, um das Zeichnen der Schaltfläche die **Befehle** im Bereich der **anpassen** Dialogfeld.|  
|[CMFCToolBarButton::OnGetCustomToolTipText](#ongetcustomtooltiptext)|Aufgerufen, um den benutzerdefinierten QuickInfo-Text für die Schaltfläche abzurufen.|  
|[CMFCToolBarButton::OnGlobalFontsChanged](#onglobalfontschanged)|Wird vom Framework aufgerufen, wenn die globale Schriftart geändert hat.|  
|[CMFCToolBarButton::OnMove](#onmove)|Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste verschoben wird.|  
|[CMFCToolBarButton::OnShow](#onshow)|Vom Framework aufgerufen, wenn die Schaltfläche wird sichtbar oder unsichtbar.|  
|[CMFCToolBarButton::OnSize](#onsize)|Wird vom Framework aufgerufen, wenn die übergeordneten Symbolleiste seine Größe ändert oder Position und diese Änderung erfordert die Schaltfläche, um die Größe zu ändern.|  
|[CMFCToolBarButton::OnToolHitTest](#ontoolhittest)|Wird vom Framework aufgerufen, wenn die übergeordneten Symbolleiste bestimmen muss, ob ein Punkt im umschließenden Rechteck neben der Schaltfläche.|  
|[CMFCToolBarButton::OnUpdateToolTip](#onupdatetooltip)|Wird vom Framework aufgerufen, wenn die übergeordneten Symbolleiste den QuickInfotext aktualisiert.|  
|[CMFCToolBarButton::PrepareDrag](#preparedrag)|Wird vom Framework aufgerufen, wenn die Schaltfläche ein Drag & Drop-Vorgang ausgeführt wird.|  
|[CMFCToolBarButton::Rect](#rect)|Ruft das umschließende Rechteck der Schaltfläche ab.|  
|[CMFCToolBarButton::ResetImageToDefault](#resetimagetodefault)|Legt das Bild, das der Schaltfläche zugeordnet ist, auf den Standardwert fest.|  
|[CMFCToolBarButton::SaveBarState](#savebarstate)|Speichert den Zustand der Symbolleisten-Schaltfläche.|  
|[CMFCToolBarButton::Serialize](#serialize)|Dieses Objekt aus dem Archiv liest oder schreibt dieses in ein Archiv. (Überschreibt [Einfügeoperatoren](../../mfc/reference/cobject-class.md#serialize).)|  
|[CMFCToolBarButton::SetACCData](#setaccdata)|Füllt die angegebene `CAccessibilityData` Objekt mit Zugriff auf Daten aus der Symbolleisten-Schaltfläche.|  
|[CMFCToolBarButton::SetClipboardFormatName](#setclipboardformatname)|Benennt das globale Zwischenablageformat.|  
|[CMFCToolBarButton::SetImage](#setimage)|Legt den Index des Bildes der Schaltfläche fest.|  
|[CMFCToolBarButton::SetProtectedCommands](#setprotectedcommands)|Legt die Liste der Befehle, die der Benutzer angepasst werden kann.|  
|[CMFCToolBarButton::SetRadio](#setradio)|Wird vom Framework aufgerufen, wenn eine Schaltfläche dessen Aktivierungszustand ändert.|  
|[CMFCToolBarButton::SetRect](#setrect)|Legt das umschließende Rechteck der Schaltfläche fest.|  
|[CMFCToolBarButton::SetStyle](#setstyle)|Legt den Stil der Schaltfläche.|  
|[CMFCToolBarButton::SetVisible](#setvisible)|Gibt an, ob die Schaltfläche sichtbar ist.|  
|[CMFCToolBarButton::Show](#show)|Anzeigen oder Ausblenden der Schaltfläche.|  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarButton::m_bImage](#m_bimage)|Gibt an, ob ein Bild auf der Schaltfläche angezeigt wird.|  
|[CMFCToolBarButton::m_bText](#m_btext)|Gibt an, ob eine Beschriftung auf der Schaltfläche angezeigt wird.|  
|[CMFCToolBarButton::m_bTextBelow](#m_btextbelow)|Gibt an, ob die Beschriftung unter dem Bild auf der Schaltfläche angezeigt wird.|  
|[CMFCToolBarButton::m_bUserButton](#m_buserbutton)|Gibt an, ob die Schaltfläche ein benutzerdefiniertes Abbild verfügt.|  
|[CMFCToolBarButton::m_bWholeText](#m_bwholetext)|Gibt an, ob die Schaltfläche die vollständige Beschriftung angezeigt, auch wenn es nicht in das Begrenzungsrechteck passt.|  
|[CMFCToolBarButton::m_bWrap](#m_bwrap)|Gibt an, ob die Schaltfläche neben einem Trennzeichen in der nächsten Zeile überführt werden sollen.|  
|[CMFCToolBarButton::m_bWrapText](#m_bwraptext)|Gibt an, ob es sich bei mehrzeiligen Textfeld Bezeichnungen aktiviert sind.|  
|[CMFCToolBarButton::m_nID](#m_nid)|Die Befehls-ID der Schaltfläche.|  
|[CMFCToolBarButton::m_nStyle](#m_nstyle)|Der Stil der Schaltfläche.|  
|[CMFCToolBarButton::m_strText](#m_strtext)|Die Beschriftung der Schaltfläche.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `CMFCToolbarButton` Objekt ist ein Steuerelement, das auf einer Symbolleiste befindet. Das Verhalten ähnelt dem für eine normale Schaltfläche. Sie können ein Bild und eine Beschriftung für dieses Objekt zuweisen. Eine Symbolleisten-Schaltfläche kann auch eine Befehls-ID haben. Wenn der Benutzer die Symbolleisten-Schaltfläche klickt, führt das Framework den Befehl, den diese ID angibt.  
  
 In der Regel die Schaltflächen der Symbolleiste können angepasst werden kann: der Benutzer kann ziehen Sie Schaltflächen zwischen Symbolleisten, und kopieren, einfügen, löschen und Beschriftungen und Bilder zu bearbeiten. Um zu verhindern, dass den Benutzer die Symbolleiste anpassen, können Sie die Symbolleiste auf zwei Arten sperren. Entweder der `bLocked` flag auf `TRUE` beim Aufruf [CMFCToolBar::LoadToolBar](../../mfc/reference/cmfctoolbar-class.md#loadtoolbar), oder die globale Liste der geschützten Befehle die Befehls-ID für eine einzelne Schaltfläche hinzu, mit der [CMFCToolBarButton::SetProtectedCommands](#setprotectedcommands) Methode.  
  
 `CMFCToolBarButton`Objekte werden Bilder aus der globalen Auflistung von symbolleistenbildern in der Anwendung. Diese Sammlungen werden von der übergeordneten Symbolleiste verwaltet [CMFCToolBar Klasse](../../mfc/reference/cmfctoolbar-class.md). Weitere Informationen finden Sie unter [CMFCToolBarImages Klasse](../../mfc/reference/cmfctoolbarimages-class.md).  
  
 Wenn der Benutzer eine Symbolleisten-Schaltfläche klickt, wird die übergeordneten Symbolleiste die Maus-Nachricht verarbeitet und kommuniziert die entsprechenden Aktionen auf die Schaltfläche. Wenn die Schaltfläche eine gültige Befehls-ID hat, sendet die übergeordneten Symbolleiste die `WM_COMMAND` Nachricht an den übergeordneten Frame.  
  
 Die `CMFCToolBarButton` Klasse ist die Basisklasse für andere Symbolleisten-Schaltfläche-Klassen, z. B. [CMFCToolBarMenuButton Klasse](../../mfc/reference/cmfctoolbarmenubutton-class.md), [CMFCToolBarEditBoxButton Klasse](../../mfc/reference/cmfctoolbareditboxbutton-class.md), und [CMFCToolBarComboBoxButton Klasse](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie so konfigurieren Sie eine `CMFCToolBarButton` Objekt mit verschiedenen Methoden in der `CMFCToolBarButton` Klasse. Das Beispiel veranschaulicht, wie die Maus zu aktivieren und Tastatureingaben, setzen Sie den Image-Index der Schaltfläche, das umschließende Rechteck der Schaltfläche festgelegt und die Schaltfläche sichtbar zu machen. Dieser Codeausschnitt ist Teil der [Registersteuerelement Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_TabControl&#1;](../../mfc/reference/codesnippet/cpp/cmfctoolbarbutton-class_1.cpp)]  
[!code-cpp[NVC_MFC_TabControl&#2;](../../mfc/reference/codesnippet/cpp/cmfctoolbarbutton-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtoolbarbutton.h  
  
##  <a name="a-namecanbedroppeda--cmfctoolbarbuttoncanbedropped"></a><a name="canbedropped"></a>CMFCToolBarButton::CanBeDropped  
 Gibt an, ob ein Benutzer eine Schaltfläche auf einer Symbolleiste oder einem Menü während der Anpassung positionieren kann.  
  
```  
virtual BOOL CanBeDropped(CMFCToolBar* pToolbar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pToolbar`  
 Nicht verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt `TRUE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig kann auf eine Symbolleistenschaltfläche abgelegt werden alle anpassbare (d. h. nicht gesperrte) Symbolleiste.  
  
 Gibt die standardmäßige Implementierung dieser Methode `TRUE`. Diese Methode überschreiben und zurückgeben `FALSE` gegebenenfalls zu verhindern, dass der Benutzer die Schaltfläche neu zu positionieren.  
  
##  <a name="a-namecanbestoreda--cmfctoolbarbuttoncanbestored"></a><a name="canbestored"></a>CMFCToolBarButton::CanBeStored  
 Bestimmt, ob die Schaltfläche gespeichert werden kann.  
  
```  
virtual BOOL CanBeStored() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt `TRUE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verwendet diese Methode, um zu bestimmen, ob die Schaltfläche in einem Drag & Drop-Vorgang teilnehmen kann.  
  
 Die Standardimplementierung gibt `TRUE` zurück. Überschreiben Sie diese Methode, wenn die Schaltfläche als Teil eines Drag & Drop-Vorgangs gespeichert werden kann. Weitere Informationen über Drag & Drop-Vorgänge finden Sie unter [Drag & Drop (OLE)](../../mfc/drag-and-drop-ole.md).  
  
##  <a name="a-namecanbestretcheda--cmfctoolbarbuttoncanbestretched"></a><a name="canbestretched"></a>CMFCToolBarButton::CanBeStretched  
 Gibt an, ob ein Benutzer während der Anpassung der Schaltfläche gestreckt werden kann.  
  
```  
virtual BOOL CanBeStretched() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt `FALSE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework verwendet, um festzustellen, ob die Schaltfläche im Anpassungsmodus gedehnt werden kann.  
  
 Gibt die standardmäßige Implementierung dieser Methode `FALSE`. Überschreiben Sie diese Methode zurückgeben `TRUE` für ein Steuerelement variabler Breite, z. B. ein Kombinationsfeld oder einem Schieberegler.  
  
 Weitere Informationen zu den Anpassungsmodus, finden Sie unter [CMFCToolBar::SetCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#setcustomizemode).  
  
##  <a name="a-namecmfctoolbarbuttona--cmfctoolbarbuttoncmfctoolbarbutton"></a><a name="cmfctoolbarbutton"></a>CMFCToolBarButton::CMFCToolBarButton  
 Erstellt und initialisiert ein `CMFCToolBarButton`-Objekt.  
  
```  
CMFCToolBarButton(
    UINT uiID,  
    int iImage,  
    LPCTSTR lpszText=NULL,  
    BOOL bUserButton=FALSE,  
    BOOL bLocked=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiID`  
 Die Befehls-ID der Schaltfläche.  
  
 [in] `iImage`  
 Der Image-Index der Schaltfläche in die Auflistung der Bilder.  
  
 [in] `lpszText`  
 Die Beschriftung der Schaltfläche. Kann `NULL`.  
  
 [in] `bUserButton`  
 Ein boolescher Wert, der bestimmt, ob die Schaltfläche Benutzerdefiniert ist. Wenn dieser Parameter ist `TRUE`, die Schaltfläche Benutzerdefiniert ist. Andernfalls ist das Schaltflächenbild aus einer Ressource geladen.  
  
 [in] `bLocked`  
 Ein boolescher Wert, der bestimmt, ob die Schaltfläche angepasst werden kann. Wenn dieser Parameter ist `TRUE`, die Schaltfläche kann nicht angepasst werden. Andernfalls kann die Schaltfläche angepasst werden.  
  
##  <a name="a-namecomparewitha--cmfctoolbarbuttoncomparewith"></a><a name="comparewith"></a>CMFCToolBarButton::CompareWith  
 Vergleicht diese Instanz mit dem angegebenen `CMFCToolBarButton` Objekt.  
  
```  
virtual BOOL CompareWith(const CMFCToolBarButton& other) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `other`  
 Verweis auf das Objekt, das mit dieser Instanz verglichen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das bereitgestellte Objekt gleich dem Wert dieser Instanz ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung der bestimmt, ob die Befehls-ID des bereitgestellten Objekts die Befehls-ID dieser Instanz entspricht. Überschreiben Sie diese Methode, wenn Sie ausführen müssen, um zu bestimmen, ob zwei zusätzliche Verarbeitung `CMFCToolBarButton` -Objekte gleich sind.  
  
##  <a name="a-namecopyfroma--cmfctoolbarbuttoncopyfrom"></a><a name="copyfrom"></a>CMFCToolBarButton::CopyFrom  
 Kopiert die Eigenschaften des aktuellen Schaltfläche eine andere Symbolleisten-Schaltfläche.  
  
```  
virtual void CopyFrom(const CMFCToolBarButton& src);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `src`  
 Ein Verweis auf die Schaltfläche "Quelle" aus dem kopiert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Kopieren von einem anderen Symbolleisten-Schaltfläche auf diese Schaltfläche.  
  
##  <a name="a-namecreatefromoledataa--cmfctoolbarbuttoncreatefromoledata"></a><a name="createfromoledata"></a>CMFCToolBarButton::CreateFromOleData  
 Erstellt eine `CMFCToolBarButton` Objekt aus dem bereitgestellten `COleDataObject` Objekt.  
  
```  
static CMFCToolBarButton* __stdcall CreateFromOleData(COleDataObject* pDataObject);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDataObject`  
 OLE Datenquellenobjekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Das erstellte `CMFCToolBarButton`-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework verwendet, um die Datenübertragung in verschiedenen Formaten. Zum Beispiel die `CMFCOutlookBarPane::OnDragOver` Methode verwendet diese Methode, um Drag & Drop-Vorgänge ausführen.  
  
##  <a name="a-nameenablewindowa--cmfctoolbarbuttonenablewindow"></a><a name="enablewindow"></a>CMFCToolBarButton::EnableWindow  
 Aktiviert oder deaktiviert die Maus- und Tastatureingaben.  
  
```  
virtual void EnableWindow(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 Legen Sie diesen Parameter `TRUE` Eingabe zu aktivieren oder zu `FALSE` Eingabe zu deaktivieren.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft die `EnableWindow` Funktion aktivieren oder deaktivieren die Eingabe. Weitere Informationen finden Sie unter [EnableWindow](http://msdn.microsoft.com/library/windows/desktop/ms646291) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-nameexporttomenubuttona--cmfctoolbarbuttonexporttomenubutton"></a><a name="exporttomenubutton"></a>CMFCToolBarButton::ExportToMenuButton  
 Kopiert den Text aus der Symbolleisten-Schaltfläche ein Menü.  
  
```  
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `menuButton`  
 Ein Verweis auf die Schaltfläche Ziel.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt `TRUE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um den Text aus einer Symbolleisten-Schaltfläche in eine Schaltfläche zu kopieren. Die standardmäßige Implementierung kopiert die Beschriftung der Schaltfläche. Wenn die Beschriftung leer ist, kopiert diese Methode den QuickInfo-Text der Schaltfläche.  
  
 Gibt die standardmäßige Implementierung dieser Methode `TRUE`. Diese Methode überschreiben, sollten Sie zusätzliche Aktionen ausführen, wenn das Framework ein Objekt konvertiert, die von abgeleitet ist [CMFCToolbarButton](../../mfc/reference/cmfctoolbarbutton-class.md) auf eine Schaltfläche.  
  
##  <a name="a-namegetclipboardformata--cmfctoolbarbuttongetclipboardformat"></a><a name="getclipboardformat"></a>CMFCToolBarButton::GetClipboardFormat  
 Ruft das globale Zwischenablageformat für die Anwendung ab.  
  
```  
static CLIPFORMAT __stdcall GetClipboardFormat();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die globale `CLIPFORMAT` Wert für die Anwendung.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um das Format der Zwischenablage für OLE-Datenübertragungsvorgänge abzurufen. Zum Beispiel die [CMFCToolBarButton::CreateFromOleData](#createfromoledata) Methode verwendet diese Methode zum Kopieren von Daten aus einem Quelldatenobjekt OLE.  
  
 Diese Methode wird die globale `CLIPFORMAT` Wert zum ersten Mal diese Methode aufgerufen wird. Alle nachfolgenden Aufrufe dieser Methode geben diesen Wert zurück.  
  
 Um Drag & Drop-Operationen zwischen Anwendungen zu ermöglichen, rufen Sie die [CMFCToolBarButton::SetClipboardFormatName](#setclipboardformatname) Methode.  
  
 Weitere Informationen zu Zwischenablagen in MFC finden Sie unter [Zwischenablage](../../mfc/clipboard.md).  
  
##  <a name="a-namegethwnda--cmfctoolbarbuttongethwnd"></a><a name="gethwnd"></a>CMFCToolBarButton::GetHwnd  
 Ruft das Fensterhandle, das dem die Symbolleisten-Schaltfläche zugeordnet ist.  
  
```  
virtual HWND GetHwnd();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Fensterhandle, dem die Symbolleisten-Schaltfläche zugeordnet ist, oder `NULL` verfügt die Symbolleisten-Schaltfläche kein Handle zugeordnete Fenster.  
  
### <a name="remarks"></a>Hinweise  
 Gibt die standardmäßige Implementierung dieser Methode `NULL`. Überschreiben Sie diese Methode, um die Rückgabe des Fensterhandles eines bestimmten Steuerelements.  
  
##  <a name="a-namegetimagea--cmfctoolbarbuttongetimage"></a><a name="getimage"></a>CMFCToolBarButton::GetImage  
 Ruft den Index des Bildes der Schaltfläche ab.  
  
```  
int GetImage() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des Bilds, das diese Schaltfläche zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Schaltfläche ein benutzerdefiniertes Abbild hat (d. h., wenn `bUserButton` wurde `TRUE` im Konstruktor), der zurückgegebene Index gibt ein Bild in die Auflistung der benutzerdefinierten Bilder (finden Sie unter [CMFCToolBar::GetUserImages](../../mfc/reference/cmfctoolbar-class.md#getuserimages)). Andernfalls gibt der Index ein Bild in die Auflistung der Bilder, die aus einer Ressourcendatei geladen werden (siehe [CMFCToolBar::GetImages](../../mfc/reference/cmfctoolbar-class.md#getimages)). Weitere Informationen über Ressourcendateien finden Sie unter [arbeiten mit Ressourcendateien](../../windows/working-with-resource-files.md).  
  
##  <a name="a-namegetinvalidaterecta--cmfctoolbarbuttongetinvalidaterect"></a><a name="getinvalidaterect"></a>CMFCToolBarButton::GetInvalidateRect  
 Ruft den Bereich des Clientbereichs der Schaltfläche, die neu gezeichnet werden muss.  
  
```  
virtual const CRect GetInvalidateRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CRect` -Objekt, das den Bereich angibt, der neu gezeichnet werden muss.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Methode gibt den gesamten Clientbereich zurück. Überschreiben Sie diese Methode, wenn Sie einen anderen Bereich neu gezeichnet werden soll.  
  
##  <a name="a-namegetparentwnda--cmfctoolbarbuttongetparentwnd"></a><a name="getparentwnd"></a>CMFCToolBarButton::GetParentWnd  
 Ruft das übergeordnete Fenster der Schaltfläche ab.  
  
```  
CWnd* GetParentWnd() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das übergeordnete Fenster der Schaltfläche.  
  
##  <a name="a-namegetprotectedcommandsa--cmfctoolbarbuttongetprotectedcommands"></a><a name="getprotectedcommands"></a>CMFCToolBarButton::GetProtectedCommands  
 Ruft die Liste der Befehle, die der Benutzer angepasst werden kann.  
  
```  
static const CList<UINT,UINT>& GetProtectedCommands();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Liste der geschützten Befehle.  
  
### <a name="remarks"></a>Hinweise  
 Im Anpassungsmodus deaktiviert das Framework Schaltfläche Befehle, die geschützt werden. Der Benutzer kann nicht ausführen von Drag & Drop und Vorgänge für deaktivierte Symbolleistenschaltflächen bearbeiten.  
  
 Verwenden der [CMFCToolBarButton::SetProtectedCommands](#setprotectedcommands) Methode zum Definieren der Liste der Befehle geschützt.  
  
##  <a name="a-namegettextsizea--cmfctoolbarbuttongettextsize"></a><a name="gettextsize"></a>CMFCToolBarButton::GetTextSize  
 Ruft die Größe des Schaltflächentexts ab.  
  
```  
SIZE GetTextSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `SIZE` -Objekt, das die Größe in Pixel, der den Text der Schaltfläche enthält.  
  
##  <a name="a-namehasfocusa--cmfctoolbarbuttonhasfocus"></a><a name="hasfocus"></a>CMFCToolBarButton::HasFocus  
 Bestimmt, ob die Schaltfläche mit den aktuellen Eingabefokus hat.  
  
```  
virtual BOOL HasFocus() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Schaltfläche den Eingabefokus hat; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Methode gibt einen Wert ungleich NULL zurück, wenn die Schaltfläche den Eingabefokus besitzt, oder ist ein untergeordnetes Element oder Nachfolgerelement Fenster des Fensters, das den Eingabefokus besitzt. Sie können diese Funktion, um dieses Verhalten anpassen, überschreiben.  
  
##  <a name="a-namehavehotbordera--cmfctoolbarbuttonhavehotborder"></a><a name="havehotborder"></a>CMFCToolBarButton::HaveHotBorder  
 Bestimmt, ob ein Rahmen der Schaltfläche angezeigt wird, wenn ein Benutzer die Schaltfläche auswählt.  
  
```  
virtual BOOL HaveHotBorder() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt `TRUE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um zu bestimmen, ob die Symbolleisten-Schaltfläche den Rahmen angezeigt werden soll, wenn ein Benutzer ausgewählt.  
  
 Die Standardimplementierung gibt `TRUE` zurück. Überschreiben Sie diese Methode, um dieses Verhalten anzupassen.  
  
##  <a name="a-nameisdrawimagea--cmfctoolbarbuttonisdrawimage"></a><a name="isdrawimage"></a>CMFCToolBarButton::IsDrawImage  
 Bestimmt, ob ein Bild auf der Schaltfläche angezeigt wird.  
  
```  
BOOL IsDrawImage() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn ein Bild auf der Schaltfläche angezeigt wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt `FALSE` die Symbolleisten-Schaltfläche besitzt kein zugeordnetes Bild ( [CMFCToolBarButton::GetImage](#getimage) gibt-1 zurück) oder wenn [CMFCToolBarButton::m_bImage](#m_bimage) auf festgelegt ist `FALSE`.  
  
##  <a name="a-nameisdrawtexta--cmfctoolbarbuttonisdrawtext"></a><a name="isdrawtext"></a>CMFCToolBarButton::IsDrawText  
 Bestimmt, ob eine Beschriftung auf der Schaltfläche angezeigt wird.  
  
```  
BOOL IsDrawText() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn eine Beschriftung angezeigt wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt `FALSE` die Symbolleisten-Schaltfläche hat keine zugeordnete Beschriftung ( [CMFCToolBarButton::m_strText](#m_strtext) leer ist) oder [CMFCToolBarButton::m_bText](#m_btext) auf festgelegt ist `FALSE`.  
  
##  <a name="a-nameisdroppeddowna--cmfctoolbarbuttonisdroppeddown"></a><a name="isdroppeddown"></a>CMFCToolBarButton::IsDroppedDown  
 Bestimmt, ob die Schaltfläche zeigt ein Untermenü an.  
  
```  
virtual BOOL IsDroppedDown() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt `FALSE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Gibt die standardmäßige Implementierung dieser Methode `FALSE`. Überschreiben Sie diese Methode zurückgeben `TRUE` , wenn das Steuerelement zeigt ein Untermenü an.  
  
##  <a name="a-nameiseditablea--cmfctoolbarbuttoniseditable"></a><a name="iseditable"></a>CMFCToolBarButton::IsEditable  
 Bestimmt, ob die Schaltfläche angepasst werden kann.  
  
```  
virtual BOOL IsEditable() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Benutzer eine Schaltfläche angepasst werden kann; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um zu bestimmen, ob der Benutzer kann die Symbolleisten-Schaltfläche mithilfe von Drag & Drop-anpassen oder Bearbeitungsvorgänge an.  
  
 Die standardmäßige Implementierung gibt `FALSE` die Befehls-ID der Schaltfläche ein Standardbefehl ist (Sie können hierfür durch Aufrufen der `IsStandardCommand` Funktion) oder Befehls-ID in der Liste der ist Befehle geschützt. Weitere Informationen zu geschützten Befehlen finden Sie unter [CMFCToolBarButton::GetProtectedCommands](#getprotectedcommands) und [CMFCToolBarButton::SetProtectedCommands](#setprotectedcommands).  
  
 Überschreiben Sie diese Methode, um sein Verhalten anpassen.  
  
##  <a name="a-nameisextrasizea--cmfctoolbarbuttonisextrasize"></a><a name="isextrasize"></a>CMFCToolBarButton::IsExtraSize  
 Bestimmt, ob die Schaltfläche mit einem erweiterten Rahmen angezeigt werden kann.  
  
```  
virtual BOOL IsExtraSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Symbolleisten-Schaltfläche mit einem erweiterten Rahmen angezeigt werden kann; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Mehrere Designs verwenden Größe für den Rahmen der Symbolleisten-Schaltflächen (z. B. round Schaltflächen).  
  
 Wenn der Benutzer diese Schaltfläche auf einer Symbolleiste in einen anderen bewegt wird, ruft das Framework die [CMFCToolBarButton::OnChangeParentWnd](#onchangeparentwnd) Methode. Die [CMFCToolBarButton::OnChangeParentWnd](#onchangeparentwnd) Methode legt das Flag für die Größe des neuen übergeordneten Symbolleiste (Weitere Informationen finden Sie unter [CMFCToolBar::IsButtonExtraSizeAvailable](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable)).  
  
##  <a name="a-nameisfirstingroupa--cmfctoolbarbuttonisfirstingroup"></a><a name="isfirstingroup"></a>CMFCToolBarButton::IsFirstInGroup  
 Bestimmt, ob die Schaltfläche in der ersten Position in der Gruppe.  
  
```  
virtual BOOL IsFirstInGroup() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Schaltfläche auf die erste Schaltfläche in der Gruppe ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode definiert eine *Schaltflächengruppe* als benachbarten Satz von Schaltflächen enthalten, werden in derselben Zeile positioniert, und durch Trennzeichen oder am Rand der Symbolleiste begrenzt werden. Diese Methode gibt `FALSE` Wenn die Symbolleisten-Schaltfläche ein Verweis auf die **anpassen** Schaltfläche. Weitere Informationen zu den **anpassen** klicken, [CMFCToolBar::GetCustomizeButton](../../mfc/reference/cmfctoolbar-class.md#getcustomizebutton).  
  
 Rufen Sie die [CMFCToolBarButton::IsLastInGroup](#islastingroup) Methode, um zu bestimmen, ob die Schaltfläche in der letzten Position in der Gruppe ist.  
  
##  <a name="a-nameishiddena--cmfctoolbarbuttonishidden"></a><a name="ishidden"></a>CMFCToolBarButton::IsHidden  
 Bestimmt, ob die Schaltfläche ausgeblendet ist.  
  
```  
BOOL IsHidden() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die Schaltfläche ausgeblendet (nicht sichtbar); andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn die übergeordneten Symbolleiste gestreckt wird, um zu bestimmen, ob die Symbolleisten-Schaltfläche sichtbar ist.  
  
 Wenn Sie die Schaltfläche, um mit unsichtbar Festlegen der [CMFCToolBarButton::SetVisible](#setvisible) -Methode [CMFCToolBarButton::IsVisible](#isvisible) zu bestimmen, ob die Symbolleisten-Schaltfläche sichtbar ist.  
  
 Standardmäßig sind alle Schaltflächen der Symbolleiste sichtbar. Verwenden der [CMFCToolBarButton::Show](#show) -Methode zum Ausblenden oder Anzeigen von Symbolleisten-Schaltflächen.  
  
##  <a name="a-nameishorizontala--cmfctoolbarbuttonishorizontal"></a><a name="ishorizontal"></a>CMFCToolBarButton::IsHorizontal  
 Bestimmt, ob die Schaltfläche auf einer horizontalen Symbolleiste befindet.  
  
```  
BOOL IsHorizontal() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn eine Symbolleisten-Schaltfläche auf einer horizontalen Symbolleiste befindet; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um das Layout von Symbolleisten-Schaltflächen zu bestimmen.  
  
 Diese Methode gibt die `m_bHorz` -Datenmember. Der Standardwert der `m_bHorz` -Datenmember ist `TRUE`; wird zurückgesetzt, bei jedem Aufruf der [CMFCToolBarButton::OnDraw](#ondraw) Methode.  
  
##  <a name="a-nameislastingroupa--cmfctoolbarbuttonislastingroup"></a><a name="islastingroup"></a>CMFCToolBarButton::IsLastInGroup  
 Gibt an, ob die Schaltfläche in der letzten Position in der Gruppe ist.  
  
```  
virtual BOOL IsLastInGroup() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Schaltfläche die letzte Schaltfläche in der Gruppe ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode definiert eine *Schaltflächengruppe* als benachbarten Satz von Schaltflächen enthalten, werden in derselben Zeile positioniert, und durch Trennzeichen oder am Rand der Symbolleiste begrenzt werden, die diese Methode gibt `FALSE` Wenn die Symbolleisten-Schaltfläche verfügt über keine übergeordneten Symbolleiste oder die Symbolleistenschaltfläche bezieht sich auf die **anpassen** Schaltfläche. Weitere Informationen zu den **anpassen** klicken, [CMFCToolBar::GetCustomizeButton](../../mfc/reference/cmfctoolbar-class.md#getcustomizebutton).  
  
 Rufen Sie die [CMFCToolBarButton::IsFirstInGroup](#isfirstingroup) Methode, um zu bestimmen, ob die Schaltfläche in der ersten Position in der Gruppe ist.  
  
##  <a name="a-nameislockeda--cmfctoolbarbuttonislocked"></a><a name="islocked"></a>CMFCToolBarButton::IsLocked  
 Bestimmt, ob die Schaltfläche auf einer Symbolleiste (nicht anpassbaren) gesperrt ist.  
  
```  
BOOL IsLocked() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Schaltfläche auf einer Symbolleiste gesperrt ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um zu bestimmen, ob der Benutzer kann die Symbolleisten-Schaltfläche mithilfe von Drag & Drop-anpassen oder Bearbeitungsvorgänge an. Legen Sie den gesperrten Attribut in der übergeordneten Symbolleiste mithilfe der [CMFCToolBar::LoadToolBar](../../mfc/reference/cmfctoolbar-class.md#loadtoolbar) Methode. Das Framework übergibt den Wert dieses Attributs an den Konstruktor der einzelnen Schaltflächen der Symbolleiste ( [CMFCToolbarButton](../../mfc/reference/cmfctoolbarbutton-class.md)), die in der übergeordneten Symbolleiste eingefügt.  
  
##  <a name="a-nameisownerofa--cmfctoolbarbuttonisownerof"></a><a name="isownerof"></a>CMFCToolBarButton::IsOwnerOf  
 Bestimmt, ob die Schaltfläche der Besitzer das angegebene Fensterhandle.  
  
```  
virtual BOOL IsOwnerOf(HWND hwnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hwnd`  
 Ein Fensterhandle.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Schaltfläche der Besitzer das angegebene Fensterhandle ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt einen Wert ungleich NULL, wenn `hwnd` bezieht sich auf das direkte Fensterhandle oder ist ein untergeordnetes Element des Fensterhandles an, der mit der Schaltfläche zugeordnet ist. Diese Methode gibt 0 zurück, wenn `hwnd` ist `NULL`.  
  
##  <a name="a-nameisvisiblea--cmfctoolbarbuttonisvisible"></a><a name="isvisible"></a>CMFCToolBarButton::IsVisible  
 Bestimmt, ob die Symbolleisten-Schaltfläche sichtbar ist.  
  
```  
BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Symbolleisten-Schaltfläche sichtbar ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie können ein- oder Ausblenden der Symbolleiste auf die Schaltfläche mit den [CMFCToolBarButton::SetVisible](#setvisible) Methode. Rufen Sie die [CPane::AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate) Methode in der übergeordneten Symbolleiste nach dem Aufruf von [CMFCToolBarButton::SetVisible](#setvisible) das Layout einer übergeordneten Symbolleiste neu berechnet.  
  
##  <a name="a-nameiswindowvisiblea--cmfctoolbarbuttoniswindowvisible"></a><a name="iswindowvisible"></a>CMFCToolBarButton::IsWindowVisible  
 Bestimmt, ob das zugrunde liegende Fensterhandle der Schaltfläche angezeigt wird.  
  
```  
virtual BOOL IsWindowVisible();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das zugrunde liegende Fensterhandle der Schaltfläche sichtbar ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt einen Wert ungleich NULL, wenn Attributs Stile für das zugrunde liegende Fensterhandle enthält die `WS_VISIBLE` Stil. Diese Methode gibt `FALSE` ist das zugrunde liegende Fensterhandle der Schaltfläche `NULL`.  
  
##  <a name="a-namembimagea--cmfctoolbarbuttonmbimage"></a><a name="m_bimage"></a>CMFCToolBarButton::m_bImage  
 Gibt an, ob ein Bild auf der Schaltfläche angezeigt wird.  
  
```  
BOOL m_bImage;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn dieses Datenelement, um festgelegt ist `TRUE`, das Framework zeigt das Bild, dem die Symbolleisten-Schaltfläche zugeordnet ist; andernfalls das Framework wird das Bild nicht angezeigt. Bei diesem Member wirkt sich auf den Rückgabewert der [CMFCToolBarButton::m_bImage](#m_bimage) Methode.  
  
##  <a name="a-namembtexta--cmfctoolbarbuttonmbtext"></a><a name="m_btext"></a>CMFCToolBarButton::m_bText  
 Gibt an, ob eine Beschriftung auf der Schaltfläche angezeigt wird.  
  
```  
BOOL m_bText;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn dieses Datenelement, um festgelegt ist `TRUE`, vom Framework die Beschriftung der Symbolleisten-Schaltfläche angezeigt wird, andernfalls das Framework nicht die Beschriftung angezeigt. Bei diesem Member wirkt sich auf den Rückgabewert der [CMFCToolBarButton::m_bText](#m_btext) Methode.  
  
##  <a name="a-namembtextbelowa--cmfctoolbarbuttonmbtextbelow"></a><a name="m_btextbelow"></a>CMFCToolBarButton::m_bTextBelow  
 Gibt an, ob die Beschriftung unter dem Bild auf der Schaltfläche angezeigt wird.  
  
```  
BOOL m_bTextBelow;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Membervariable, um festgelegt ist `TRUE`, das Framework zeigt den Text der Schaltfläche unter dem Bild. Der Standardwert dieses Elements ist `FALSE`.  
  
##  <a name="a-namembuserbuttona--cmfctoolbarbuttonmbuserbutton"></a><a name="m_buserbutton"></a>CMFCToolBarButton::m_bUserButton  
 Gibt an, ob die Schaltfläche ein benutzerdefiniertes Bild enthält  
  
```  
BOOL m_bUserButton;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieses Datenelement wird festgelegt, um `TRUE` Wenn die Schaltfläche ein benutzerdefiniertes Abbild zugeordnet ist.  
  
##  <a name="a-namembwholetexta--cmfctoolbarbuttonmbwholetext"></a><a name="m_bwholetext"></a>CMFCToolBarButton::m_bWholeText  
 Gibt an, ob die Schaltfläche die vollständige Beschriftung angezeigt, auch wenn es nicht in das Begrenzungsrechteck passt.  
  
```  
BOOL m_bWholeText;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn dieses Datenelement, um festgelegt ist `TRUE`, vom Framework die vollständige Beschriftung durch das Vergrößern der Schaltfläche angezeigt. Andernfalls das Framework abgeschnitten, und fügt Auslassungspunkte ( **... **) an die textbezeichnung.  
  
##  <a name="a-namembwrapa--cmfctoolbarbuttonmbwrap"></a><a name="m_bwrap"></a>CMFCToolBarButton::m_bWrap  
 Gibt an, ob die Schaltfläche neben einem Trennzeichen in der nächsten Zeile überführt werden sollen.  
  
```  
BOOL m_bWrap;  
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework setzt dieses Datenelement auf `TRUE` Wenn die Symbolleisten-Schaltfläche passt nicht in der aktuellen Zeile oder wenn Sie ein Layout (z. B. eine bestimmte Anzahl von Symbolleisten-Schaltflächen pro Zeile) angeben.  
  
 Das Framework setzt diese Schaltfläche in der nächsten Zeile, wenn dieses Datenelement, um festgelegt ist `TRUE` und die Symbolleiste wird horizontal gedockt oder nicht.  
  
 Der Standardwert für dieses Datenelement ist `FALSE`.  
  
##  <a name="a-namembwraptexta--cmfctoolbarbuttonmbwraptext"></a><a name="m_bwraptext"></a>CMFCToolBarButton::m_bWrapText  
 Gibt an, ob es sich bei mehrzeiligen Textfeld Bezeichnungen aktiviert sind.  
  
```  
AFX_IMPORT_DATA static BOOL m_bWrapText;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese statische Membervariable ist `TRUE`, das Framework ermöglicht allen Toolbars mehrzeilige Beschriftungen auf Symbolleisten-Schaltflächen angezeigt.  
  
 Der Standardwert für dieses Datenelement ist `FALSE`.  
  
##  <a name="a-namemnida--cmfctoolbarbuttonmnid"></a><a name="m_nid"></a>CMFCToolBarButton::m_nID  
 Die Befehls-ID der Schaltfläche.  
  
```  
UINT m_nID;  
```  
  
### <a name="remarks"></a>Hinweise  
 Befehls-ID&1; gibt an, dass die Schaltfläche ein Trennzeichen ist. Alle Trennlinien haben die `TBBS_SEPARATOR` Stil. Finden Sie unter [CMFCToolBarButton::m_nStyle](#m_nstyle) Weitere Informationen zu Schaltflächenstile.  
  
##  <a name="a-namemnstylea--cmfctoolbarbuttonmnstyle"></a><a name="m_nstyle"></a>CMFCToolBarButton::m_nStyle  
 Der Stil der Schaltfläche.  
  
```  
UINT m_nStyle;  
```  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [Steuerelementtypen für die Symbolleiste](../../mfc/reference/toolbar-control-styles.md) für die Liste der verfügbaren Symbolleiste Schaltflächenstile.  
  
##  <a name="a-namemstrtexta--cmfctoolbarbuttonmstrtext"></a><a name="m_strtext"></a>CMFCToolBarButton::m_strText  
 Die Beschriftung der Schaltfläche.  
  
```  
CString m_strText;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieses Datenelement enthält die Beschriftung der Schaltfläche. Die Beschriftung kann leer sein.  
  
##  <a name="a-namenotifycommanda--cmfctoolbarbuttonnotifycommand"></a><a name="notifycommand"></a>CMFCToolBarButton::NotifyCommand  
 Gibt an, ob die Schaltfläche verarbeitet die [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Nachricht.  
  
```  
virtual BOOL NotifyCommand(int iNotifyCode);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iNotifyCode`  
 Die Nachricht, die mit dem Befehl zugeordnet ist.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt `FALSE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode aus, wenn es senden möchten, ist ein [WM_COMMAND](http://msdn.microsoft.com/library/windows/desktop/ms647591) Nachricht an das übergeordnete Fenster.  
  
 Standardmäßig gibt diese Methode `FALSE`. Überschreiben Sie diese Methode zurückgeben `TRUE` Wenn Sie verarbeiten möchten die `WM_COMMAND` Nachricht oder `FALSE` an, dass die Nachricht von die übergeordneten Symbolleiste behandelt werden sollen.  
  
##  <a name="a-nameonaddtocustomizepagea--cmfctoolbarbuttononaddtocustomizepage"></a><a name="onaddtocustomizepage"></a>CMFCToolBarButton::OnAddToCustomizePage  
 Vom Framework aufgerufen, wenn die Schaltfläche hinzugefügt wird ein **anpassen** Dialogfeld.  
  
```  
virtual void OnAddToCustomizePage();
```  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Methode wird keine Aktion ausgeführt. Überschreiben Sie diese Methode, wenn eine bestimmte Aktion ausgeführt, wenn die Schaltfläche hinzugefügt werden soll eine **anpassen** Dialogfeld.  
  
##  <a name="a-nameonbeforedraga--cmfctoolbarbuttononbeforedrag"></a><a name="onbeforedrag"></a>CMFCToolBarButton::OnBeforeDrag  
 Gibt an, ob die Schaltfläche gezogen werden kann.  
  
```  
virtual BOOL OnBeforeDrag() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Schaltfläche gezogen werden kann; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, bevor der Benutzer beginnt, ziehen die Schaltfläche.  
  
 Gibt die standardmäßige Implementierung dieser Methode `TRUE`. Überschreiben Sie diese Methode zurückgeben `FALSE` zum Deaktivieren der Schaltfläche ziehen.  
  
##  <a name="a-nameonbeforedropa--cmfctoolbarbuttononbeforedrop"></a><a name="onbeforedrop"></a>CMFCToolBarButton::OnBeforeDrop  
 Gibt an, ob ein Benutzer die Schaltfläche auf der Symbolleiste des Ziels gelöscht werden kann.  
  
```  
virtual BOOL OnBeforeDrop(CMFCToolBar* pTarget);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pTarget`  
 Das Ziel des Drag & Drop-Vorgangs.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Schaltfläche auf der Symbolleiste des bereitgestellten Ziel gelöscht werden kann: andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, bevor eine Symbolleiste die Schaltfläche abgelegt wird.  
  
 Gibt die standardmäßige Implementierung dieser Methode `TRUE`. Überschreiben Sie diese Methode zurückgeben `FALSE` den Drop-Vorgang für das angegebene Ziel zu deaktivieren.  
  
##  <a name="a-nameoncalculatesizea--cmfctoolbarbuttononcalculatesize"></a><a name="oncalculatesize"></a>CMFCToolBarButton::OnCalculateSize  
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
 Das Framework ruft diese Methode zum Ermitteln der Größe der Symbolleisten-Schaltfläche für den angegebenen Gerätekontext und Andocken von Status.  
  
 Die standardmäßige Implementierung berücksichtigt die Text- und Image-Größe (sofern angezeigt), die Text- und Image-Positionen (den Text unter oder auf der rechten Seite des Bilds) sowie die Symbolleiste andocken Zustand.  
  
 Überschreiben Sie diese Methode, wenn Sie die Größe einer nicht standardmäßigen Schaltfläche (z. B. ein Feldschaltfläche bearbeiten) bereitstellen möchten.  
  
##  <a name="a-nameoncancelmodea--cmfctoolbarbuttononcancelmode"></a><a name="oncancelmode"></a>CMFCToolBarButton::OnCancelMode  
 Aufgerufen, behandelt der [WM_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615) Nachricht.  
  
```  
virtual void OnCancelMode();
```  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Methode wird keine Aktion ausgeführt. Wenn Sie behandeln möchten, überschreiben Sie diese Methode die [WM_CANCELMODE](http://msdn.microsoft.com/library/windows/desktop/ms632615) Nachricht.  
  
##  <a name="a-nameonchangeparentwnda--cmfctoolbarbuttononchangeparentwnd"></a><a name="onchangeparentwnd"></a>CMFCToolBarButton::OnChangeParentWnd  
 Wird vom Framework aufgerufen, wenn eine neue Symbolleiste die Schaltfläche eingefügt wird.  
  
```  
virtual void OnChangeParentWnd(CWnd* pWndParent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWndParent`  
 Das neue übergeordnete Fenster.  
  
### <a name="remarks"></a>Hinweise  
 Die Schaltfläche wird in eine Symbolleiste, z. B. eingefügt, wenn der Benutzer über eine Symbolleiste an eine andere Symbolleiste gezogen wird.  
  
 Die standardmäßige Implementierung dieser Methode wird keine Aktion ausgeführt.  
  
##  <a name="a-nameonclicka--cmfctoolbarbuttononclick"></a><a name="onclick"></a>CMFCToolBarButton::OnClick  
 Vom Framework aufgerufen, wenn der Benutzer die Maustaste klickt.  
  
```  
virtual BOOL OnClick(
    CWnd* pWnd,  
    BOOL bDelay=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 Das übergeordnete Fenster der Symbolleisten-Schaltfläche.  
  
 [in] `bDelay`  
 `TRUE`Wenn die Nachricht mit einer Verzögerung behandelt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt `FALSE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn der Benutzer die Symbolleisten-Schaltfläche klickt.  
  
 Die standardmäßige Implementierung keine Aktion aus und gibt `FALSE`. Überschreiben Sie diese Methode, um einen Wert ungleich NULL zurück, wenn die Schaltfläche, die auf-Nachricht verarbeitet.  
  
##  <a name="a-nameonclickupa--cmfctoolbarbuttononclickup"></a><a name="onclickup"></a>CMFCToolBarButton::OnClickUp  
 Wird vom Framework aufgerufen, wenn der Benutzer die Maustaste loslässt.  
  
```  
virtual BOOL OnClickUp();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt `FALSE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn der Benutzer die Symbolleisten-Schaltfläche loslässt.  
  
 Die standardmäßige Implementierung keine Aktion aus und gibt `FALSE`. Überschreiben Sie diese Methode, um einen Wert ungleich NULL zurück, wenn die Schaltfläche, die auf-Nachricht verarbeitet.  
  
##  <a name="a-nameoncontexthelpa--cmfctoolbarbuttononcontexthelp"></a><a name="oncontexthelp"></a>CMFCToolBarButton::OnContextHelp  
 Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste behandelt eine `WM_HELPHITTEST` Nachricht.  
  
```  
virtual BOOL OnContextHelp(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 Das übergeordnete Fenster der Symbolleisten-Schaltfläche.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt `FALSE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Methode führt keine Aktion aus und gibt `FALSE`. Überschreiben Sie diese Methode, um einen Wert ungleich NULL zurück, wenn die Schaltfläche hilfemeldung verarbeitet.  
  
 Weitere Informationen zu den `WM_HELPHITTEST` finden Sie unter [TN028: kontextbezogene Hilfe Support](../../mfc/tn028-context-sensitive-help-support.md).  
  
##  <a name="a-nameonctlcolora--cmfctoolbarbuttononctlcolor"></a><a name="onctlcolor"></a>CMFCToolBarButton::OnCtlColor  
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
 Die bestimmte Farbe-Benachrichtigung.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für das Brush-Objekt, das Framework verwendet, um den Hintergrund der Schaltfläche zeichnen.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, wenn die übergeordneten Symbolleiste verarbeitet die `WM_CTLCOLOR` Nachricht für eine Symbolleisten-Schaltfläche, die ein Windows-Steuerelement enthält. Das Framework wird diese Methode nicht aufrufen, wenn die Symbolleisten-Schaltfläche fensterlose ist.  
  
 Das Framework ruft diese Methode auf, wenn die Symbolleiste Framework im Anpassungsmodus und die Symbolleisten-Schaltfläche nicht gesperrt ist. Weitere Informationen zu den Anpassungsmodus, finden Sie unter [CMFCToolBar::SetCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#setcustomizemode). Weitere Informationen zum Sperren von Symbolleisten-Schaltflächen finden Sie unter [CMFCToolBarButton::IsLocked](#islocked).  
  
 Die standardmäßige Implementierung keine Aktion aus und gibt `NULL`.  
  
##  <a name="a-nameoncustomizemenua--cmfctoolbarbuttononcustomizemenu"></a><a name="oncustomizemenu"></a>CMFCToolBarButton::OnCustomizeMenu  
 Können die Schaltfläche, um die bereitgestellte Menü ändern, wenn die Anwendung auf der Symbolleiste des übergeordneten ein Kontextmenü angezeigt.  
  
```  
virtual BOOL OnCustomizeMenu(CMenu* pMenu);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pMenu`  
 Klicken Sie im Menü anpassen.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt `FALSE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung keine Aktion aus und gibt `FALSE`. Diese Methode überschreiben und einen Wert ungleich NULL zurück, wenn Sie den Inhalt des angegebenen Menüs ändern möchten.  
  
##  <a name="a-nameondblclka--cmfctoolbarbuttonondblclk"></a><a name="ondblclk"></a>CMFCToolBarButton::OnDblClk  
 Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste behandelt eine [WM_LBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms645606) Nachricht.  
  
```  
virtual void OnDblClk(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 -   Das übergeordnete Fenster der Schaltfläche.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, indem die `CMFCToolBar::OnLButtonDblClk` -Methode, wenn die übergeordneten Symbolleiste behandelt eine [WM_LBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms645606) Nachricht.  
  
 Die standardmäßige Implementierung dieser Methode wird keine Aktion ausgeführt.  
  
##  <a name="a-nameondrawa--cmfctoolbarbuttonondraw"></a><a name="ondraw"></a>CMFCToolBarButton::OnDraw  
 Vom Framework aufgerufen wird die Schaltfläche gezeichnet werden soll, mithilfe der angegebenen Formate und -Optionen.  
  
```  
virtual void OnDraw(
    CDC* pDC,  
    const CRect& rect,  
    CMFCToolBarImages* pImages,  
    BOOL bHorz=TRUE,  
    BOOL bCustomizeMode=FALSE,  
    BOOL bHighlight=FALSE,  
    BOOL bDrawBorder=TRUE,  
    BOOL bGrayDisabledButtons=TRUE);
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
  
##  <a name="a-nameondrawoncustomizelista--cmfctoolbarbuttonondrawoncustomizelist"></a><a name="ondrawoncustomizelist"></a>CMFCToolBarButton::OnDrawOnCustomizeList  
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
 Diese Methode wird aufgerufen, durch das Dialogfeld Anpassen ( **Befehle** Registerkarte) Wenn die Schaltfläche wird im Ownerdrawn-Listenfeld angezeigt.  
  
 Die standardmäßige Implementierung dieser Methode wird die Bild und die Beschriftung der Schaltfläche angezeigt, sofern diese verfügbar sind. Wenn die Beschriftung der Schaltfläche nicht verfügbar ist, zeigt die Methode den QuickInfo-Text.  
  
 Überschreiben Sie diese Methode, um eine benutzerdefinierte Zeichnung.  
  
##  <a name="a-nameongetcustomtooltiptexta--cmfctoolbarbuttonongetcustomtooltiptext"></a><a name="ongetcustomtooltiptext"></a>CMFCToolBarButton::OnGetCustomToolTipText  
 Aufgerufen, um den benutzerdefinierten QuickInfo-Text für die Schaltfläche abzurufen.  
  
```  
virtual BOOL OnGetCustomToolTipText(CString& strToolTip);
```  
  
### <a name="parameters"></a>Parameter  
 [out] `strToolTip`  
 Ein `CString` -Objekt, das den benutzerdefinierten QuickInfo-Text erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt `FALSE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode beim Anzeigen der QuickInfo für die Symbolleisten-Schaltfläche. Wenn diese Methode zurückgibt `FALSE`, verwendet das Framework eine Standard-QuickInfo.  
  
 Die standardmäßige Implementierung keine Aktion aus und gibt `FALSE`. Überschreiben Sie diese Methode, und geben Sie einen Wert ungleich Null zum Bereitstellen von benutzerdefinierten QuickInfo-Text für die Symbolleisten-Schaltfläche zurück.  
  
##  <a name="a-nameonglobalfontschangeda--cmfctoolbarbuttononglobalfontschanged"></a><a name="onglobalfontschanged"></a>CMFCToolBarButton::OnGlobalFontsChanged  
 Wird vom Framework aufgerufen, wenn die globale Schriftart geändert hat.  
  
```  
virtual void OnGlobalFontsChanged();
```  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Methode wird keine Aktion ausgeführt. Überschreiben Sie diese Methode, um die Schriftart zu aktualisieren, die verwendet wird, um den Text der Schaltfläche anzuzeigen.  
  
##  <a name="a-nameonmovea--cmfctoolbarbuttononmove"></a><a name="onmove"></a>CMFCToolBarButton::OnMove  
 Vom Framework aufgerufen, wenn die übergeordneten Symbolleiste verschoben wird.  
  
```  
virtual void OnMove();
```  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Methode wird keine Aktion ausgeführt. Überschreiben Sie diese Methode, um die Schaltfläche neu positionieren, wenn die übergeordneten Symbolleiste verschoben wird.  
  
##  <a name="a-nameonshowa--cmfctoolbarbuttononshow"></a><a name="onshow"></a>CMFCToolBarButton::OnShow  
 Vom Framework aufgerufen, wenn die Schaltfläche wird sichtbar oder unsichtbar.  
  
```  
virtual void OnShow(BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bShow`  
 Gibt an, ob die Schaltfläche sichtbar ist. Wenn dieser Parameter ist `TRUE`, die Schaltfläche sichtbar ist. Andernfalls ist die Schaltfläche nicht angezeigt.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Methode wird keine Aktion ausgeführt. Überschreiben Sie diese Methode, um die Sichtbarkeit der Schaltfläche Aktualisieren.  
  
##  <a name="a-nameonsizea--cmfctoolbarbuttononsize"></a><a name="onsize"></a>CMFCToolBarButton::OnSize  
 Wird vom Framework aufgerufen, wenn die übergeordneten Symbolleiste seine Größe ändert oder Position und diese Änderung bewirkt, dass die Schaltfläche, um die Größe zu ändern.  
  
```  
virtual void OnSize(int iSize);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iSize`  
 Die neue Breite der Schaltfläche.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Methode wird keine Aktion ausgeführt. Überschreiben Sie diese Methode, um die Schaltfläche angepasst wird, wenn die Größe oder Position der übergeordneten Symbolleiste ändert.  
  
##  <a name="a-nameontoolhittesta--cmfctoolbarbuttonontoolhittest"></a><a name="ontoolhittest"></a>CMFCToolBarButton::OnToolHitTest  
 Wird vom Framework aufgerufen, wenn die übergeordneten Symbolleiste bestimmen muss, ob ein Punkt im umschließenden Rechteck neben der Schaltfläche.  
  
```  
virtual BOOL OnToolHitTest(
    const CWnd* pWnd,  
    TOOLINFO* pTI);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pWnd`  
 Das übergeordnete Fenster der Schaltfläche. Kann `NULL`.  
  
 [in] `pTI`  
 Ein `TOOLINFO` -Struktur, die Informationen über ein Tool in einem QuickInfo-Steuerelement enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Ergebnis des `OnMenuButtonToolHitTest` , wenn die Schaltfläche einen Zeiger auf den übergeordneten Rahmenfensters; abrufen kann andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft eine der folgenden Methoden, wenn das übergeordnete Fenster mit einem gültigen Frameobjekt konvertiert werden kann:  
  
- [CMDIFrameWndEx::OnMenuButtonToolHitTest](../../mfc/reference/cmdiframewndex-class.md#onmenubuttontoolhittest)  
  
- [CFrameWndEx::OnMenuButtonToolHitTest](../../mfc/reference/cframewndex-class.md#onmenubuttontoolhittest)  
  
- [COleIPFrameWndEx::OnMenuButtonToolHitTest](../../mfc/reference/coleipframewndex-class.md#onmenubuttontoolhittest)  
  
##  <a name="a-nameonupdatetooltipa--cmfctoolbarbuttononupdatetooltip"></a><a name="onupdatetooltip"></a>CMFCToolBarButton::OnUpdateToolTip  
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
 Das übergeordnete Fenster.  
  
 [in] `iButtonIndex`  
 Der nullbasierte Index der Schaltfläche in der übergeordneten Auflistung.  
  
 [in] `wndToolTip`  
 Das Steuerelement, das den QuickInfo-Text anzeigt.  
  
 [out] `str`  
 Ein `CString` -Objekt, das den aktualisierten QuickInfo-Text erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt `FALSE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Methode führt keine Aktion aus und gibt `FALSE`. Überschreiben Sie diese Methode, um einen Wert ungleich NULL zurück, wenn Sie eine QuickInfo-Text-Zeichenfolge angeben.  
  
##  <a name="a-namepreparedraga--cmfctoolbarbuttonpreparedrag"></a><a name="preparedrag"></a>CMFCToolBarButton::PrepareDrag  
 Wird vom Framework aufgerufen, wenn die Schaltfläche ein Drag & Drop-Vorgang ausgeführt wird.  
  
```  
virtual BOOL PrepareDrag(COleDataSource& srcItem);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `srcItem`  
 Ein `COleDataSource` -Objekt, das Statusinformationen über den Drag & Drop-Vorgang gespeichert.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Vorgang erfolgreich ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode zum Vorbereiten der Symbolleisten-Schaltfläche zum Speichern von Zuständen in der bereitgestellten `COleDataSource` Objekt. Diese Methode speichert seinen Zustand selbst zu einer freigegebenen Datei serialisieren und dann diese Datei an die [COleDataSource:: CacheGlobalData](../../mfc/reference/coledatasource-class.md#cacheglobaldata) Methode. Weitere Informationen über die Symbolleisten-Schaltfläche-Serialisierung finden Sie unter [CMFCToolBarButton::Serialize](#serialize).  
  
 Diese Methode führt keine Aktion aus und gibt `TRUE` Wenn die Schaltfläche gespeichert werden kann (die [CMFCToolBarButton::CanBeStored](#canbestored) -Methode gibt `FALSE`). Es gibt `FALSE` tritt eine Ausnahme während der Serialisierung von Objekten.  
  
 Weitere Informationen zu OLE-Drag & Drop-Operationen, finden Sie unter [Drag & Drop (OLE)](../../mfc/drag-and-drop-ole.md).  
  
##  <a name="a-namerecta--cmfctoolbarbuttonrect"></a><a name="rect"></a>CMFCToolBarButton::Rect  
 Ruft das umschließende Rechteck der Schaltfläche ab.  
  
```  
const CRect& Rect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CRect` -Objekt, das das umschließende Rechteck eine Schaltfläche enthält.  
  
##  <a name="a-nameresetimagetodefaulta--cmfctoolbarbuttonresetimagetodefault"></a><a name="resetimagetodefault"></a>CMFCToolBarButton::ResetImageToDefault  
 Legt das Bild, das der Schaltfläche zugeordnet ist, auf den Standardwert fest.  
  
```  
virtual void ResetImageToDefault();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft das Standardbild aus der übergeordneten Symbolleiste ab, indem die [CMFCToolBar::GetDefaultImage](../../mfc/reference/cmfctoolbar-class.md#getdefaultimage) Methode. Wenn die Schaltfläche keine zugeordneten Standardbild besitzt, wird diese Methode die Beschriftung der Schaltfläche entsprechend der Zeichenfolgenressource mit dem [CStringT::LoadString](../../atl-mfc-shared/reference/cstringt-class.md#loadstring) Methode. Weitere Informationen zu Ressourcen finden Sie unter [arbeiten mit Ressourcendateien](../../windows/working-with-resource-files.md).  
  
 Diese Methode bewirkt nichts, wenn die Schaltfläche ein benutzerdefiniertes Abbild hat.  
  
##  <a name="a-namesavebarstatea--cmfctoolbarbuttonsavebarstate"></a><a name="savebarstate"></a>CMFCToolBarButton::SaveBarState  
 Speichert den Zustand der Symbolleisten-Schaltfläche.  
  
```  
virtual void SaveBarState();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn es erstellt ein `CMFCToolBarButton` Objekt als Ergebnis eines Drag & Drop-Vorgangs.  
  
 Die standardmäßige Implementierung dieser Methode wird keine Aktion ausgeführt. Überschreiben Sie diese Methode, um den Status der Symbolleisten-Schaltfläche in einer externen Datenquelle zu speichern.  
  
##  <a name="a-nameserializea--cmfctoolbarbuttonserialize"></a><a name="serialize"></a>CMFCToolBarButton::Serialize  
 Dieses Objekt aus dem Archiv liest oder schreibt dieses in ein Archiv.  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `ar`  
 Das `CArchive` Objekt aus dem oder in das Serialisieren.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode unterstützt Datentransfers beispielsweise bei Zwischenablage- oder Drag & Drop-Vorgänge. Er liest oder schreibt die Eigenschaften der Schaltfläche wie z. B. die ID-Bezeichnung und Bild-ID aus, oder die `CArchive` Objekt.  
  
 Beispiele zur Serialisierung finden Sie [Serialisierung: Serialisieren eines Objekts](../../mfc/serialization-serializing-an-object.md).  
  
##  <a name="a-namesetaccdataa--cmfctoolbarbuttonsetaccdata"></a><a name="setaccdata"></a>CMFCToolBarButton::SetACCData  
 Füllt die angegebene `CAccessibilityData` Objekt mit Zugriff auf Daten aus der Symbolleisten-Schaltfläche.  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pParent`  
 Das übergeordnete Fenster der Symbolleisten-Schaltfläche.  
  
 [in] `data`  
 Ein `CAccessibilityData` Objekt, das mit den Zugriff auf Daten der Symbolleisten-Schaltfläche enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt `TRUE` zurück.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode zurückgeben `FALSE` Wenn die Symbolleisten-Schaltfläche keinen Zugriff auf Daten.  
  
##  <a name="a-namesetclipboardformatnamea--cmfctoolbarbuttonsetclipboardformatname"></a><a name="setclipboardformatname"></a>CMFCToolBarButton::SetClipboardFormatName  
 Benennt das globale Zwischenablageformat.  
  
```  
static void __stdcall SetClipboardFormatName(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszName`  
 Der neue Name für das globale Zwischenablageformat. Nicht `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ermöglicht das Drag & Drop-Vorgänge für mehrere Anwendungen auftreten. Jede Anwendung muss den gleichen Zwischenablage Formatnamen angeben.  
  
 Sie müssen diese Methode vor das Framework ruft Aufrufen [CMFCToolBarButton::GetClipboardFormat](#getclipboardformat).  
  
##  <a name="a-namesetimagea--cmfctoolbarbuttonsetimage"></a><a name="setimage"></a>CMFCToolBarButton::SetImage  
 Legt den Index des Bildes der Schaltfläche fest.  
  
```  
virtual void SetImage(int iImage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iImage`  
 Der Index des Bilds in die Auflistung der Symbolleistenbilder.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Symbolleisten-Schaltfläche ein Trennzeichen ist `iImage` bezieht sich auf die Breite der Trennzeichenschaltfläche.  
  
 Wenn `iImage` ist kleiner als&0; (null), diese Methode deaktiviert das Zeichnen des Bilds und die Beschriftung der Schaltfläche zeichnen können.  
  
##  <a name="a-namesetprotectedcommandsa--cmfctoolbarbuttonsetprotectedcommands"></a><a name="setprotectedcommands"></a>CMFCToolBarButton::SetProtectedCommands  
 Legt die Liste der Befehle, die der Benutzer angepasst werden kann.  
  
```  
static void SetProtectedCommands(const CList<UINT,UINT>& lstCmds);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lstCmds`  
 Die Liste der geschützten Befehle.  
  
### <a name="remarks"></a>Hinweise  
 Im Anpassungsmodus deaktiviert das Framework Schaltfläche Befehle, die geschützt werden. Der Benutzer kann nicht ausführen von Drag & Drop und Vorgänge für deaktivierte Symbolleistenschaltflächen bearbeiten.  
  
 Verwenden der [CMFCToolBarButton::GetProtectedCommands](#getprotectedcommands) Methode zum Abrufen der Liste der Befehle geschützt.  
  
##  <a name="a-namesetradioa--cmfctoolbarbuttonsetradio"></a><a name="setradio"></a>CMFCToolBarButton::SetRadio  
 Wird vom Framework aufgerufen, wenn eine Schaltfläche dessen Aktivierungszustand ändert.  
  
```  
virtual void SetRadio();
```  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Methode wird keine Aktion ausgeführt. Überschreiben Sie diese Methode, um eine benutzerdefinierte Aktion auszuführen, wenn die Schaltfläche dessen Aktivierungszustand ändert.  
  
##  <a name="a-namesetrecta--cmfctoolbarbuttonsetrect"></a><a name="setrect"></a>CMFCToolBarButton::SetRect  
 Legt das umschließende Rechteck der Schaltfläche fest.  
  
```  
void SetRect(const CRect rect);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rect`  
 Das neue umfassende Rechteck der Schaltfläche.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft die [CMFCToolBarButton::OnMove](#onmove) -Methode auf, nachdem das neue umfassende Rechteck festgelegt.  
  
##  <a name="a-namesetstylea--cmfctoolbarbuttonsetstyle"></a><a name="setstyle"></a>CMFCToolBarButton::SetStyle  
 Legt den Stil der Schaltfläche.  
  
```  
virtual void SetStyle(UINT nStyle);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nStyle`  
 Der neue Stil der Schaltfläche.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung legt die [CMFCToolBarButton::m_nStyle](#m_nstyle) -Datenmember auf `nStyle`. Überschreiben Sie diese Methode, wenn Sie zusätzliche Verarbeitung auszuführen, um die Änderung im Stil behandeln möchten. Finden Sie unter [Steuerelementtypen für die Symbolleiste](toolbar-control-styles.md) eine Liste der gültigen Formatflags.  
  
##  <a name="a-namesetvisiblea--cmfctoolbarbuttonsetvisible"></a><a name="setvisible"></a>CMFCToolBarButton::SetVisible  
 Gibt an, ob die Schaltfläche sichtbar ist.  
  
```  
void SetVisible(BOOL bShow=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bShow`  
 Ein boolescher Wert, der angibt, ob die Schaltfläche ein- oder auszublenden. Wenn dieser Parameter ist `TRUE`, die Schaltfläche wird angezeigt. Wenn der Parameter `FALSE`, ist die Schaltfläche ausgeblendet wird.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um eine bestimmte Symbolleisten-Schaltfläche anzeigen oder ausblenden. Rufen Sie die [CPane::AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate) -Methode auf, nachdem Sie diese Methode aufrufen.  
  
##  <a name="a-nameshowa--cmfctoolbarbuttonshow"></a><a name="show"></a>CMFCToolBarButton::Show  
 Anzeigen oder Ausblenden der Schaltfläche.  
  
```  
void Show(BOOL bShow);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bShow`  
 Ein boolescher Wert, der angibt, ob die Schaltfläche ein- oder auszublenden. Wenn dieser Parameter ist `TRUE`, die Schaltfläche wird angezeigt. Wenn der Parameter `FALSE`, ist die Schaltfläche ausgeblendet wird.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode, um die Sichtbarkeit der Schaltflächen der Symbolleiste beim Ändern der Größe ihrer übergeordneten Symbolleiste zu aktualisieren. Das Framework ruft diese Methode mit `bShow` festgelegt `FALSE` Wenn die Schaltfläche nicht mehr innerhalb der Grenzen der Symbolleiste passt. Das Framework ruft diese Methode mit `bShow` festgelegt `TRUE` Wenn nach dem Ändern der Größe der Schaltfläche wieder innerhalb der Grenzen der Symbolleiste geeignet ist.  
  
 Verwenden der [CMFCToolBarButton::SetVisible](#setvisible) Methode, um die allgemeine Sichtbarkeit der Schaltfläche festzulegen.  
  
 Diese Methode ruft die [CMFCToolBarButton::OnShow](#onshow) -Methode auf, nachdem sie den Sichtbarkeitsstatus der Schaltfläche aktualisiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarImages-Klasse](../../mfc/reference/cmfctoolbarimages-class.md)

