---
title: CStatusBar-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStatusBar
- AFXEXT/CStatusBar
- AFXEXT/CStatusBar::CStatusBar
- AFXEXT/CStatusBar::CommandToIndex
- AFXEXT/CStatusBar::Create
- AFXEXT/CStatusBar::CreateEx
- AFXEXT/CStatusBar::DrawItem
- AFXEXT/CStatusBar::GetItemID
- AFXEXT/CStatusBar::GetItemRect
- AFXEXT/CStatusBar::GetPaneInfo
- AFXEXT/CStatusBar::GetPaneStyle
- AFXEXT/CStatusBar::GetPaneText
- AFXEXT/CStatusBar::GetStatusBarCtrl
- AFXEXT/CStatusBar::SetIndicators
- AFXEXT/CStatusBar::SetPaneInfo
- AFXEXT/CStatusBar::SetPaneStyle
- AFXEXT/CStatusBar::SetPaneText
dev_langs:
- C++
helpviewer_keywords:
- indicators, status bar
- CStatusBar class
- status bars
- indicators
- status indicators
ms.assetid: a3bde3db-e71c-4881-a3ca-1d5481c345ba
caps.latest.revision: 24
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
ms.openlocfilehash: e96070041ef5bcee0865991a14b6484082d8fc91
ms.lasthandoff: 02/24/2017

