---
title: CPaneDialog-Klasse
ms.date: 11/04/2016
f1_keywords:
- CPaneDialog
- AFXPANEDIALOG/CPaneDialog
- AFXPANEDIALOG/CPaneDialog::Create
- AFXPANEDIALOG/CPaneDialog::HandleInitDialog
- AFXPANEDIALOG/CPaneDialog::SetOccDialogInfo
helpviewer_keywords:
- CPaneDialog [MFC], Create
- CPaneDialog [MFC], HandleInitDialog
- CPaneDialog [MFC], SetOccDialogInfo
ms.assetid: 48a6bb91-4b92-40f5-8907-b3270b146cf6
ms.openlocfilehash: 16aa707792cc1289ced380e54abef3f15289e7cf
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57274556"
---
# <a name="cpanedialog-class"></a>CPaneDialog-Klasse

Die `CPaneDialog` Klasse unterstützt ein nicht modales, andockbares Dialogfeld.

## <a name="syntax"></a>Syntax

```
class CPaneDialog : public CDockablePane
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|`CPaneDialog::CPaneDialog`|Standardkonstruktor|
|`CPaneDialog::~CPaneDialog`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CPaneDialog::Create](#create)|Erstellt ein andockbares Dialogfeld und fügt sie an einer `CPaneDialog` Objekt.|
|`CPaneDialog::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|
|`CPaneDialog::GetThisClass`|Durch das Framework verwendet wird, einen Zeiger zum Abrufen der [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|
|[CPaneDialog::HandleInitDialog](#handleinitdialog)|Verarbeitet die [WM_INITDIALOG](/windows/desktop/dlgbox/wm-initdialog) Nachricht. (Neu definiert `CBasePane::HandleInitDialog`.)|
|`CPaneDialog::OnEraseBkgnd`|Verarbeitet die [WM_ERASEBKGND](/windows/desktop/winmsg/wm-erasebkgnd) Nachricht. (Neu definiert [CWnd::OnEraseBkgnd](../../mfc/reference/cwnd-class.md#onerasebkgnd).)|
|`CPaneDialog::OnLButtonDblClk`|Verarbeitet die [WM_LBUTTONDBLCLK](/windows/desktop/inputdev/wm-lbuttondblclk) Nachricht. (Neu definiert [CWnd::OnLButtonDblClk](../../mfc/reference/cwnd-class.md#onlbuttondblclk).)|
|`CPaneDialog::OnLButtonDown`|Verarbeitet die [WM_LBUTTONDOWN](/windows/desktop/inputdev/wm-lbuttondown) Nachricht. (Neu definiert [CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown).)|
|`CPaneDialog::OnUpdateCmdUI`|Wird aufgerufen, durch das Framework das Dialogfeldfenster zu aktualisieren. (Überschreibt [CDockablePane:: OnUpdateCmdUI](cdockablepane-class.md).)|
|`CPaneDialog::OnWindowPosChanging`|Verarbeitet die [WM_WINDOWPOSCHANGING](/windows/desktop/winmsg/wm-windowposchanging) Nachricht. (Neu definiert [CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging).)|
|[CPaneDialog::SetOccDialogInfo](#setoccdialoginfo)|Gibt die Vorlage für ein Dialogfeld, das einen OLE-Container-Steuerelement ist.|

## <a name="remarks"></a>Hinweise

Erstellen einer `CPaneDialog` Objekt in zwei Schritten. Erstellen Sie zunächst das Objekt in Ihrem Code. Rufen Sie zweitens [CPaneDialog::Create](#create). Sie geben Sie eine gültige Ressource Vorlage Namen oder der Vorlage-ID und einen Zeiger auf das übergeordnete Fenster übergeben. Andernfalls schlägt der Erstellungsvorgang. Das Dialogfeld muss es sich um das WS_CHILD und WS_VISIBLE-Format angeben. Es wird empfohlen, dass Sie auch die Stile WS_CLIPCHILDREN und WS_CLIPSIBLINGS angeben. Weitere Informationen finden Sie unter [Window-Stile](styles-used-by-mfc.md#window-styles).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CDockablePane](../../mfc/reference/cdockablepane-class.md)

[CPaneDialog](../../mfc/reference/cpanedialog-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxpanedialog.h

##  <a name="create"></a>  CPaneDialog::Create

Erstellt einen andockbaren Dialogfeld und fügt sie an einer `CPaneDialog` Objekt.

```
BOOL Create(
    LPCTSTR lpszWindowName,
    CWnd* pParentWnd,
    BOOL bHasGripper,
    LPCTSTR lpszTemplateName,
    UINT nStyle,
    UINT nID,
    DWORD dwTabbedStyle= AFX_CBRS_REGULAR_TABS,
    DWORD dwControlBarStyle=AFX_DEFAULT_DOCKING_PANE_STYLE);

BOOL Create(
    LPCTSTR lpszWindowName,
    CWnd* pParentWnd,
    BOOL bHasGripper,
    UINT nIDTemplate,
    UINT nStyle,
    UINT nID);

BOOL Create(
    CWnd* pParentWnd,
    LPCTSTR lpszTemplateName,
    UINT nStyle,
    UINT nID);

BOOL Create(
    CWnd* pParentWnd,
    UINT nIDTemplate,
    UINT nStyle,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*lpszWindowName*<br/>
[in] Der Name des im Dialogfeld andocken.

*pParentWnd*<br/>
[in] Verweist auf das übergeordnete Fenster.

*bHasGripper*<br/>
[in] "True", erstellen Sie im Dialogfeld Andocken mit Beschriftung (Ziehpunkt); andernfalls "false".

*lpszTemplateName*<br/>
[in] Der Name der Ressource Dialogfeldvorlage.

*nStyle*<br/>
[in] Der Windows-Stil.

*nID*<br/>
[in] Die Steuerelement-ID.

*nIDTemplate*<br/>
[in] Die Ressourcen-ID der Dialogfeldvorlage.

*dwTabbedStyle*<br/>
[in] Der Stil des Fensters im Registerkartenformat, die sich ergibt, wenn der Benutzer ein anderes Steuerelement im Bereich auf die Beschriftung des in diesem Bereich Steuerelement zieht. Der Standardwert ist AFX_CBRS_REGULAR_TABS. Weitere Informationen finden Sie im Abschnitt "Hinweise" der [cbasepane:: CreateEx](../../mfc/reference/cbasepane-class.md#createex) Methode.

*dwControlBarStyle*<br/>
[in] Zusätzliche Formatattribute. Der Standardwert ist AFX_DEFAULT_DOCKING_PANE_STYLE. Weitere Informationen finden Sie im Abschnitt "Hinweise" der [cbasepane:: CreateEx](../../mfc/reference/cbasepane-class.md#createex) Methode.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie die `Create` -Methode in der die `CPaneDialog` Klasse. In diesem Beispiel ist Teil der [legen Sie die Größe Beispiel](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_SetPaneSize#2](../../mfc/reference/codesnippet/cpp/cpanedialog-class_1.h)]
[!code-cpp[NVC_MFC_SetPaneSize#3](../../mfc/reference/codesnippet/cpp/cpanedialog-class_2.cpp)]

##  <a name="handleinitdialog"></a>  CPaneDialog::HandleInitDialog

Verarbeitet die [WM_INITDIALOG](/windows/desktop/dlgbox/wm-initdialog) Nachricht.

```
afx_msg LRESULT HandleInitDialog(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parameter

*wParam*<br/>
[in] Handle für das Steuerelement, das den Standard-Tastaturfokus erhalten.

*lParam*<br/>
[in] Gibt zusätzliche Initialisierung der Daten.

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false". "True" legt darüber hinaus den Tastaturfokus fest, auf das Steuerelement, das gemäß der *wParam* -Parameter ist. "False" wird verhindert, dass den Standard-Tastaturfokus festlegen.

### <a name="remarks"></a>Hinweise

Das Framework verwendet diese Methode, um Steuerelemente und die Darstellung eines Dialogfelds zu initialisieren. Das Framework ruft diese Methode auf, bevor Sie das Dialogfeld angezeigt.

##  <a name="setoccdialoginfo"></a>  CPaneDialog::SetOccDialogInfo

Gibt die Vorlage für ein Dialogfeld, das einen OLE-Container-Steuerelement ist.

```
virtual BOOL SetOccDialogInfo(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```

### <a name="parameters"></a>Parameter

*pOccDialogInfo*<br/>
[in] Zeiger auf eine Dialogfeldvorlage, die verwendet wird, um den Dialog Box-Objekt zu erstellen. Der Wert dieses Parameters wird anschließend übergeben, in der [COccManager::CreateDlgControls](../../mfc/reference/coccmanager-class.md#createdlgcontrols) Methode.

### <a name="return-value"></a>Rückgabewert

Immer "true".

### <a name="remarks"></a>Hinweise

Diese Methode unterstützt die [COccManager](../../mfc/reference/coccmanager-class.md) -Klasse, die OLE-controlsites und ActiveX-Steuerelemente verwaltet. Die _AFX_OCC_DIALOG_INFO-Struktur wird in der Headerdatei afxocc.h definiert.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md)<br/>
[Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles)
