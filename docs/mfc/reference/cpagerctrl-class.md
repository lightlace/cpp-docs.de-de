---
title: CPagerCtrl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPagerCtrl
- AFXCMN/CPagerCtrl
- AFXCMN/CPagerCtrl::CPagerCtrl
- AFXCMN/CPagerCtrl::Create
- AFXCMN/CPagerCtrl::CreateEx
- AFXCMN/CPagerCtrl::ForwardMouse
- AFXCMN/CPagerCtrl::GetBkColor
- AFXCMN/CPagerCtrl::GetBorder
- AFXCMN/CPagerCtrl::GetButtonSize
- AFXCMN/CPagerCtrl::GetButtonState
- AFXCMN/CPagerCtrl::GetDropTarget
- AFXCMN/CPagerCtrl::GetScrollPos
- AFXCMN/CPagerCtrl::IsButtonDepressed
- AFXCMN/CPagerCtrl::IsButtonGrayed
- AFXCMN/CPagerCtrl::IsButtonHot
- AFXCMN/CPagerCtrl::IsButtonInvisible
- AFXCMN/CPagerCtrl::IsButtonNormal
- AFXCMN/CPagerCtrl::RecalcSize
- AFXCMN/CPagerCtrl::SetBkColor
- AFXCMN/CPagerCtrl::SetBorder
- AFXCMN/CPagerCtrl::SetButtonSize
- AFXCMN/CPagerCtrl::SetChild
- AFXCMN/CPagerCtrl::SetScrollPos
dev_langs:
- C++
helpviewer_keywords:
- CPagerCtrl [MFC], CPagerCtrl
- CPagerCtrl [MFC], Create
- CPagerCtrl [MFC], CreateEx
- CPagerCtrl [MFC], ForwardMouse
- CPagerCtrl [MFC], GetBkColor
- CPagerCtrl [MFC], GetBorder
- CPagerCtrl [MFC], GetButtonSize
- CPagerCtrl [MFC], GetButtonState
- CPagerCtrl [MFC], GetDropTarget
- CPagerCtrl [MFC], GetScrollPos
- CPagerCtrl [MFC], IsButtonDepressed
- CPagerCtrl [MFC], IsButtonGrayed
- CPagerCtrl [MFC], IsButtonHot
- CPagerCtrl [MFC], IsButtonInvisible
- CPagerCtrl [MFC], IsButtonNormal
- CPagerCtrl [MFC], RecalcSize
- CPagerCtrl [MFC], SetBkColor
- CPagerCtrl [MFC], SetBorder
- CPagerCtrl [MFC], SetButtonSize
- CPagerCtrl [MFC], SetChild
- CPagerCtrl [MFC], SetScrollPos
ms.assetid: 65ac58dd-4f5e-4b7e-b15c-e0d435a7e884
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a582d5de7087e433aed839dc2f55db01dd926f22
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46447569"
---
# <a name="cpagerctrl-class"></a>CPagerCtrl-Klasse

Die Klasse `CPagerCtrl` kapselt das Windows-Pagersteuerelement, in dem der Benutzer einen Bildlauf durchführen kann, um ein Fenster innerhalb eines anderen Fensters in den sichtbaren Bereich zu verschieben, sofern es größer ist als das umgebende Fenster.

## <a name="syntax"></a>Syntax

