---
title: CTabView-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: 8f204c545ed9179438a2498c39229d328f821973
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46436350"
---
# <a name="ctabview-class"></a>CTabView-Klasse

Die `CTabView` Klasse vereinfacht die Verwendung der Registerkarten-Steuerelement-Klasse ( [CMFCTabCtrl](../../mfc/reference/ctabview-class.md)) in Anwendungen, die MFCs Dokument-/Ansichtarchitektur verwenden.

## <a name="syntax"></a>Syntax

```
class CTabbedView : public CView
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CTabView::AddView](#addview)|Das Registerkarten-Steuerelement wird eine neue Ansicht hinzugefügt.|
|[CTabView::FindTab](#findtab)|Gibt den Index der angegebenen Ansicht im Registerkarten-Steuerelement zurück.|
|[CTabView::GetActiveView](#getactiveview)|Gibt einen Zeiger auf die derzeit aktive Ansicht|
|[CTabView::GetTabControl](#gettabcontrol)|Gibt einen Verweis auf das Registerkarten-Steuerelement, das der Ansicht zugeordnet.|
|[CTabView::RemoveView](#removeview)|Entfernt die Ansicht aus dem Registerkarten-Steuerelement.|
|[CTabView::SetActiveView](#setactiveview)|Eine Ansicht aktiviert.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CTabView::IsScrollBar](#isscrollbar)|Vom Framework aufgerufen, beim Erstellen einer Registerkartenansicht bestimmt, ob die Registerkartenansicht an eine freigegebene horizontale Bildlaufleiste angezeigt wird.|
|[CTabView::OnActivateView](#onactivateview)|Vom Framework aufgerufen, wenn die Registerkartenansicht aktiv oder inaktiv erfolgt.|

## <a name="remarks"></a>Hinweise

Diese Klasse erleichtert die Ansicht im Registerkartenformat in eine Anwendung für die Dokument-/Ansicht einfügen. `CTabView` ist eine `CView`-abgeleitete Klasse, die ein eingebettetes enthält `CMFCTabCtrl` Objekt. `CTabView` verarbeitet alle Nachrichten, die erforderlich sind, zur Unterstützung der `CMFCTabCtrl` Objekt. Leiten Sie einfach eine Klasse von `CTabView` es in Ihre Anwendung einbinden, und fügen `CView`-abgeleitete Klassen mithilfe der `AddView` Methode. Das Registerkarten-Steuerelement werden diese Sichten als Registerkarten angezeigt werden.

Angenommen, Sie müssen möglicherweise ein Dokument, das auf unterschiedliche Weise dargestellt werden kann: als ein Arbeitsblatt, ein Diagramm, bearbeitbaren Formular, und So weiter. Sie einzelne Ansichten, zeichnen die Daten nach Bedarf erstellen, fügen Sie sie in Ihrem `CTabView`-abgeleitetes Objekt zu bitten, ohne eine zusätzliche Codierung im Registerkartenformat.

[TabbedView-Beispiel: MFC-im Registerkartenformat anzeigen Anwendung](../../visual-cpp-samples.md) veranschaulicht die Verwendung der `CTabView`.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt wie `CTabView` wird im Beispiel TabbedView verwendet.

[!code-cpp[NVC_MFC_TabbedView#1](../../mfc/reference/codesnippet/cpp/ctabview-class_1.h)]

## <a name="requirements"></a>Anforderungen

**Header:** afxTabView.h

##  <a name="addview"></a>  CTabView::AddView

Das Registerkarten-Steuerelement wird eine Ansicht hinzugefügt.

```
int AddView(
    CRuntimeClass* pViewClass,
    const CString& strViewLabel,
    int iIndex=-1,
    CCreateContext* pContext=NULL);