---
# <a name="cstatusbar-class"></a>CStatusBar-Klasse
Eine Steuerleiste mit einer Zeile von Textausgabebereichen ("Indikatoren" genannt).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CStatusBar : public CControlBar  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStatusBar::CStatusBar](#cstatusbar)|Erstellt ein `CStatusBar`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CStatusBar::CommandToIndex](#commandtoindex)|Ruft Index für einen bestimmten Indikator-ID.|  
|[CStatusBar::Create](#create)|Die Statusleiste erstellt wird, fügt es die `CStatusBar` -Objekt und legt die anfängliche Höhe der Schriftart und Balken.|  
|[CStatusBar:: CreateEx](#createex)|Erstellt eine `CStatusBar` Objekt mit Weitere Formate für das eingebettete `CStatusBarCtrl` Objekt.|  
|[CStatusBar::DrawItem](#drawitem)|Wird aufgerufen, wenn sich ein Darstellungsaspekt eines ownerdrawn Statusleisten-Steuerelement ändert.|  
|[CStatusBar::GetItemID](#getitemid)|Ruft den Indikator-ID für einen bestimmten Index ab.|  
|[CStatusBar::GetItemRect](#getitemrect)|Ruft anzeigen Rechteck für einen bestimmten index|  
|[CStatusBar::GetPaneInfo](#getpaneinfo)|Ruft Indikator-ID, Stil und die Breite für einen bestimmten Index ab.|  
|[CStatusBar::GetPaneStyle](#getpanestyle)|Ruft die indikatorart für einen bestimmten Index ab.|  
|[CStatusBar::GetPaneText](#getpanetext)|Ruft den Text fest, der für einen bestimmten Index ab.|  
|[GetStatusBarCtrl](#getstatusbarctrl)|Ermöglicht den direkten Zugriff auf das zugrunde liegende Standardsteuerelement.|  
|[CStatusBar:: SetIndicators](#setindicators)|Legt die Symbol-IDs.|  
|[CStatusBar::SetPaneInfo](#setpaneinfo)|Indikator-ID, Stil und Breite für einen bestimmten Index festgelegt.|  
|[CStatusBar::SetPaneStyle](#setpanestyle)|Legt die indikatorart für einen bestimmten Index fest.|  
|[CStatusBar::SetPaneText](#setpanetext)|Legt Text fest, der für einen bestimmten Index fest.|  
  
## <a name="remarks"></a>Hinweise  
 Der Ausgabebereiche werden häufig als Nachricht Linien und Statusanzeigen verwendet. Beispiele sind die im Menü Hilfe-Message-Zeilen, die kurz den Menübefehl und die Indikatoren, die den Status der Rollen, NUM-Taste und andere Schlüssel anzuzeigen.  
  
 [GetStatusBarCtrl](#getstatusbarctrl), eine Memberfunktion neue MFC 4.0, können Sie die allgemeinen Windows-Steuerelements-Unterstützung für die Statusleiste anpassen und zusätzliche Funktionen nutzen. `CStatusBar`Member-Funktionen bieten Ihnen die meisten Funktionen des allgemeinen Windows-Steuerelemente; allerdings beim Aufruf `GetStatusBarCtrl`, Sie können den Statusleisten geben auch weitere Merkmale einer Statusleiste Windows 95-und Windows 98. Beim Aufruf von `GetStatusBarCtrl`, es gibt einen Verweis auf ein `CStatusBarCtrl` Objekt. Finden Sie unter [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) für Weitere Informationen zum Entwerfen von Symbolleisten mithilfe der allgemeinen Windows-Steuerelemente. Weitere allgemeine Informationen über allgemeine Steuerelemente, finden Sie unter [Standardsteuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb775493) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Das Framework speichert Indikatorinformationen in einem Array mit den am weitesten links stehende Indikator an Position 0. Wenn Sie eine Statusleiste erstellen, verwenden Sie ein Array von Zeichenfolgen-IDs, die das Framework die entsprechenden Indikatoren zuordnet. Eine Zeichenfolgen-ID oder einen Index können dann einen Indikator zugreifen.  
  
 Standardmäßig ist der erste Indikator "elastisch": Es nimmt die Statusleiste Länge, die nicht von den anderen Indikator Bereichen verwendet, damit die anderen Bereiche sind rechts ausgerichtet.  
  
 Gehen Sie folgendermaßen vor, um eine Statusleiste zu erstellen:  
  
1.  Erstellen der `CStatusBar` Objekt.  
  
2.  Rufen Sie die [erstellen](#create) (oder [CreateEx](#createex)) Funktion, um das Fenster mit der Statusleiste erstellen und Anfügen an die `CStatusBar` Objekt.  
  
3.  Rufen Sie [SetIndicators](#setindicators) jedes Indikators eine Zeichenfolgen-ID zugeordnet.  
  
 Es gibt drei Möglichkeiten, den Text in einer Statusleiste zu aktualisieren:  
  
1.  Rufen Sie [CWnd::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) um den Text im Bereich 0 nur aktualisieren.  
  
2.  Rufen Sie [CCmdUI::SetText](../../mfc/reference/ccmdui-class.md#settext) in der Statusleiste `ON_UPDATE_COMMAND_UI` Handler.  
  
3.  Rufen Sie [SetPaneText aufgerufen wird](#setpanetext) um den Text für einen beliebigen Bereich aktualisieren.  
  
 Rufen Sie [SetPaneStyle](#setpanestyle) die Farbe eines Statusleiste angezeigt.  
  
 Weitere Informationen zur Verwendung von `CStatusBar`, finden Sie im Artikel [Status Leiste Implementierung in MFC](../../mfc/status-bar-implementation-in-mfc.md) und [Technische Hinweis 31: Steuerleisten](../../mfc/tn031-control-bars.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CStatusBar`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxext.h  
  
##  <a name="commandtoindex"></a>CStatusBar::CommandToIndex  
 Ruft den Indikator Index für eine angegebene-ID.  
  
```  
int CommandToIndex(UINT nIDFind) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIDFind`  
 Zeichenfolgen Sie-ID des Indikators, dessen Index ist, abgerufen werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des Indikators, wenn erfolgreich; -1, wenn nicht erfolgreich.  
  
### <a name="remarks"></a>Hinweise  
 Der Index des ersten Indikators ist 0.  
  
##  <a name="create"></a>CStatusBar::Create  
 Erstellt eine Statusleiste (ein untergeordnetes Fenster), und ordnet sie der `CStatusBar` Objekt.  
  
```  
virtual BOOL Create(
    CWnd* pParentWnd,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentWnd`  
 Zeiger auf die [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, dessen Windows-Fenster das übergeordnete Element der Statusleiste ist.  
  
 `dwStyle`  
 Die Statusleiste. Zusätzlich zu den standardmäßigen Windows [Stile](../../mfc/reference/window-styles.md), diese Formate werden unterstützt.  
  
- `CBRS_TOP`Steuerleiste ist am Anfang Rahmenfenster.  
  
- `CBRS_BOTTOM`Steuerleiste ist am unteren Rand Rahmenfenster.  
  
- `CBRS_NOALIGN`Steuerleiste ist nicht neu angeordnet, die übergeordnetem Element geändert wird.  
  
 `nID`  
 Die Symbolleiste untergeordneten Fensters-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Außerdem legt die ursprüngliche Schriftart und den Status des Balkens Höhe auf einen Standardwert.  
  
##  <a name="createex"></a>CStatusBar:: CreateEx  
 Rufen Sie diese Funktion zum Erstellen einer Statusleiste (ein untergeordnetes Fenster), und ordnen sie die `CStatusBar` Objekt.  
  
```  
virtual BOOL CreateEx(
    CWnd* pParentWnd,  
    DWORD dwCtrlStyle = 0,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,  
    UINT nID = AFX_IDW_STATUS_BAR);
```  
  
### <a name="parameters"></a>Parameter  
 `pParentWnd`  
 Zeiger auf die [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, dessen Windows-Fenster das übergeordnete Element der Statusleiste ist.  
  
 `dwCtrlStyle`  
 Weitere Formate für die Erstellung der eingebetteten [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) Objekt. Der Standardwert gibt an, eine Statusleiste, ohne einen Größenziehpunkt oder eine QuickInfo zu unterstützen. Status Leiste Stile unterstützt werden:  
  
- **SBARS_SIZEGRIP** Statusleisten-Steuerelements einen Größenziehpunkt am rechten Ende der Statusleiste enthält. Ein Größenziehpunkt ähnelt einem Rahmen. Es ist ein Rechteck, das der Benutzer klicken und ziehen die Größe des übergeordneten Fensters ändern kann.  
  
- **SBT_TOOLTIPS** die Statusleiste QuickInfos unterstützt.  
  
 Weitere Informationen zu diesen Formaten finden Sie unter [Einstellungen für CStatusBarCtrl](../../mfc/settings-for-the-cstatusbarctrl.md).  
  
 `dwStyle`  
 Die Balkenart Status. Der Standardwert gibt an, dass es sich bei eine sichtbar Statusleiste am unteren Rand des Rahmenfensters erstellt werden. Wenden Sie eine beliebige Kombination von Steuerelementtypen aufgeführt, die der Statusleiste [Fensterstile](../../mfc/reference/window-styles.md) und [CDialogBar::Create](../../mfc/reference/cdialogbar-class.md#create). Dieser Parameter sollte jedoch immer die Formate WS_CHILD und WS_VISIBLE enthalten.  
  
 `nID`  
 Die Statusleiste untergeordneten Fensters-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion auch legt die ursprüngliche Schriftart und den Status des Balkens Höhe auf einen Standardwert.  
  
 Verwendung `CreateEx`, anstelle von [erstellen](#create), wenn bestimmte Formatvorlagen während der Erstellung der eingebetteten Statusleiste-Steuerelement vorhanden sein müssen. Legen Sie z. B. `dwCtrlStyle` auf **SBT_TOOLTIPS** zum Anzeigen von QuickInfos in einem Status Bar-Objekt.  
  
##  <a name="cstatusbar"></a>CStatusBar::CStatusBar  
 Erstellt ein `CStatusBar` -Objekt, eine Statusleiste Standardschriftart bei Bedarf erstellt und Eigenschaften der Schriftart auf Standardwerte festgelegt.  
  
```  
CStatusBar();
```  
  
##  <a name="drawitem"></a>CStatusBar::DrawItem  
 Diese Memberfunktion wird von dem Framework, wenn sich ein Darstellungsaspekt eines ownerdrawn Statusleisten ändert aufgerufen.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpDrawItemStruct`  
 Ein Zeiger auf eine [DRAWITEMSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb775802) -Struktur, die Informationen über den Typ der erforderlichen Zeichnung enthält.  
  
### <a name="remarks"></a>Hinweise  
 Die **ItemAction** Mitglied der `DRAWITEMSTRUCT` Struktur definiert die Zeichnen-Aktion, die ausgeführt werden soll. Überschreiben Sie diese Memberfunktion zum Implementieren der Zeichnung für eine Ownerdrawn- `CStatusBar` Objekt. Die Anwendung sollte alle Grafiken Device Interface (GDI) Objekte ausgewählt, für der Anzeigekontext im angegebenen wiederherstellen `lpDrawItemStruct` vor dem Beenden von dieser Memberfunktion.  
  
##  <a name="getitemid"></a>CStatusBar::GetItemID  
 Gibt die ID des Indikators für den angegebenen `nIndex`.  
  
```  
UINT GetItemID(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der Index des Indikators, deren ID wird abgerufen werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Die ID des Indikators für den angegebenen `nIndex`.  
  
##  <a name="getitemrect"></a>CStatusBar::GetItemRect  
 Kopiert die Koordinaten des Indikators für den angegebenen `nIndex` in die Struktur, die auf den `lpRect`.  
  
```  
void GetItemRect(
    int nIndex,  
    LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der Index des Indikators, dessen Koordinaten für das Rechteck abgerufen werden sollen.  
  
 `lpRect`  
 Verweist auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur oder ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das die Koordinaten des Indikators für den angegebenen erhalten `nIndex`.  
  
### <a name="remarks"></a>Hinweise  
 Koordinaten werden in Pixel relativ zu der oberen linken Ecke der Statusleiste.  
  
##  <a name="getpaneinfo"></a>CStatusBar::GetPaneInfo  
 Legt `nID`, `nStyle`, und `cxWidth` -ID, Stil und Breite des Bereichs Indikator am angegebenen Speicherort `nIndex`.  
  
```  
void GetPaneInfo(
    int nIndex,  
    UINT& nID,  
    UINT& nStyle,  
    int& cxWidth) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der Index des Bereichs, dessen Informationen wird abgerufen werden sollen.  
  
 `nID`  
 Ein Verweis auf eine **UINT** , die auf die ID des Bereichs festgelegt wird.  
  
 `nStyle`  
 Ein Verweis auf eine **UINT** , die das Format der Bereich festgelegt ist.  
  
 `cxWidth`  
 Verweis auf eine ganze Zahl, die die Breite des Bereichs festgelegt wird.  
  
##  <a name="getpanestyle"></a>CStatusBar::GetPaneStyle  
 Rufen Sie diese Memberfunktion, um den Stil der Statusleiste Bereich abzurufen.  
  
```  
UINT GetPaneStyle(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der Index des Bereichs, dessen Stil wird abgerufen werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Das Format der Statusleiste angegebenen `nIndex`.  
  
### <a name="remarks"></a>Hinweise  
 Ein Bereich Stil bestimmt, wie der Bereich angezeigt wird.  
  
 Eine Liste der verfügbaren Statusleisten, finden Sie unter [erstellen](#create).  
  
##  <a name="getpanetext"></a>CStatusBar::GetPaneText  
 Rufen Sie diese Memberfunktion zum Abrufen des Texts, der in einer Statusleiste angezeigt wird.  
  
```  
CString GetPaneText(int nIndex) const;  void GetPaneText(int nIndex, CString& rString) const;  ```  
  
### Parameters  
 `nIndex`  
 Index of the pane whose text is to be retrieved.  
  
 `rString`  
 A reference to a [CString](../../atl-mfc-shared/reference/cstringt-class.md) object that contains the text to be retrieved.  
  
### Return Value  
 A `CString` object containing the pane's text.  
  
### Remarks  
 The second form of this member function fills a `CString` object with the string text.  
  
##  <a name="getstatusbarctrl"></a>  CStatusBar::GetStatusBarCtrl  
 This member function allows direct access to the underlying common control.  
  
```  
CStatusBarCtrl & GetStatusBarCtrl() const;  
```  
  
### Return Value  
 Contains a reference to a [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) object.  
  
### Remarks  
 Use `GetStatusBarCtrl` to take advantage of the functionality of the Windows status-bar common control, and to take advantage of the support [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md) provides for status-bar customization. For example, by using the common control, you can specify a style that includes a sizing grip on the status bar, or you can specify a style to have the status bar appear at the top of the parent window's client area.  
  
 For more general information about common controls, See [Common Controls](http://msdn.microsoft.com/library/windows/desktop/bb775493) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setindicators"></a>  CStatusBar::SetIndicators  
 Sets each indicator's ID to the value specified by the corresponding element of the array `lpIDArray`, loads the string resource specified by each ID, and sets the indicator's text to the string.  
  
```  
BOOL SetIndicators (const UINT * LpIDArray,  
    Int nIDCount);
```  
  
### Parameters  
 `lpIDArray`  
 Pointer to an array of IDs.  
  
 `nIDCount`  
 Number of elements in the array pointed to by `lpIDArray`.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
##  <a name="setpaneinfo"></a>  CStatusBar::SetPaneInfo  
 Sets the specified indicator pane to a new ID, style, and width.  
  
```  
void SetPaneInfo (Int nIndex,  
    UINT nID  
    UINT-nStyle  
    Int CxWidth);
```  
  
### Parameters  
 `nIndex`  
 Index of the indicator pane whose style is to be set.  
  
 `nID`  
 New ID for the indicator pane.  
  
 `nStyle`  
 New style for the indicator pane.  
  
 `cxWidth`  
 New width for the indicator pane.  
  
### Remarks  
 The following indicator styles are supported:  
  
- **SBPS_NOBORDERS** No 3-D border around the pane.  
  
- **SBPS_POPOUT** Reverse border so that text "pops out."  
  
- **SBPS_DISABLED** Do not draw text.  
  
- **SBPS_STRETCH** Stretch pane to fill unused space. Only one pane per status bar can have this style.  
  
- **SBPS_NORMAL** No stretch, borders, or pop-out.  
  
##  <a name="setpanestyle"></a>  CStatusBar::SetPaneStyle  
 Call this member function to set the style of a status bar's pane.  
  
```  
void SetPaneStyle (Int nIndex,  
    UINT-nStyle);
```  
  
### Parameters  
 `nIndex`  
 Index of the pane whose style is to be set.  
  
 `nStyle`  
 Style of the pane whose style is to be set.  
  
### Remarks  
 A pane's style determines how the pane appears.  
  
 For a list of styles available for status bars, see [SetPaneInfo](#setpaneinfo).  
  
##  <a name="setpanetext"></a>  CStatusBar::SetPaneText  
 Call this member function to set the pane text to the string pointed to by `lpszNewText`.  
  
```  
BOOL SetPaneText aufgerufen wird (Int nIndex,  
    LPCTSTR LpszNewText,  
    BOOL bUpdate = TRUE);
```  
  
### Parameters  
 `nIndex`  
 Index of the pane whose text is to be set.  
  
 `lpszNewText`  
 Pointer to the new pane text.  
  
 *bUpdate*  
 If **TRUE**, the pane is invalidated after the text is set.  
  
### Return Value  
 Nonzero if successful; otherwise 0.  
  
### Remarks  
 After you call `SetPaneText`, you must add a UI update handler to display the new text in the status bar.  
  
### Example  
 [!code-cpp[NVC_MFCDocView#176](../../mfc/codesnippet/cpp/cstatusbar-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#177](../../mfc/codesnippet/cpp/cstatusbar-class_2.cpp)]  
  
 [!code-cpp[NVC_MFCDocView#178](../../mfc/codesnippet/cpp/cstatusbar-class_3.cpp)]  
  
## See Also  
 [MFC Sample CTRLBARS](../../visual-cpp-samples.md)   
 [MFC Sample DLGCBR32](../../visual-cpp-samples.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [CStatusBarCtrl Class](../../mfc/reference/cstatusbarctrl-class.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)