```
class CPagerCtrl : public CWnd
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CPagerCtrl::CPagerCtrl](#cpagerctrl)|Erstellt ein `CPagerCtrl`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CPagerCtrl::Create](#create)|Ein Pager-Steuerelement erstellt, mit der angegebenen Formate und hängt es an der aktuellen `CPagerCtrl` Objekt.|
|[CPagerCtrl::CreateEx](#createex)|Erstellt ein Pagersteuerelement mit angegebenen Erweiterte Stile und hängt es an der aktuellen `CPagerCtrl` Objekt.|
|[CPagerCtrl::ForwardMouse](#forwardmouse)|Aktiviert oder deaktiviert die Weiterleitung [WM_MOUSEMOVE](/windows/desktop/inputdev/wm-mousemove) Nachrichten an das Fenster, das in der aktuellen Pager-Steuerelement enthalten ist.|
|[CPagerCtrl::GetBkColor](#getbkcolor)|Ruft die Hintergrundfarbe des aktuellen Pager-Steuerelements ab.|
|[CPagerCtrl::GetBorder](#getborder)|Ruft die Rahmengröße des aktuellen Pager-Steuerelements ab.|
|[CPagerCtrl::GetButtonSize](#getbuttonsize)|Ruft die Größe der Schaltfläche des aktuellen Pager-Steuerelements ab.|
|[CPagerCtrl::GetButtonState](#getbuttonstate)|Ruft den Zustand der angegebenen Schaltfläche in der aktuellen Pager-Steuerelement.|
|[CPagerCtrl::GetDropTarget](#getdroptarget)|Ruft die [IDropTarget](/windows/desktop/api/oleidl/nn-oleidl-idroptarget) Schnittstelle für das aktuelle Pagersteuerelement.|
|[CPagerCtrl::GetScrollPos](#getscrollpos)|Ruft ab, das die Bildlaufposition des die aktuelle Pager-Steuerelement.|
|[CPagerCtrl::IsButtonDepressed](#isbuttondepressed)|Gibt an, ob die angegebene Schaltfläche aus, der das aktuelle Pagersteuerelement in `pressed` Zustand.|
|[CPagerCtrl::IsButtonGrayed](#isbuttongrayed)|Gibt an, ob die angegebene Schaltfläche aus, der das aktuelle Pagersteuerelement in `grayed` Zustand.|
|[CPagerCtrl::IsButtonHot](#isbuttonhot)|Gibt an, ob die angegebene Schaltfläche aus, der das aktuelle Pagersteuerelement in `hot` Zustand.|
|[CPagerCtrl::IsButtonInvisible](#isbuttoninvisible)|Gibt an, ob die angegebene Schaltfläche aus, der das aktuelle Pagersteuerelement in `invisible` Zustand.|
|[CPagerCtrl::IsButtonNormal](#isbuttonnormal)|Gibt an, ob die angegebene Schaltfläche aus, der das aktuelle Pagersteuerelement in `normal` Zustand.|
|[CPagerCtrl::RecalcSize](#recalcsize)|Bewirkt, dass das aktuelle Pagersteuerelement, um die Größe des Fensters enthaltenen neu zu berechnen.|
|[CPagerCtrl::SetBkColor](#setbkcolor)|Legt die Hintergrundfarbe des aktuellen Pager-Steuerelements fest.|
|[CPagerCtrl::SetBorder](#setborder)|Legt fest, die Rahmengröße des aktuellen Pager-Steuerelements.|
|[CPagerCtrl::SetButtonSize](#setbuttonsize)|Legt die Größe der Schaltfläche des aktuellen Pager-Steuerelements fest.|
|[CPagerCtrl::SetChild](#setchild)|Legt den im Fenster für das aktuelle Pagersteuerelement fest.|
|[CPagerCtrl::SetScrollPos](#setscrollpos)|Legt fest, das die Bildlaufposition des die aktuelle Pager-Steuerelement.|

## <a name="remarks"></a>Hinweise

Ein Pager-Steuerelement ist ein Fenster, das ein anderes Fenster enthält ist linear und größer als der enthaltenden Fensters, und ermöglicht es Ihnen, den im Fenster: Bildlauf. Das Pagersteuerelement zeigt zwei Bildlaufleisten-Schaltflächen, die automatisch aufgehoben, wenn es sich bei der im Fenster ein Bildlauf durchgeführt wird, den am weitesten entfernten Umfang, und andernfalls wieder. Sie können in einem Pagersteuerelement erstellen, die entweder horizontal oder vertikal gescrollt.

Beispielsweise verfügt Ihre Anwendung eine Symbolleiste, die nicht breit genug ist, um sämtliche Elemente anzuzeigen, können Sie die Symbolleiste in einem Pagersteuerelement zuweisen, und Benutzer werden in der Lage, scrollen Sie die Symbolleiste, um Links oder rechts, um alle Elemente zugreifen. Microsoft Internet Explorer Version 4.0 (commctrl.dll Version 4.71) führt das Pagersteuerelement.

Die `CPagerCtrl` abgeleitete Klasse wird die [CWnd](../../mfc/reference/cwnd-class.md) Klasse. Weitere Informationen und eine Abbildung in einem Pagersteuerelement, finden Sie unter [Paginierungssteuerelemente](/windows/desktop/Controls/pager-controls).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CPagerCtrl`

