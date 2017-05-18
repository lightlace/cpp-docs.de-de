---
title: Klasse CTabView | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTabView
- AFXTABVIEW/CTabView
- AFXTABVIEW/CTabView::AddView
- AFXTABVIEW/CTabView::FindTab
- AFXTABVIEW/CTabView::GetActiveView
- AFXTABVIEW/CTabView::GetTabControl
- AFXTABVIEW/CTabView::RemoveView
- AFXTABVIEW/CTabView::SetActiveView
- AFXTABVIEW/CTabView::IsScrollBar
- AFXTABVIEW/CTabView::OnActivateView
dev_langs:
- C++
helpviewer_keywords:
- CTabView class
ms.assetid: 8e6ecd9d-d28d-432b-8ec8-0446f0204d52
caps.latest.revision: 32
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
ms.openlocfilehash: 20f5745c3784e771d6ec95f7d4dc363142c687f8
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="ctabview-class"></a>CTabView-Klasse
Die `CTabView` -Klasse vereinfacht die Verwendung der Registerkarte Steuerelementklasse ( [CMFCTabCtrl](../../mfc/reference/ctabview-class.md)) in Clientanwendungen, die MFC Dokument-/ Ansichtarchitektur verwenden.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CTabbedView : public CView  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTabView::AddView](#addview)|Das Registerkarten-Steuerelement hinzugefügt eine neue Ansicht.|  
|[CTabView::FindTab](#findtab)|Gibt den Index der angegebenen Ansicht im Registerkarten-Steuerelement zurück.|  
|[CTabView::GetActiveView](#getactiveview)|Gibt einen Zeiger auf die derzeit aktive Ansicht|  
|[CTabView::GetTabControl](#gettabcontrol)|Gibt einen Verweis auf das Registerkarten-Steuerelement, das der Ansicht zugeordnet.|  
|[CTabView::RemoveView](#removeview)|Entfernt die Ansicht über das Registerkarten-Steuerelement.|  
|[CTabView::SetActiveView](#setactiveview)|Eine Ansicht wird aktiviert.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTabView::IsScrollBar](#isscrollbar)|Wird vom Framework aufgerufen, wenn zum Erstellen einer Registerkartenansicht bestimmt, ob die Registerkartenansicht eine freigegebene horizontale Bildlaufleiste angezeigt.|  
|[CTabView::OnActivateView](#onactivateview)|Vom Framework aufgerufen, wenn die Registerkartenansicht aktiv oder inaktiv erfolgt.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse erleichtert die Ansicht im Registerkartenformat in ein Dokument/Ansicht-Anwendung zu versetzen. `CTabView`ist ein `CView`-abgeleitete Klasse enthält eine eingebettete `CMFCTabCtrl` Objekt. `CTabView`verarbeitet alle Nachrichten, die zur Unterstützung der `CMFCTabCtrl` Objekt. Leiten Sie einfach eine Klasse von `CTabView` und schließen Sie es an die Anwendung, und fügen Sie dann `CView`-abgeleitete Klassen mithilfe der `AddView` Methode. Das Registerkarten-Steuerelement wird diesen Ansichten als Registerkarten angezeigt.  
  
 Angenommen, Sie müssen möglicherweise ein Dokument, das auf verschiedene Arten dargestellt werden kann: als eine Kalkulationstabelle, ein Diagramm, ein bearbeitbares Formular usw.. Sie können einzelne Ansichten, zeichnen die Daten nach Bedarf zu erstellen, fügen Sie sie in Ihrer `CTabView`-abgeleitetes Objekt zu bitten, ohne dass eine zusätzliche Codierung im Registerkartenformat.  
  
 [TabbedView-Beispiel: MFC-Viewer im Registerkartenformat](../../visual-cpp-samples.md) veranschaulicht die Verwendung der `CTabView`.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt wie `CTabView` in das TabbedView-Beispiel verwendet wird.  
  
 [!code-cpp[NVC_MFC_TabbedView&#1;](../../mfc/reference/codesnippet/cpp/ctabview-class_1.h)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxTabView.h  
  
##  <a name="addview"></a>CTabView::AddView  
 Das Registerkarten-Steuerelement hinzugefügt eine Ansicht.  
  
```  
int AddView(
    CRuntimeClass* pViewClass,  
    const CString& strViewLabel,  
    int iIndex=-1,  
    CCreateContext* pContext=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pViewClass`  
 Ein Zeiger auf eine Laufzeitklasse der eingefügten Ansicht.  
  
 [in] `strViewLabel`  
 Gibt die Registerkarte Text.  
  
 [in] `iIndex`  
 Gibt die nullbasierte Position, an der die Sicht eingefügt. Wenn die Position&1;, die neue Registerkarte wird am Ende eingefügt ist.  
  
 [in] `pContext`  
 Ein Zeiger auf die `CCreateContext` der Ansicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Index anzeigen, wenn diese Methode erfolgreich ist. Andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um das Registerkarten-Steuerelement eine Ansicht hinzuzufügen, die in einem Frame eingebettet ist.  
  
##  <a name="findtab"></a>CTabView::FindTab  
 Gibt den Index der angegebenen Ansicht im Registerkarten-Steuerelement zurück.  
  
```  
int FindTab(HWND hWndView) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hWndView`  
 Das Handle der Ansicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index der Ansicht, wenn es gefunden wird. andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um den Index einer Sicht abzurufen, die ein angegebenen Handle.  
  
##  <a name="getactiveview"></a>CTabView::GetActiveView  
 Gibt einen Zeiger auf die derzeit aktive Ansicht.  
  
```  
CView* GetActiveView() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gültiger Zeiger auf die aktive Ansicht oder `NULL` , wenn keine aktive Ansicht vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gettabcontrol"></a>CTabView::GetTabControl  
 Gibt einen Verweis auf das Registerkarten-Steuerelement, das der Ansicht zugeordnet.  
  
```  
DECLARE_DYNCREATE CMFCTabCtrl& GetTabControl();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das Registerkarten-Steuerelement, das der Ansicht zugeordnet.  
  
##  <a name="isscrollbar"></a>CTabView::IsScrollBar  
 Wird vom Framework aufgerufen, wenn zum Erstellen einer Registerkartenansicht bestimmt, ob die Registerkartenansicht eine freigegebene horizontale Bildlaufleiste angezeigt.  
  
```  
virtual BOOL IsScrollBar() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Registerkartenansicht zusammen mit einer freigegebenen Bildlaufleiste erstellt werden soll. Andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode bei einem `CTabView` Objekt erstellt wird.  
  
 Überschreiben der `IsScrollBar` -Methode in einer `CTabView`-abgeleiteten Klasse und der Rückgabewert `TRUE` Wenn eine Sicht erstellen, eine freigegebene horizontale Bildlaufleiste angezeigt werden soll.  
  
##  <a name="onactivateview"></a>CTabView::OnActivateView  
 Vom Framework aufgerufen, wenn die Registerkartenansicht aktiv oder inaktiv erfolgt.  
  
```  
virtual void OnActivateView(CView* view);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `view`  
 Ein Zeiger auf die Ansicht.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie diese Methode in einer `CTabView`-abgeleitete Klasse, um diese Benachrichtigung zu verarbeiten.  
  
##  <a name="removeview"></a>CTabView::RemoveView  
 Entfernt die Ansicht über das Registerkarten-Steuerelement.  
  
```  
BOOL RemoveView(int iTabNum);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iTabNum`  
 Der Index des zu entfernenden Sicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index der entfernten Ansicht, wenn diese Methode erfolgreich ist. Andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setactiveview"></a>CTabView::SetActiveView  
 Eine Ansicht wird aktiviert.  
  
```  
BOOL SetActiveView(int iTabNum);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iTabNum`  
 Der nullbasierte Index der Registerkartenansicht.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die angegebene Ansicht aktiv ist, wurde `FALSE` , wenn die Ansicht Index ungültig ist.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [CMFCTabCtrl::SetActiveTab](../../mfc/reference/cmfctabctrl-class.md#setactivetab).  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCTabCtrl](../../mfc/reference/ctabview-class.md)   
 [CView-Klasse](../../mfc/reference/cview-class.md)

