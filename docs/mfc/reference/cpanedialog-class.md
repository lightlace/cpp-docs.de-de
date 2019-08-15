---
title: Cpanedialog-Klasse
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
ms.openlocfilehash: e7ff55e37194d0fa405925e4b3895428cfcaf9eb
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502983"
---
# <a name="cpanedialog-class"></a>Cpanedialog-Klasse

Die `CPaneDialog` -Klasse unterstützt ein nicht modalem, Andock bares Dialogfeld.

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
|[CPaneDialog::Create](#create)|Erstellt ein Andock bares Dialogfeld und fügt es an `CPaneDialog` ein-Objekt an.|
|`CPaneDialog::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|
|`CPaneDialog::GetThisClass`|Wird vom Framework verwendet, um einen Zeiger auf das [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt abzurufen, das diesem Klassentyp zugeordnet ist.|
|[CPaneDialog::HandleInitDialog](#handleinitdialog)|Verarbeitet die [WM_INITDIALOG](/windows/win32/dlgbox/wm-initdialog) -Meldung. (Definiert `CBasePane::HandleInitDialog`neu.)|
|`CPaneDialog::OnEraseBkgnd`|Verarbeitet die [WM_ERASEBKGND](/windows/win32/winmsg/wm-erasebkgnd) -Meldung. (Definiert [CWnd:: onerasebkgnd](../../mfc/reference/cwnd-class.md#onerasebkgnd)neu.)|
|`CPaneDialog::OnLButtonDblClk`|Verarbeitet die [WM_LBUTTONDBLCLK](/windows/win32/inputdev/wm-lbuttondblclk) -Meldung. (Definiert [CWnd:: OnLButtonDblClk](../../mfc/reference/cwnd-class.md#onlbuttondblclk)neu.)|
|`CPaneDialog::OnLButtonDown`|Verarbeitet die [WM_LBUTTONDOWN](/windows/win32/inputdev/wm-lbuttondown) -Meldung. (Definiert [CWnd:: OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown)neu.)|
|`CPaneDialog::OnUpdateCmdUI`|Wird von Framework aufgerufen, um das Dialogfeld Fenster zu aktualisieren. (Überschreibt [CDockablePane:: OnUpdateCmdUI](cdockablepane-class.md).)|
|`CPaneDialog::OnWindowPosChanging`|Verarbeitet die [WM_WINDOWPOSCHANGING](/windows/win32/winmsg/wm-windowposchanging) -Meldung. (Definiert [CWnd:: onwindowposchanging](../../mfc/reference/cwnd-class.md#onwindowposchanging)neu.)|
|[CPaneDialog::SetOccDialogInfo](#setoccdialoginfo)|Gibt die Vorlage für ein Dialogfeld an, das ein OLE-Steuerelement Container ist.|

## <a name="remarks"></a>Hinweise

Erstellen Sie `CPaneDialog` ein-Objekt in zwei Schritten. Erstellen Sie zunächst das-Objekt im Code. Rufen Sie anschließend [cpanedialog:: Create](#create)auf. Sie müssen einen gültigen Namen für die Ressourcen Vorlage oder eine Vorlagen-ID angeben und einen Zeiger an das übergeordnete Fenster übergeben. Andernfalls schlägt der Erstellungs Vorgang fehl. Im Dialogfeld muss der Stil WS_CHILD und WS_VISIBLE angegeben werden. Es wird empfohlen, dass Sie auch die Stile WS_CLIPCHILDREN und WS_CLIPSIBLINGS angeben. Weitere Informationen finden Sie unter [Fenster Stile](styles-used-by-mfc.md#window-styles).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CDockablePane](../../mfc/reference/cdockablepane-class.md)

[CPaneDialog](../../mfc/reference/cpanedialog-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxpanedialog. h

##  <a name="create"></a>Cpanedialog:: Create

Erstellt ein Andock Dialogfeld und fügt es `CPaneDialog` an ein-Objekt an.

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
in Der Name des Andock Dialogfelds.

*pParentWnd*<br/>
in Zeigt auf das übergeordnete Fenster.

*bHasGripper*<br/>
in TRUE, um das Andocken-Dialogfeld mit einer Beschriftung (Greifer) zu erstellen. andernfalls false.

*lpszTemplateName*<br/>
in Der Name der Ressourcen Dialogvorlage.

*nStyle*<br/>
in Der Windows-Stil.

*nID*<br/>
in Die Steuerelement-ID.

*nIDTemplate*<br/>
in Die Ressourcen-ID der Dialogfeld Vorlage.

*dwTabbedStyle*<br/>
in Der Stil des Fensters im Registerkarten Format, das sich ergibt, wenn der Benutzer einen anderen Steuerungs Bereich auf die Beschriftung dieses Steuerelement Bereichs zieht. Der Standardwert ist AFX_CBRS_REGULAR_TABS. Weitere Informationen finden Sie im Abschnitt "Hinweise" der Methode " [cbasepane:: kreateex](../../mfc/reference/cbasepane-class.md#createex) ".

*dwControlBarStyle*<br/>
in Zusätzliche Stil Attribute. Der Standardwert ist AFX_DEFAULT_DOCKING_PANE_STYLE. Weitere Informationen finden Sie im Abschnitt "Hinweise" der Methode " [cbasepane:: kreateex](../../mfc/reference/cbasepane-class.md#createex) ".

### <a name="return-value"></a>Rückgabewert

TRUE, wenn diese Methode erfolgreich ist. andernfalls false.

### <a name="remarks"></a>Hinweise

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie die `Create` -Methode in `CPaneDialog` der-Klasse verwendet wird. Dieses Beispiel ist Teil des Beispiels " [Set Pane size](../../overview/visual-cpp-samples.md)".

[!code-cpp[NVC_MFC_SetPaneSize#2](../../mfc/reference/codesnippet/cpp/cpanedialog-class_1.h)]
[!code-cpp[NVC_MFC_SetPaneSize#3](../../mfc/reference/codesnippet/cpp/cpanedialog-class_2.cpp)]

##  <a name="handleinitdialog"></a>Cpanedialog:: handleinitdialog

Verarbeitet die [WM_INITDIALOG](/windows/win32/dlgbox/wm-initdialog) -Meldung.

```
afx_msg LRESULT HandleInitDialog(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>Parameter

*wParam*<br/>
in Handle für das Steuerelement, das den Standardtastatur Fokus erhalten soll.

*lParam*<br/>
in Gibt zusätzliche Initialisierungs Daten an.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn diese Methode erfolgreich ist. andernfalls false. Außerdem legt true den Tastaturfokus auf das Steuerelement fest, das durch den *wParam* -Parameter angegeben wird. FALSE verhindert, dass der Standardtastatur Fokus festgelegt wird.

### <a name="remarks"></a>Hinweise

Das Framework verwendet diese Methode, um Steuerelemente und das Aussehen eines Dialog Felds zu initialisieren. Das Framework ruft diese Methode auf, bevor das Dialogfeld angezeigt wird.

##  <a name="setoccdialoginfo"></a>Cpanedialog:: ""

Gibt die Vorlage für ein Dialogfeld an, das ein OLE-Steuerelement Container ist.

```
virtual BOOL SetOccDialogInfo(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```

### <a name="parameters"></a>Parameter

*pOccDialogInfo*<br/>
in Zeiger auf eine Dialogfeld Vorlage, die zum Erstellen des Dialogfeld Objekts verwendet wird. Der Wert dieses Parameters wird anschließend an die Methode " [COccManager:: kreatedlgcontrols](../../mfc/reference/coccmanager-class.md#createdlgcontrols) " übergeben.

### <a name="return-value"></a>Rückgabewert

Immer true.

### <a name="remarks"></a>Hinweise

Diese Methode unterstützt die [COccManager](../../mfc/reference/coccmanager-class.md) -Klasse, die OLE-Steuerelemente und ActiveX-Steuerelemente verwaltet. Die _AFX_OCC_DIALOG_INFO-Struktur wird in der afxocc. h-Header Datei definiert.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md)<br/>
[Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles)
