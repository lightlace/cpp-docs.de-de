---
title: CTabView Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CTabView [MFC], AddView
- CTabView [MFC], FindTab
- CTabView [MFC], GetActiveView
- CTabView [MFC], GetTabControl
- CTabView [MFC], RemoveView
- CTabView [MFC], SetActiveView
- CTabView [MFC], IsScrollBar
- CTabView [MFC], OnActivateView
ms.assetid: 8e6ecd9d-d28d-432b-8ec8-0446f0204d52
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8d64d503c4bad0d452be174064e2932ed100d7de
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121756"
---
# <a name="ctabview-class"></a>CTabView-Klasse
Die `CTabView` Klasse vereinfacht die Verwendung der Registerkarte "-Steuerelementklasse ( [CMFCTabCtrl](../../mfc/reference/ctabview-class.md)) in Anwendungen, die MFC Dokument-/ Ansichtarchitektur verwenden.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CTabbedView : public CView  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTabView::AddView](#addview)|Das Registerkarten-Steuerelement hinzugefügt eine neue Ansicht.|  
|[CTabView::FindTab](#findtab)|Gibt den Index der angegebenen Ansicht im Registerkarten-Steuerelement zurück.|  
|[CTabView::GetActiveView](#getactiveview)|Gibt einen Zeiger auf die derzeit aktive Ansicht|  
|[CTabView::GetTabControl](#gettabcontrol)|Gibt einen Verweis auf das Registerkarten-Steuerelement, das der Ansicht zugeordnet.|  
|[CTabView::RemoveView](#removeview)|Entfernt die Ansicht aus dem Registerkarten-Steuerelement.|  
|[CTabView::SetActiveView](#setactiveview)|Eine Ansicht wird aktiviert.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTabView::IsScrollBar](#isscrollbar)|Vom Framework aufgerufen, beim Erstellen einer Registerkartenansicht bestimmt, ob die Registerkartenansicht eine freigegebene horizontale Bildlaufleiste angezeigt.|  
|[CTabView::OnActivateView](#onactivateview)|Vom Framework aufgerufen, wenn die Registerkartenansicht aktiv oder inaktiv erfolgt.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse vereinfacht die Ansicht im Registerkartenformat in einer Anwendung für die Dokument-/Ansichtarchitektur zu versetzen. `CTabView` ist eine `CView`-abgeleitete Klasse, die ein eingebettetes enthält `CMFCTabCtrl` Objekt. `CTabView` behandelt alle Nachrichten, die zur Unterstützung der `CMFCTabCtrl` Objekt. Leiten Sie eine Klasse aus einfach `CTabView` stecken Sie es in Ihrer Anwendung, und fügen `CView`-abgeleitete Klassen mithilfe der `AddView` Methode. Das Registerkarten-Steuerelement werden diese Sichten als Registerkarten angezeigt werden.  
  
 Angenommen, Sie müssen möglicherweise ein Dokument, das auf verschiedene Weise dargestellt werden kann: als ein Arbeitsblatt, ein Diagramm, ein bearbeitbares Formular usw. Sie können einzelne Ansichten, zeichnen die Daten nach Bedarf erstellen, fügen Sie sie in Ihrem `CTabView`-abgeleitetes Objekt darum zu bitten, ohne eine zusätzliche Codierung im Registerkartenformat.  
  
 [TabbedView-Beispiel: MFC im Registerkartenformat View Application](../../visual-cpp-samples.md) veranschaulicht die Verwendung von `CTabView`.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt wie `CTabView` wird im Beispiel TabbedView verwendet.  
  
 [!code-cpp[NVC_MFC_TabbedView#1](../../mfc/reference/codesnippet/cpp/ctabview-class_1.h)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxTabView.h  
  
##  <a name="addview"></a>  CTabView::AddView  
 Das Registerkarten-Steuerelement hinzugefügt eine Ansicht.  
  
```  
int AddView(
    CRuntimeClass* pViewClass,  
    const CString& strViewLabel,  
    int iIndex=-1,  
    CCreateContext* pContext=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pViewClass*  
 Ein Zeiger auf eine Laufzeitklasse der eingefügten Ansicht.  
  
 [in] *StrViewLabel*  
 Gibt den Registerkartentext ein.  
  
 [in] *iIndex*  
 Gibt die nullbasierte Position, an dem die Sicht eingefügt. Die Position ist-1 wird die neue Registerkarte am Ende eingefügt.  
  
 [in] *"pContext"*  
 Ein Zeiger auf die `CCreateContext` der Ansicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Index anzeigen, wenn diese Methode erfolgreich ausgeführt wird. Andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird eine Ansicht auf das Registerkarten-Steuerelement hinzuzufügen, die in einem Frame eingebettet ist.  
  
##  <a name="findtab"></a>  CTabView::FindTab  
 Gibt den Index der angegebenen Ansicht im Registerkarten-Steuerelement zurück.  
  
```  
int FindTab(HWND hWndView) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] *hWndView*  
 Das Handle der Sicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index der Ansicht, wenn es gefunden wird. andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird zum Abrufen des Index einer Sicht, die ein angegebenen Handle verfügt.  
  
##  <a name="getactiveview"></a>  CTabView::GetActiveView  
 Gibt einen Zeiger auf die derzeit aktive Ansicht an.  
  
```  
CView* GetActiveView() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gültiger Zeiger auf die aktive Ansicht oder NULL, wenn keine aktive Ansicht vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gettabcontrol"></a>  CTabView::GetTabControl  
 Gibt einen Verweis auf das Registerkarten-Steuerelement, das der Ansicht zugeordnet.  
  
```  
DECLARE_DYNCREATE CMFCTabCtrl& GetTabControl();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das Registerkarten-Steuerelement, das der Ansicht zugeordnet.  
  
##  <a name="isscrollbar"></a>  CTabView::IsScrollBar  
 Vom Framework aufgerufen, beim Erstellen einer Registerkartenansicht bestimmt, ob die Registerkartenansicht eine freigegebene horizontale Bildlaufleiste angezeigt.  
  
```  
virtual BOOL IsScrollBar() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 "True", wenn die Registerkartenansicht zusammen mit einer freigegebenen Bildlaufleiste erstellt werden soll. Andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode bei einem *CTabView* Objekt erstellt wird.  
  
 Überschreiben der *IsScrollBar* Methode in einer *CTabView*-abgeleiteten Klasse und gibt "true", wenn Sie eine Sicht erstellen, die einen gemeinsamen horizontalen Bildlaufleiste möchten.  
  
##  <a name="onactivateview"></a>  CTabView::OnActivateView  
 Vom Framework aufgerufen, wenn die Registerkartenansicht aktiv oder inaktiv erfolgt.  
  
```  
virtual void OnActivateView(CView* view);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *anzeigen*  
 Ein Zeiger auf die Ansicht.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie diese Methode in einer `CTabView`-abgeleitete Klasse, um diese Benachrichtigung zu verarbeiten.  
  
##  <a name="removeview"></a>  CTabView::RemoveView  
 Entfernt die Ansicht aus dem Registerkarten-Steuerelement.  
  
```  
BOOL RemoveView(int iTabNum);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *iTabNum*  
 Der Index des zu entfernenden Sicht.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index der entfernten Ansicht, wenn diese Methode erfolgreich ausgeführt wird. Andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setactiveview"></a>  CTabView::SetActiveView  
 Eine Ansicht wird aktiviert.  
  
```  
BOOL SetActiveView(int iTabNum);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *iTabNum*  
 Der nullbasierte Index der Registerkartenansicht.  
  
### <a name="return-value"></a>Rückgabewert  
 "True", wenn die angegebene Ansicht aktiv ist, "false" erfolgte, wenn die Sicht Index ungültig ist.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [CMFCTabCtrl::SetActiveTab](../../mfc/reference/cmfctabctrl-class.md#setactivetab).  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCTabCtrl](../../mfc/reference/ctabview-class.md)   
 [CView-Klasse](../../mfc/reference/cview-class.md)