## <a name="requirements"></a>Anforderungen

**Header:** afxcmn.h

##  <a name="cpagerctrl"></a>  CPagerCtrl::CPagerCtrl

Erstellt ein `CPagerCtrl`-Objekt.

```
CPagerCtrl();
```

### <a name="remarks"></a>Hinweise

Verwenden der [CPagerCtrl::Create](#create) oder [CPagerCtrl::CreateEx](#createex) Methode zum Erstellen eines Auslagerungssteuerelements und fügen Sie ihn auf die `CPagerCtrl` Objekt.

##  <a name="create"></a>  CPagerCtrl::Create

Ein Pager-Steuerelement erstellt, mit der angegebenen Formate und hängt es an der aktuellen `CPagerCtrl` Objekt.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*dwStyle*|[in] Eine bitweise Kombination (OR) von [Window-Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles) und [Stile von Listensteuerelementen Pager](/windows/desktop/Controls/pager-control-styles) auf das Steuerelement angewendet werden.|
|*Rect*|[in] Ein Verweis auf eine [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die Position und Größe des Steuerelements in Clientkoordinaten enthält.|
|*pParentWnd*|[in] Ein Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das das übergeordnete Fenster des Steuerelements ist. Dieser Parameter darf nicht NULL sein.|
|*nID*|[in] Die ID des Steuerelements.|

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Um ein Pager-Steuerelement zu erstellen, deklarieren einen `CPagerCtrl` Variable, rufen Sie dann die [CPagerCtrl::Create](#create) oder [CPagerCtrl::CreateEx](#createex) Methode für diese Variable.

### <a name="example"></a>Beispiel

Das folgende Beispiel erstellt ein Pager-Steuerelement, und verwendet dann die [CPagerCtrl::SetChild](#setchild) Methode, die Pager-Steuerelement ein sehr lange Schaltflächen-Steuerelement zugeordnet werden soll. Anschließend wird die [CPagerCtrl::SetButtonSize](#setbuttonsize) Methode, um die Höhe der Pager-Steuerelement und 20 Pixel, festzulegen und die [CPagerCtrl::SetBorder](#setborder) Methode, um die Stärke des Rahmens um 1-Pixel festgelegt.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

##  <a name="createex"></a>  CPagerCtrl::CreateEx

Erstellt ein Pagersteuerelement mit angegebenen Erweiterte Stile und hängt es an der aktuellen `CPagerCtrl` Objekt.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*dwExStyle*|[in] Eine bitweise Kombination von erweiterten Stile, die auf das Steuerelement angewendet werden. Weitere Informationen finden Sie unter den *DwExStyle* Parameter, der die [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Funktion.|
|*dwStyle*|[in] Eine bitweise Kombination (OR) von [Window-Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles) und [Stile von Listensteuerelementen Pager](/windows/desktop/Controls/pager-control-styles) auf das Steuerelement angewendet werden.|
|*Rect*|[in] Ein Verweis auf eine [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die Position und Größe des Steuerelements in Clientkoordinaten enthält.|
|*pParentWnd*|[in] Ein Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das das übergeordnete Fenster des Steuerelements ist. Dieser Parameter darf nicht NULL sein.|
|*nID*|[in] Die ID des Steuerelements.|

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Um ein Pager-Steuerelement zu erstellen, deklarieren einen `CPagerCtrl` Variable, rufen Sie dann die [CPagerCtrl::Create](#create) oder [CPagerCtrl::CreateEx](#createex) Methode für diese Variable.

##  <a name="forwardmouse"></a>  CPagerCtrl::ForwardMouse

Aktiviert oder deaktiviert die Weiterleitung [WM_MOUSEMOVE](/windows/desktop/inputdev/wm-mousemove) Nachrichten an das Fenster, das in der aktuellen Pager-Steuerelement enthalten ist.

```
void ForwardMouse(BOOL bForward);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*bForward*|[in] True, um vorwärts mausmeldungen, oder "false", nicht mausmeldungen weiterleiten.|

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [PGM_FORWARDMOUSE](/windows/desktop/Controls/pgm-forwardmouse) -Nachricht, die im Windows SDK beschrieben wird.

##  <a name="getborder"></a>  CPagerCtrl::GetBorder

Ruft die Rahmengröße des aktuellen Pager-Steuerelements ab.

```
int GetBorder() const;
```

### <a name="return-value"></a>Rückgabewert

Die aktuelle Rahmengröße, gemessen in Pixel.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [PGM_GETBORDER](/windows/desktop/Controls/pgm-getborder) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird die [CPagerCtrl::GetBorder](#getborder) Methode, um die Stärke des Rahmens des Pagersteuerelements abzurufen.

[!code-cpp[NVC_MFC_CSplitButton_s2#5](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_2.cpp)]

##  <a name="getbkcolor"></a>  CPagerCtrl::GetBkColor

Ruft die Hintergrundfarbe des aktuellen Pager-Steuerelements ab.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Rückgabewert

Ein [COLORREF](/windows/desktop/gdi/colorref) Wert, der die aktuelle Hintergrundfarbe des Pager-Steuerelement enthält.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [PGM_GETBKCOLOR](/windows/desktop/Controls/pgm-getbkcolor) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird die [CPagerCtrl::SetBkColor](#setbkcolor) Methode, um die Hintergrundfarbe der Pager-Steuerelement sich in Rot, festzulegen und die [CPagerCtrl::GetBkColor](#getbkcolor) Methode, um sicherzustellen, dass die Änderung vorgenommen wurde.

[!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]

##  <a name="getbuttonsize"></a>  CPagerCtrl::GetButtonSize

Ruft die Größe der Schaltfläche des aktuellen Pager-Steuerelements ab.

```
int GetButtonSize() const;
```

### <a name="return-value"></a>Rückgabewert

Die aktuelle Schaltflächengröße, gemessen in Pixel.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [PGM_GETBUTTONSIZE](/windows/desktop/Controls/pgm-getbuttonsize) -Nachricht, die im Windows SDK beschrieben wird.

Wenn das Pagersteuerelement styl PGS_HORZ verfügt, wird die Größe der Schaltfläche bestimmt die Breite der Pagerschaltflächen, und wenn das Pagersteuerelement styl PGS_VERT verfügt, wird die Größe der Schaltfläche bestimmt die Höhe der Pagerschaltflächen. Weitere Informationen finden Sie unter [Stile von Listensteuerelementen Pager](/windows/desktop/Controls/pager-control-styles).

##  <a name="getbuttonstate"></a>  CPagerCtrl::GetButtonState

Ruft den Status der die angegebene Bildlaufschaltfläche in das aktuelle Pagersteuerelement ab.

```
DWORD GetButtonState(int iButton) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*iButton*|[in] Gibt die Schaltfläche für die der Status abgerufen wird. Wenn das Format des Steuerelements Pager PGS_HORZ ist, geben Sie PGB_TOPORLEFT für die linke Maustaste und PGB_BOTTOMORRIGHT, für die Rechte Taste. Wenn das Steuerelement Pagerformat PGS_VERT ist, geben Sie PGB_TOPORLEFT für die oberste Schaltfläche und PGB_BOTTOMORRIGHT, für die Schaltfläche unten. Weitere Informationen finden Sie unter [Stile von Listensteuerelementen Pager](/windows/desktop/Controls/pager-control-styles).|

### <a name="return-value"></a>Rückgabewert

Der Zustand der Schaltfläche angegeben wird, indem die *iButton* Parameter. Der Zustand ist einem PGF_INVISIBLE PGF_NORMAL, PGF_GRAYED, PGF_DEPRESSED oder PGF_HOT. Weitere Informationen finden Sie im Abschnitt Rückgabewert der [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) Nachricht.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) -Nachricht, die im Windows SDK beschrieben wird.

##  <a name="getdroptarget"></a>  CPagerCtrl::GetDropTarget

Ruft die [IDropTarget](/windows/desktop/api/oleidl/nn-oleidl-idroptarget) Schnittstelle für das aktuelle Pagersteuerelement.

```
IDropTarget* GetDropTarget() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die `IDropTarget` Schnittstelle für das aktuelle Pagersteuerelement.

### <a name="remarks"></a>Hinweise

`IDropTarget` ist eine der Schnittstellen Sie, um implementieren Drag & Drop-Vorgänge in Ihrer Anwendung zu unterstützen.

Diese Methode sendet die [PGM_GETDROPTARGET](/windows/desktop/Controls/pgm-getdroptarget) -Nachricht, die im Windows SDK beschrieben wird. Der Aufrufer dieser Methode ist verantwortlich für das Aufrufen der `Release` Mitglied der [IDropTarget](/windows/desktop/api/oleidl/nn-oleidl-idroptarget) -Schnittstelle auf, wenn die Schnittstelle nicht mehr benötigt wird.

##  <a name="getscrollpos"></a>  CPagerCtrl::GetScrollPos

Ruft ab, das die Bildlaufposition des die aktuelle Pager-Steuerelement.

```
int GetScrollPos() const;
```

### <a name="return-value"></a>Rückgabewert

Die aktuelle Bildlaufposition, gemessen in Pixel.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [PGM_GETPOS](/windows/desktop/Controls/pgm-getpos) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird die [CPagerCtrl::GetScrollPos](#getscrollpos) Methode zum Abrufen der aktuellen Position des Pager-Steuerelement. Wenn das Pagersteuerelement nicht bereits 0 (null), die am weitesten links stehende Position gescrollt wird im Beispiel wird die [CPagerCtrl::SetScrollPos](#setscrollpos) Methode, um die Bildlaufposition auf 0 (null) festgelegt.

[!code-cpp[NVC_MFC_CSplitButton_s2#7](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_4.cpp)]

##  <a name="isbuttondepressed"></a>  CPagerCtrl::IsButtonDepressed

Gibt an, ob die angegebene Bildlaufschaltfläche der aktuellen Pagersteuerelement im gedrückten Zustand ist.

```
BOOL IsButtonDepressed(int iButton) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*iButton*|[in] Gibt die Schaltfläche für die der Status abgerufen wird. Wenn das Format des Steuerelements Pager PGS_HORZ ist, geben Sie PGB_TOPORLEFT für die linke Maustaste und PGB_BOTTOMORRIGHT, für die Rechte Taste. Wenn das Steuerelement Pagerformat PGS_VERT ist, geben Sie PGB_TOPORLEFT für die oberste Schaltfläche und PGB_BOTTOMORRIGHT, für die Schaltfläche unten. Weitere Informationen finden Sie unter [Stile von Listensteuerelementen Pager](/windows/desktop/Controls/pager-control-styles).|

### <a name="return-value"></a>Rückgabewert

True, wenn die angegebene Schaltfläche im gedrückten Zustand befindet. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) -Nachricht, die im Windows SDK beschrieben wird. Dann wird getestet, ob der Zustand, der zurückgegeben wird PGF_DEPRESSED ist. Weitere Informationen finden Sie im Abschnitt Rückgabewert der [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) Nachricht.

##  <a name="isbuttongrayed"></a>  CPagerCtrl::IsButtonGrayed

Gibt an, ob die angegebene Bildlaufschaltfläche des aktuellen Steuerelements Pager abgeblendet ist.

```
BOOL IsButtonGrayed(int iButton) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*iButton*|[in] Gibt die Schaltfläche für die der Status abgerufen wird. Wenn das Format des Steuerelements Pager PGS_HORZ ist, geben Sie PGB_TOPORLEFT für die linke Maustaste und PGB_BOTTOMORRIGHT, für die Rechte Taste. Wenn das Steuerelement Pagerformat PGS_VERT ist, geben Sie PGB_TOPORLEFT für die oberste Schaltfläche und PGB_BOTTOMORRIGHT, für die Schaltfläche unten. Weitere Informationen finden Sie unter [Stile von Listensteuerelementen Pager](/windows/desktop/Controls/pager-control-styles).|

### <a name="return-value"></a>Rückgabewert

True, wenn die angegebene Schaltfläche abgeblendet ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) -Nachricht, die im Windows SDK beschrieben wird. Dann wird getestet, ob der Zustand, der zurückgegeben wird PGF_GRAYED ist. Weitere Informationen finden Sie im Abschnitt Rückgabewert der [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) Nachricht.

##  <a name="isbuttonhot"></a>  CPagerCtrl::IsButtonHot

Gibt an, ob die angegebene Bildlaufschaltfläche der aktuellen Pagersteuerelement im aktiven Zustand ist.

```
BOOL IsButtonHot(int iButton) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*iButton*|[in] Gibt die Schaltfläche für die der Status abgerufen wird. Wenn das Format des Steuerelements Pager PGS_HORZ ist, geben Sie PGB_TOPORLEFT für die linke Maustaste und PGB_BOTTOMORRIGHT, für die Rechte Taste. Wenn das Steuerelement Pagerformat PGS_VERT ist, geben Sie PGB_TOPORLEFT für die oberste Schaltfläche und PGB_BOTTOMORRIGHT, für die Schaltfläche unten. Weitere Informationen finden Sie unter [Stile von Listensteuerelementen Pager](/windows/desktop/Controls/pager-control-styles).|

### <a name="return-value"></a>Rückgabewert

True, wenn die angegebene Schaltfläche im aktiven Zustand. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) -Nachricht, die im Windows SDK beschrieben wird. Dann wird getestet, ob der Zustand, der zurückgegeben wird PGF_HOT ist. Weitere Informationen finden Sie im Abschnitt Rückgabewert der [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) Nachricht.

##  <a name="isbuttoninvisible"></a>  CPagerCtrl::IsButtonInvisible

Gibt an, ob die angegebene Bildlaufschaltfläche, der das aktuelle Pagersteuerelement nicht sichtbar ist.

```
BOOL IsButtonInvisible(int iButton) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*iButton*|[in] Gibt die Schaltfläche für die der Status abgerufen wird. Wenn das Format des Steuerelements Pager PGS_HORZ ist, geben Sie PGB_TOPORLEFT für die linke Maustaste und PGB_BOTTOMORRIGHT, für die Rechte Taste. Wenn das Steuerelement Pagerformat PGS_VERT ist, geben Sie PGB_TOPORLEFT für die oberste Schaltfläche und PGB_BOTTOMORRIGHT, für die Schaltfläche unten. Weitere Informationen finden Sie unter [Stile von Listensteuerelementen Pager](/windows/desktop/Controls/pager-control-styles).|

### <a name="return-value"></a>Rückgabewert

True, wenn die angegebene Schaltfläche nicht sichtbar ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Windows wird die Bildlaufschaltfläche auf eine bestimmte Richtung unsichtbar bei der im Fenster auf den am weitesten entfernten Umfang Bildlauf durchgeführt wird, da Sie auf die Schaltfläche Weiter mehr von den im Fenster in der Ansicht erscheinen kann nicht.

Diese Methode sendet die [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) -Nachricht, die im Windows SDK beschrieben wird. Dann wird getestet, ob der Zustand, der zurückgegeben wird PGF_INVISIBLE ist. Weitere Informationen finden Sie im Abschnitt Rückgabewert der [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) Nachricht.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird die [CPagerCtrl::IsButtonInvisible](#isbuttoninvisible) Methode, um zu bestimmen, ob das Pagersteuerelement dem linken und rechten scrollschaltflächen sichtbar sind.

[!code-cpp[NVC_MFC_CSplitButton_s2#6](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_5.cpp)]

##  <a name="isbuttonnormal"></a>  CPagerCtrl::IsButtonNormal

Gibt an, ob die angegebene Bildlaufschaltfläche, der das aktuelle Pagersteuerelement im normalen Zustand befindet.

```
BOOL IsButtonNormal(int iButton) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*iButton*|[in] Gibt die Schaltfläche für die der Status abgerufen wird. Wenn das Format des Steuerelements Pager PGS_HORZ ist, geben Sie PGB_TOPORLEFT für die linke Maustaste und PGB_BOTTOMORRIGHT, für die Rechte Taste. Wenn das Steuerelement Pagerformat PGS_VERT ist, geben Sie PGB_TOPORLEFT für die oberste Schaltfläche und PGB_BOTTOMORRIGHT, für die Schaltfläche unten. Weitere Informationen finden Sie unter [Stile von Listensteuerelementen Pager](/windows/desktop/Controls/pager-control-styles).|

### <a name="return-value"></a>Rückgabewert

True, wenn die angegebene Schaltfläche im normalen Zustand befindet. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) -Nachricht, die im Windows SDK beschrieben wird. Dann wird getestet, ob der Zustand, der zurückgegeben wird PGF_NORMAL ist. Weitere Informationen finden Sie im Abschnitt Rückgabewert der [PGM_GETBUTTONSTATE](/windows/desktop/Controls/pgm-getbuttonstate) Nachricht.

##  <a name="recalcsize"></a>  CPagerCtrl::RecalcSize

Bewirkt, dass das aktuelle Pagersteuerelement, um die Größe des Fensters enthaltenen neu zu berechnen.

```
void RecalcSize();
```

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [PGM_RECALCSIZE](/windows/desktop/Controls/pgm-recalcsize) -Nachricht, die im Windows SDK beschrieben wird. Das Pagersteuerelement daher sendet die [PGN_CALCSIZE](/windows/desktop/Controls/pgn-calcsize) Benachrichtigung, um die bildlauffähigen Dimensionen von den im Fenster zu erhalten.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird die [CPagerCtrl::RecalcSize](#recalcsize) Methode, um das aktuelle Pagersteuerelement seine Größe neu berechnen anfordern.

[!code-cpp[NVC_MFC_CSplitButton_s2#3](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_6.cpp)]

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird [Nachricht Reflektion](../../mfc/tn062-message-reflection-for-windows-controls.md) So aktivieren Sie das Pagersteuerelement, seine eigene Größe statt übergeordneten-Dialogfeld zum Durchführen der Berechnung des Steuerelements neu zu berechnen. Im Beispiel wird abgeleitet der `MyPagerCtrl` -Klasse aus der [CPagerCtrl-Klasse](../../mfc/reference/cpagerctrl-class.md), klicken Sie dann zum Zuordnen eine meldungszuordnung verwendet die [PGN_CALCSIZE](/windows/desktop/Controls/pgn-calcsize) Benachrichtigung mit der `OnCalcsize` Benachrichtigungshandler. In diesem Beispiel legt die Benachrichtigungshandler die Breite und Höhe des Steuerelements Pager festen Werten fest.

[!code-cpp[NVC_MFC_CSplitButton_s2#8](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_7.cpp)]

##  <a name="setbkcolor"></a>  CPagerCtrl::SetBkColor

Legt die Hintergrundfarbe des aktuellen Pager-Steuerelements fest.

```
COLORREF SetBkColor(COLORREF clrBk);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*clrBk*|[in] Ein [COLORREF](/windows/desktop/gdi/colorref) -Wert, der der Pager-Steuerelement die neue Hintergrundfarbe enthält.|

### <a name="return-value"></a>Rückgabewert

Ein [COLORREF](/windows/desktop/gdi/colorref) Wert, der die vorherige Hintergrundfarbe der Pager-Steuerelement enthält.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [PGM_SETBKCOLOR](/windows/desktop/Controls/pgm-setbkcolor) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird die [CPagerCtrl::SetBkColor](#setbkcolor) Methode, um die Hintergrundfarbe der Pager-Steuerelement sich in Rot, festzulegen und die [CPagerCtrl::GetBkColor](#getbkcolor) Methode, um sicherzustellen, dass die Änderung vorgenommen wurde.

[!code-cpp[NVC_MFC_CSplitButton_s2#4](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_3.cpp)]

##  <a name="setborder"></a>  CPagerCtrl::SetBorder

Legt fest, die Rahmengröße des aktuellen Pager-Steuerelements.

```
int SetBorder(int iBorder);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*iBorder*|[in] Die neue Rahmengröße, gemessen in Pixel. Wenn die *iBorder* -Parameter ist negativ, die Rahmengröße auf 0 (null) festgelegt ist.|

### <a name="return-value"></a>Rückgabewert

Die vorherige Rahmengröße, gemessen in Pixel.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [PGM_SETBORDER](/windows/desktop/Controls/pgm-setborder) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Beispiel erstellt ein Pager-Steuerelement, und verwendet dann die [CPagerCtrl::SetChild](#setchild) Methode, die Pager-Steuerelement ein sehr lange Schaltflächen-Steuerelement zugeordnet werden soll. Anschließend wird die [CPagerCtrl::SetButtonSize](#setbuttonsize) Methode, um die Höhe der Pager-Steuerelement und 20 Pixel, festzulegen und die [CPagerCtrl::SetBorder](#setborder) Methode, um die Stärke des Rahmens um 1-Pixel festgelegt.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

##  <a name="setbuttonsize"></a>  CPagerCtrl::SetButtonSize

Legt die Größe der Schaltfläche des aktuellen Pager-Steuerelements fest.

```
int SetButtonSize(int iButtonSize);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*iButtonSize*|[in] Die Größe der neuen Schaltfläche, gemessen in Pixel.|

### <a name="return-value"></a>Rückgabewert

Die vorherige Schaltflächengröße, gemessen in Pixel.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [PGM_SETBUTTONSIZE](/windows/desktop/Controls/pgm-setpos) -Nachricht, die im Windows SDK beschrieben wird.

Wenn das Pagersteuerelement styl PGS_HORZ verfügt, wird die Größe der Schaltfläche bestimmt die Breite der Pagerschaltflächen, und wenn das Pagersteuerelement styl PGS_VERT verfügt, wird die Größe der Schaltfläche bestimmt die Höhe der Pagerschaltflächen. Die Standardgröße der Schaltfläche ist drei Viertel der Breite der Schiebeleiste und die minimale Schaltfläche beträgt 12 Pixel. Weitere Informationen finden Sie unter [Stile von Listensteuerelementen Pager](/windows/desktop/Controls/pager-control-styles).

### <a name="example"></a>Beispiel

Das folgende Beispiel erstellt ein Pager-Steuerelement, und verwendet dann die [CPagerCtrl::SetChild](#setchild) Methode, die Pager-Steuerelement ein sehr lange Schaltflächen-Steuerelement zugeordnet werden soll. Anschließend wird die [CPagerCtrl::SetButtonSize](#setbuttonsize) Methode, um die Höhe der Pager-Steuerelement und 20 Pixel, festzulegen und die [CPagerCtrl::SetBorder](#setborder) Methode, um die Stärke des Rahmens um 1-Pixel festgelegt.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

##  <a name="setchild"></a>  CPagerCtrl::SetChild

Legt den im Fenster für das aktuelle Pagersteuerelement fest.

```
void SetChild(HWND hwndChild);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*hwndChild*|[in] Handle für das Fenster enthalten sein soll.|

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [PGM_SETCHILD](/windows/desktop/Controls/pgm-setchild) -Nachricht, die im Windows SDK beschrieben wird.

Diese Methode ändert nicht das übergeordnete Element des Fensters enthalten. Es weist nur ein Fensterhandle der Pager-Steuerelement für den Bildlauf. In den meisten Fällen werden die im Fenster eines untergeordneten Fensters, das Pagersteuerelement.

### <a name="example"></a>Beispiel

Das folgende Beispiel erstellt ein Pager-Steuerelement, und verwendet dann die [CPagerCtrl::SetChild](#setchild) Methode, die Pager-Steuerelement ein sehr lange Schaltflächen-Steuerelement zugeordnet werden soll. Anschließend wird die [CPagerCtrl::SetButtonSize](#setbuttonsize) Methode, um die Höhe der Pager-Steuerelement und 20 Pixel, festzulegen und die [CPagerCtrl::SetBorder](#setborder) Methode, um die Stärke des Rahmens um 1-Pixel festgelegt.

[!code-cpp[NVC_MFC_CSplitButton_s2#1](../../mfc/reference/codesnippet/cpp/cpagerctrl-class_1.cpp)]

##  <a name="setscrollpos"></a>  CPagerCtrl::SetScrollPos

Legt fest, das die Bildlaufposition des die aktuelle Pager-Steuerelement.

```
void SetScrollPos(int iPos);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*iPos*|[in] Der neue Bildlaufposition, gemessen in Pixel.|

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [PGM_SETPOS](/windows/desktop/Controls/pgm-setpos) -Nachricht, die im Windows SDK beschrieben wird.

## <a name="see-also"></a>Siehe auch

[CPagerCtrl-Klasse](../../mfc/reference/cpagerctrl-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Pager-Steuerelemente](/windows/desktop/Controls/pager-controls)



