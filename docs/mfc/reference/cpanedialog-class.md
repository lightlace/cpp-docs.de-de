---
title: CPaneDialog Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPaneDialog
- AFXPANEDIALOG/CPaneDialog
- AFXPANEDIALOG/CPaneDialog::Create
- AFXPANEDIALOG/CPaneDialog::HandleInitDialog
- AFXPANEDIALOG/CPaneDialog::SetOccDialogInfo
dev_langs:
- C++
helpviewer_keywords:
- CPaneDialog [MFC], Create
- CPaneDialog [MFC], HandleInitDialog
- CPaneDialog [MFC], SetOccDialogInfo
ms.assetid: 48a6bb91-4b92-40f5-8907-b3270b146cf6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3e247d1d824d710cfa9588a01d73e1ca611d77ed
ms.sourcegitcommit: a5a69d2dc3513261e9e28320e4e067aaf40d2ef2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2018
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
|[CPaneDialog::Create](#create)|Erstellt ein andockbares Dialogfeld und fügt es einer `CPaneDialog` Objekt.|  
|`CPaneDialog::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|`CPaneDialog::GetThisClass`|Durch das Framework verwendet wird, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das diesem Klassentyp zugeordnet ist.|  
|[CPaneDialog::HandleInitDialog](#handleinitdialog)|Behandelt die [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) Nachricht. (Definiert `CBasePane::HandleInitDialog`.)|  
|`CPaneDialog::OnEraseBkgnd`|Behandelt die [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055) Nachricht. (Definiert [CWnd::OnEraseBkgnd](../../mfc/reference/cwnd-class.md#onerasebkgnd).)|  
|`CPaneDialog::OnLButtonDblClk`|Behandelt die [WM_LBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms645606) Nachricht. (Definiert [CWnd::OnLButtonDblClk](../../mfc/reference/cwnd-class.md#onlbuttondblclk).)|  
|`CPaneDialog::OnLButtonDown`|Behandelt die [WM_LBUTTONDOWN](http://msdn.microsoft.com/library/windows/desktop/ms645607) Nachricht. (Definiert [CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown).)|  
|`CPaneDialog::OnUpdateCmdUI`|Wird aufgerufen, durch das Framework, um das Dialogfeld zu aktualisieren. (Überschreibt [CDockablePane:: OnUpdateCmdUI](http://msdn.microsoft.com/en-us/5dd61606-1c12-40d4-b024-f3839aa5e2e0).)|  
|`CPaneDialog::OnWindowPosChanging`|Behandelt die [WM_WINDOWPOSCHANGING](http://msdn.microsoft.com/library/windows/desktop/ms632653) Nachricht. (Definiert [CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging).)|  
|[CPaneDialog::SetOccDialogInfo](#setoccdialoginfo)|Gibt die Vorlage für ein Dialogfeld, das ein OLE-Container-Steuerelement ist.|  
  
## <a name="remarks"></a>Hinweise  
 Erstellen einer `CPaneDialog` Objekt in zwei Schritten. Erstellen Sie zunächst das Objekt in Ihrem Code. Rufen Sie zweitens [CPaneDialog::Create](#create). Sie müssen eine gültige Ressource Vorlage Namen oder der Vorlage-ID angeben und übergeben ein Zeigers an das übergeordnete Fenster. Andernfalls schlägt der Erstellungsvorgang. Das Dialogfeld muss das WS_CHILD und WS_VISIBLE-Format angeben. Es wird empfohlen, dass Sie auch die Stile WS_CLIPCHILDREN und WS_CLIPSIBLINGS angeben. Weitere Informationen finden Sie unter [Fensterstile](styles-used-by-mfc.md#window-styles).  
  
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
 Erstellt einen andockbaren (Dialogfeld), und fügt es einer `CPaneDialog` Objekt.  
  
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
 [in] `lpszWindowName`  
 Der Name des Dialogfelds andocken.  
  
 [in] `pParentWnd`  
 Verweist auf das übergeordnete Fenster.  
  
 [in] `bHasGripper`  
 `TRUE` So erstellen im Dialogfeld andockbaren mit einem Titel (Ziehpunkt); andernfalls `FALSE`.  
  
 [in] `lpszTemplateName`  
 Der Name der Ressource Dialogfeldvorlage.  
  
 [in] `nStyle`  
 Der Windows-Stil.  
  
 [in] `nID`  
 Die Steuerelement-ID.  
  
 [in] `nIDTemplate`  
 Ressourcen-ID der Dialogfeldvorlage.  
  
 [in] `dwTabbedStyle`  
 Der Stil des Fensters im Registerkartenformat, die entsteht, wenn der Benutzer ein anderes Steuerelement im Bereich auf die Beschriftung des in diesem Bereich des Steuerelements gezogen wird. Der Standardwert ist `AFX_CBRS_REGULAR_TABS`. Weitere Informationen finden Sie im Abschnitt "Hinweise" der [cbasepane:: CreateEx](../../mfc/reference/cbasepane-class.md#createex) Methode.  
  
 [in] `dwControlBarStyle`  
 Zusätzliche Formatattribute. Der Standardwert ist `AFX_DEFAULT_DOCKING_PANE_STYLE`. Weitere Informationen finden Sie im Abschnitt "Hinweise" der [cbasepane:: CreateEx](../../mfc/reference/cbasepane-class.md#createex) Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn diese Methode erfolgreich ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `Create` Methode in der `CPaneDialog` Klasse. In diesem Beispiel ist Teil der [legen Sie die Größe Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_SetPaneSize#2](../../mfc/reference/codesnippet/cpp/cpanedialog-class_1.h)]  
[!code-cpp[NVC_MFC_SetPaneSize#3](../../mfc/reference/codesnippet/cpp/cpanedialog-class_2.cpp)]  
  
##  <a name="handleinitdialog"></a>  CPaneDialog::HandleInitDialog  
 Behandelt die [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) Nachricht.  
  
```  
afx_msg LRESULT HandleInitDialog(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `wParam`  
 Handle für das Steuerelement, das den Tastaturfokus Standardwert zu erhalten.  
  
 [in] `lParam`  
 Gibt zusätzliche Initialisierungsdaten.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn diese Methode erfolgreich ist; andernfalls `FALSE`. Darüber hinaus `TRUE` legt den Tastaturfokus auf das Steuerelement, das gemäß der `wParam` -Parameter. `FALSE` wird verhindert, dass die Standard-Tastaturfokus festlegen.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verwendet diese Methode initialisiert werden, Steuerelemente und die Darstellung eines Dialogfelds an. Das Framework ruft diese Methode auf, bevor Sie das Dialogfeld angezeigt.  
  
##  <a name="setoccdialoginfo"></a>  CPaneDialog::SetOccDialogInfo  
 Gibt die Vorlage für ein Dialogfeld, das ein OLE-Container-Steuerelement ist.  
  
```  
virtual BOOL SetOccDialogInfo(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pOccDialogInfo`  
 Ein Zeiger auf eine Dialogfeldvorlage, mit denen die Dialogfeldobjekt erstellt wird. Der Wert dieses Parameters wird anschließend in übergeben der [COccManager::CreateDlgControls](../../mfc/reference/coccmanager-class.md#createdlgcontrols) Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 Immer `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode unterstützt die [COccManager](../../mfc/reference/coccmanager-class.md) Klasse, die OLE-Steuerelement-Standorte und ActiveX-Steuerelemente verwaltet. Die _AFX_OCC_DIALOG_INFO-Struktur ist in der Headerdatei afxocc.h definiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md)   
 [Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles)



