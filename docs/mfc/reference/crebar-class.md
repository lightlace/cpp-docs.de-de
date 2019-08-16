---
title: Krebar-Klasse
ms.date: 11/19/2018
f1_keywords:
- CReBar
- AFXEXT/CReBar
- AFXEXT/CReBar::AddBar
- AFXEXT/CReBar::Create
- AFXEXT/CReBar::GetReBarCtrl
helpviewer_keywords:
- CReBar [MFC], AddBar
- CReBar [MFC], Create
- CReBar [MFC], GetReBarCtrl
ms.assetid: c1ad2720-1d33-4106-8e4e-80aa84f93559
ms.openlocfilehash: 434232e8f99bf914b00379db53d4b4a37d24fe36
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502792"
---
# <a name="crebar-class"></a>Krebar-Klasse

Eine Steuerleiste, die Layout-, Persistenz- und Zustandsinformationen für Grundleisten-Steuerelemente bereitstellt.

## <a name="syntax"></a>Syntax

```
class CReBar : public CControlBar
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CReBar::AddBar](#addbar)|Fügt ein Band zu einer Info Leiste hinzu.|
|[CReBar::Create](#create)|Erstellt das Grund leisten-Steuerelement und fügt es `CReBar` an das-Objekt an.|
|[CReBar::GetReBarCtrl](#getrebarctrl)|Ermöglicht den direkten Zugriff auf das zugrunde liegende allgemeine Steuerelement.|

## <a name="remarks"></a>Hinweise

Ein Grund leisten-Objekt kann eine Vielzahl von untergeordneten Fenstern enthalten, normalerweise andere Steuerelemente, einschließlich Bearbeitungs Feldern, Symbolleisten und Listenfelder. Ein Grund leisten-Objekt kann seine untergeordneten Fenster über einer angegebenen Bitmap anzeigen. Ihre Anwendung kann die Größe der Info Leiste automatisch ändern, oder der Benutzer kann die Größe der Info Leiste manuell ändern, indem er auf die Zieh Punkt Leiste klickt oder diese zieht.

![Beispiel für rebarmenu](../../mfc/reference/media/vc4sc61.gif "Beispiel für rebarmenu")

## <a name="rebar-control"></a>Grund leisten-Steuerelement

Ein Grund leisten-Objekt verhält sich ähnlich wie ein Toolbar-Objekt. Eine Grund Leiste verwendet den Click-and-Drag-Mechanismus, um die Größe der Bänder zu ändern. Ein Grund leisten-Steuerelement kann ein oder mehrere Bänder enthalten, wobei jedes Band eine beliebige Kombination aus einer Zieh Punkt Leiste, einer Bitmap, einer Text Bezeichnung und einem untergeordneten Fenster enthält. Bänder dürfen jedoch nicht mehr als ein untergeordnetes Fenster enthalten.

`CReBar`verwendet die Klasse " [krebarctrl](../../mfc/reference/crebarctrl-class.md) ", um die Implementierung bereitzustellen. Sie können auf das Grund leisten-Steuerelement über [GetReBarCtrl](#getrebarctrl) zugreifen, um die Anpassungsoptionen des-Steuer Elements zu nutzen. Weitere Informationen zu den Grund leisten-Steuerelementen `CReBarCtrl`finden Sie unter. Weitere Informationen zum Verwenden von Grund leisten-Steuerelementen finden Sie unter [verwenden](../../mfc/using-crebarctrl.md)von "debugstrg".

> [!CAUTION]
>  Das Andocken von Steuerelement Objekten unterstützt die MFC-Steuerleiste nicht. Wenn `CRebar::EnableDocking` aufgerufen wird, wird die Anwendung von der Anwendung bestätigt.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CReBar`

## <a name="requirements"></a>Anforderungen

**Header:** Afxext. h

##  <a name="addbar"></a>Krebar:: addbar

Diese Member-Funktion wird aufgerufen, um der Info Leiste ein Band hinzuzufügen.

```
BOOL AddBar(
    CWnd* pBar,
    LPCTSTR pszText = NULL,
    CBitmap* pbmp = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS | RBBS_FIXEDBMP);

BOOL AddBar(
    CWnd* pBar,
    COLORREF clrFore,
    COLORREF clrBack,
    LPCTSTR pszText = NULL,
    DWORD dwStyle = RBBS_GRIPPERALWAYS);
```

