---
title: Klasse CPaneDialog | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPaneDialog
dev_langs:
- C++
helpviewer_keywords:
- CPaneDialog::OnLButtonDblClk method
- CPaneDialog::OnLButtonDown method
- CPaneDialog::CreateObject method
- CPaneDialog::OnUpdateCmdUI method
- CPaneDialog constructor
- CPaneDialog::OnEraseBkgnd method
- CPaneDialog class
- CPaneDialog::OnWindowPosChanging method
ms.assetid: 48a6bb91-4b92-40f5-8907-b3270b146cf6
caps.latest.revision: 27
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 85c7e338382758dd809fb770c5ab14860e362da8
ms.lasthandoff: 02/24/2017

---
# <a name="cpanedialog-class"></a>CPaneDialog-Klasse
Die `CPaneDialog` Klasse unterstützt ein nicht modales, andockbares Dialogfeld.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CPaneDialog : public CDockablePane  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CPaneDialog::CPaneDialog`|Standardkonstruktor|  
|`CPaneDialog::~CPaneDialog`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPaneDialog::Create](#create)|Erstellt ein andockbares Dialogfeld und fügt es ein `CPaneDialog` Objekt.|  
|`CPaneDialog::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|`CPaneDialog::GetThisClass`|Vom Framework verwendet werden, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das Klassentyp zugeordnet ist.|  
|[CPaneDialog::HandleInitDialog](#handleinitdialog)|Behandelt das [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) Nachricht. (Definiert `CBasePane::HandleInitDialog`.)|  
|`CPaneDialog::OnEraseBkgnd`|Behandelt das [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055) Nachricht. (Definiert [CWnd::OnEraseBkgnd](../../mfc/reference/cwnd-class.md#onerasebkgnd).)|  
|`CPaneDialog::OnLButtonDblClk`|Behandelt das [WM_LBUTTONDBLCLK](http://msdn.microsoft.com/library/windows/desktop/ms645606) Nachricht. (Definiert [CWnd::OnLButtonDblClk](../../mfc/reference/cwnd-class.md#onlbuttondblclk).)|  
|`CPaneDialog::OnLButtonDown`|Behandelt das [WM_LBUTTONDOWN](http://msdn.microsoft.com/library/windows/desktop/ms645607) Nachricht. (Definiert [CWnd::OnLButtonDown](../../mfc/reference/cwnd-class.md#onlbuttondown).)|  
|`CPaneDialog::OnUpdateCmdUI`|Aufgerufen, um das Dialogfeld zu aktualisieren. (Überschreibt [CDockablePane:: OnUpdateCmdUI](http://msdn.microsoft.com/en-us/5dd61606-1c12-40d4-b024-f3839aa5e2e0).)|  
|`CPaneDialog::OnWindowPosChanging`|Behandelt das [WM_WINDOWPOSCHANGING](http://msdn.microsoft.com/library/windows/desktop/ms632653) Nachricht. (Definiert [CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging).)|  
|[CPaneDialog::SetOccDialogInfo](#setoccdialoginfo)|Gibt die Vorlage für ein Dialogfeld, das ein OLE-Container-Steuerelement ist.|  
  
## <a name="remarks"></a>Hinweise  
 Erstellen einer `CPaneDialog` Objekt in zwei Schritten. Zunächst erstellen Sie das Objekt im Code. Rufen Sie zweitens [CPaneDialog::Create](#create). Sie müssen eine gültige Ressource Vorlage Namen oder der Vorlage-ID angeben und übergeben einen Zeiger auf das übergeordnete Fenster. Andernfalls schlägt der Erstellungsvorgang. Das Dialogfeld muss es sich um das Format WS_CHILD und WS_VISIBLE angeben. Es wird empfohlen, dass Sie auch die Stile WS_CLIPCHILDREN und WS_CLIPSIBLINGS angeben. Weitere Informationen finden Sie unter [Fensterstile](window-styles.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CPaneDialog](../../mfc/reference/cpanedialog-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxpanedialog.h  
  
##  <a name="a-namecreatea--cpanedialogcreate"></a><a name="create"></a>CPaneDialog::Create  
 Erstellt einen andockbaren Dialogfeld und fügt es ein `CPaneDialog` Objekt.  
  
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
 Der Name im Dialogfeld andocken.  
  
 [in] `pParentWnd`  
 Verweist auf das übergeordnete Fenster.  
  
 [in] `bHasGripper`  
 `TRUE`So erstellen Sie im Dialogfeld docking mit Beschriftung (Ziehpunkt); andernfalls `FALSE`.  
  
 [in] `lpszTemplateName`  
 Der Name der Ressource Dialogfeldvorlage.  
  
 [in] `nStyle`  
 Der Windows-Stil.  
  
 [in] `nID`  
 Die Steuerelement-ID.  
  
 [in] `nIDTemplate`  
 Die Ressourcen-ID der Dialogfeldvorlage.  
  
 [in] `dwTabbedStyle`  
 Der Stil des Fensters im Registerkartenformat, die sich ergibt, wenn der Benutzer ein anderes Steuerelement im Bereich auf die Beschriftung des in diesem Bereich des Steuerelements gezogen wird. Der Standardwert ist `AFX_CBRS_REGULAR_TABS`. Weitere Informationen finden Sie im Abschnitt Hinweise der [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) Methode.  
  
 [in] `dwControlBarStyle`  
 Zusätzliche Formatattribute. Der Standardwert ist `AFX_DEFAULT_DOCKING_PANE_STYLE`. Weitere Informationen finden Sie im Abschnitt Hinweise der [CBasePane::CreateEx](../../mfc/reference/cbasepane-class.md#createex) Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn diese Methode erfolgreich ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `Create` -Methode in der `CPaneDialog` Klasse. Dieses Beispiel ist Teil der [Fenstergröße festgelegt Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_SetPaneSize&#2;](../../mfc/reference/codesnippet/cpp/cpanedialog-class_1.h)]  
[!code-cpp[NVC_MFC_SetPaneSize&3;](../../mfc/reference/codesnippet/cpp/cpanedialog-class_2.cpp)]  
  
##  <a name="a-namehandleinitdialoga--cpanedialoghandleinitdialog"></a><a name="handleinitdialog"></a>CPaneDialog::HandleInitDialog  
 Behandelt das [WM_INITDIALOG](http://msdn.microsoft.com/library/windows/desktop/ms645428) Nachricht.  
  
```  
afx_msg LRESULT HandleInitDialog(
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `wParam`  
 Handle für das Steuerelement, das den Standard-Tastaturfokus erhält.  
  
 [in] `lParam`  
 Gibt zusätzliche Daten.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn diese Methode erfolgreich ist; andernfalls `FALSE`. Darüber hinaus `TRUE` legt den Tastaturfokus auf das Steuerelement festgelegt, die von der `wParam` -Parameter. `FALSE` verhindert, dass die Standard-Tastaturfokus festlegen.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework verwendet diese Methode, um Steuerelemente und die Darstellung eines Dialogfelds zu initialisieren. Das Framework ruft diese Methode auf, bevor das Dialogfeld angezeigt.  
  
##  <a name="a-namesetoccdialoginfoa--cpanedialogsetoccdialoginfo"></a><a name="setoccdialoginfo"></a>CPaneDialog::SetOccDialogInfo  
 Gibt die Vorlage für ein Dialogfeld, das ein OLE-Container-Steuerelement ist.  
  
```  
virtual BOOL SetOccDialogInfo(_AFX_OCC_DIALOG_INFO* pOccDialogInfo);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pOccDialogInfo`  
 Ein Zeiger auf eine Dialogfeldvorlage, die verwendet wird, um die Dialogfeldobjekt zu erstellen. Der Wert dieses Parameters wird anschließend in übergeben der [COccManager::CreateDlgControls](../../mfc/reference/coccmanager-class.md#createdlgcontrols) Methode.  
  
### <a name="return-value"></a>Rückgabewert  
 Immer `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode unterstützt die [COccManager](../../mfc/reference/coccmanager-class.md) -Klasse, die OLE-Steuerelement-Websites und ActiveX-Steuerelemente verwaltet. Die _AFX_OCC_DIALOG_INFO-Struktur ist in der Headerdatei afxocc.h definiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md)   
 [Fensterstile](../../mfc/reference/window-styles.md)