```

### <a name="parameters"></a>Parameter

*pViewClass*<br/>
[in] Ein Zeiger auf eine Laufzeitklasse der Sicht eingefügt werden soll.

*strViewLabel*<br/>
[in] Gibt Text an der Registerkarte.

*iIndex*<br/>
[in] Gibt die nullbasierte Position, an dem die Ansicht eingefügt werden soll. Wenn die Position 1, wird die neue Registerkarte am Ende eingefügt.

*"pContext"*<br/>
[in] Ein Zeiger auf die `CCreateContext` der Ansicht.

### <a name="return-value"></a>Rückgabewert

Ein Index anzeigen, wenn diese Methode erfolgreich ist. Andernfalls -1.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion zum Hinzufügen einer Ansicht an das Registerkarten-Steuerelement, das in einem Frame eingebettet ist.

##  <a name="findtab"></a>  CTabView::FindTab

Gibt den Index der angegebenen Ansicht im Registerkarten-Steuerelement zurück.

```
int FindTab(HWND hWndView) const;
```

### <a name="parameters"></a>Parameter

*hWndView*<br/>
[in] Das Handle der Ansicht.

### <a name="return-value"></a>Rückgabewert

Der Index der Ansicht, wenn es gefunden wird. andernfalls -1.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Funktion, um den Index einer Sicht abgerufen werden, die ein angegebenen Handle.

##  <a name="getactiveview"></a>  CTabView::GetActiveView

Gibt einen Zeiger auf die derzeit aktive Ansicht zurück.

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

Vom Framework aufgerufen, beim Erstellen einer Registerkartenansicht bestimmt, ob die Registerkartenansicht an eine freigegebene horizontale Bildlaufleiste angezeigt wird.

```
virtual BOOL IsScrollBar() const;
```

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die Registerkartenansicht zusammen mit einer freigegebenen Bildlaufleiste erstellt werden soll. Andernfalls "false".

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Methode bei einem *CTabView* Objekt erstellt wird.

Überschreiben der *IsScrollBar* -Methode in eine *CTabView*-abgeleiteten Klasse und gibt WAHR zurück, wenn eine Ansicht zu erstellen, die eine freigegebene horizontale Bildlaufleiste angezeigt werden sollen.

##  <a name="onactivateview"></a>  CTabView::OnActivateView

Vom Framework aufgerufen, wenn die Registerkartenansicht aktiv oder inaktiv erfolgt.

```
virtual void OnActivateView(CView* view);
```

### <a name="parameters"></a>Parameter

*Anzeigen*<br/>
[in] Ein Zeiger auf die Ansicht.

### <a name="remarks"></a>Hinweise

Bei der Standardimplementierung wird keine Aktion ausgeführt. Überschreiben Sie diese Methode in einer `CTabView`-abgeleitete Klasse, um diese Benachrichtigung zu verarbeiten.

##  <a name="removeview"></a>  CTabView::RemoveView

Entfernt die Ansicht aus dem Registerkarten-Steuerelement.

```
BOOL RemoveView(int iTabNum);
```

### <a name="parameters"></a>Parameter

*iTabNum*<br/>
[in] Der Index des zu entfernenden Sicht.

### <a name="return-value"></a>Rückgabewert

Der Index der entfernten Ansicht, wenn diese Methode erfolgreich ist. Andernfalls -1.

### <a name="remarks"></a>Hinweise

##  <a name="setactiveview"></a>  CTabView::SetActiveView

Eine Ansicht aktiviert.

```
BOOL SetActiveView(int iTabNum);
```

### <a name="parameters"></a>Parameter

*iTabNum*<br/>
[in] Der nullbasierte Index der Registerkartenansicht.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die angegebene Ansicht aktiv ist, "false" erstellt wurde, wenn die Ansicht der Indexwert ungültig ist.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [CMFCTabCtrl::SetActiveTab](../../mfc/reference/cmfctabctrl-class.md#setactivetab).

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CMFCTabCtrl](../../mfc/reference/ctabview-class.md)<br/>
[CView-Klasse](../../mfc/reference/cview-class.md)