### <a name="parameters"></a>Parameter

*pBar*<br/>
Ein Zeiger auf ein `CWnd` -Objekt, das das untergeordnete Fenster ist, das in die Info Leiste eingefügt werden soll. Das referenzierte Objekt muss über eine WS_CHILD verfügen.

*lpszText*<br/>
Ein Zeiger auf eine Zeichenfolge, die den Text enthält, der auf der Info Leiste angezeigt werden soll. Standardmäßig NULL. Der in *lpszText* enthaltene Text ist nicht Teil des untergeordneten Fensters. Sie befindet sich auf der Grund leisten selbst.

*pbmp*<br/>
Ein Zeiger auf ein `CBitmap` -Objekt, das im Hintergrund der Hintergrund Anzeige angezeigt werden soll. Standardmäßig NULL.

*dwStyle*<br/>
Ein DWORD, das das Format enthält, das auf die Info Leiste angewendet werden soll. Eine komplette `fStyle` Liste der Band Stile finden Sie in der Funktionsbeschreibung in der Win32-Struktur [REBARBANDINFO](/windows/win32/api/commctrl/ns-commctrl-rebarbandinfow) .

*clrFore*<br/>
Ein COLORREF-Wert, der die Vordergrundfarbe der Info Leiste darstellt.

*clrBack*<br/>
Ein COLORREF-Wert, der die Hintergrundfarbe der Info Leiste darstellt.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CReBarCtrl#1](../../mfc/reference/codesnippet/cpp/crebar-class_1.cpp)]

##  <a name="create"></a>"Krebar:: Create"

Rufen Sie diese Member-Funktion auf, um eine Grund Leiste zu erstellen.

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = RBS_BANDBORDERS,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_CLIPSIBLINGS | WS_CLIPCHILDREN | CBRS_TOP,
    UINT nID = AFX_IDW_REBAR);
```

### <a name="parameters"></a>Parameter

*pParentWnd*<br/>
Zeiger auf das `CWnd` -Objekt, dessen Windows-Fenster der Statusleiste übergeordnet ist. Normalerweise das Rahmen Fenster.

*dwCtrlStyle*<br/>
Der Stil des Grund leisten Steuer Elements. Standardmäßig werden in RBS_BANDBORDERS schmale Linien angezeigt, um angrenzende Bänder innerhalb des Grund leisten-Steuer Elements zu trennen. Eine Liste der Stile finden Sie Untergrund leisten- [Steuerelement Stile](/windows/win32/Controls/rebar-control-styles) in der Windows SDK.

*dwStyle*<br/>
Die Fenster Stile des Fenster Fensters.

*nID*<br/>
Die ID des untergeordneten Fensters der Info Leiste.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="example"></a>Beispiel

  Weitere Informationen finden Sie im Beispiel für " [krebar:: addbar](#addbar)".

##  <a name="getrebarctrl"></a>Krebar:: GetReBarCtrl

Diese Member-Funktion ermöglicht den direkten Zugriff auf das zugrunde liegende allgemeine Steuerelement.

```
CReBarCtrl& GetReBarCtrl() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf ein " [krebarctrl](../../mfc/reference/crebarctrl-class.md) "-Objekt.

### <a name="remarks"></a>Hinweise

Mit dieser Member-Funktion können Sie die Funktionalität des allgemeinen Windows-Steuer Elements für die Grund Leiste beim Anpassen der Info Leiste nutzen. Wenn Sie `GetReBarCtrl`den Befehl verwenden, wird ein Verweis Objekt an `CReBarCtrl` das-Objekt zurückgegeben, sodass Sie beide Member-Funktionen verwenden können.

Weitere Informationen zum Anpassen der `CReBarCtrl` Info Leiste mithilfe von finden Sie unter [verwenden](../../mfc/using-crebarctrl.md)von "debugstrg".

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CReBarCtrl#2](../../mfc/reference/codesnippet/cpp/crebar-class_2.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel-MFCIE](../../overview/visual-cpp-samples.md)<br/>
[CControlBar-Klasse](../../mfc/reference/ccontrolbar-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
