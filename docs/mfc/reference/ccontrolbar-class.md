---
title: CControlBar Class
ms.date: 11/04/2016
f1_keywords:
- CControlBar
- AFXEXT/CControlBar
- AFXEXT/CControlBar::CControlBar
- AFXEXT/CControlBar::CalcDynamicLayout
- AFXEXT/CControlBar::CalcFixedLayout
- AFXEXT/CControlBar::CalcInsideRect
- AFXEXT/CControlBar::DoPaint
- AFXEXT/CControlBar::DrawBorders
- AFXEXT/CControlBar::DrawGripper
- AFXEXT/CControlBar::EnableDocking
- AFXEXT/CControlBar::GetBarStyle
- AFXEXT/CControlBar::GetBorders
- AFXEXT/CControlBar::GetCount
- AFXEXT/CControlBar::GetDockingFrame
- AFXEXT/CControlBar::IsFloating
- AFXEXT/CControlBar::OnUpdateCmdUI
- AFXEXT/CControlBar::SetBarStyle
- AFXEXT/CControlBar::SetBorders
- AFXEXT/CControlBar::SetInPlaceOwner
- AFXEXT/CControlBar::m_bAutoDelete
- AFXEXT/CControlBar::m_pInPlaceOwner
helpviewer_keywords:
- CControlBar [MFC], CControlBar
- CControlBar [MFC], CalcDynamicLayout
- CControlBar [MFC], CalcFixedLayout
- CControlBar [MFC], CalcInsideRect
- CControlBar [MFC], DoPaint
- CControlBar [MFC], DrawBorders
- CControlBar [MFC], DrawGripper
- CControlBar [MFC], EnableDocking
- CControlBar [MFC], GetBarStyle
- CControlBar [MFC], GetBorders
- CControlBar [MFC], GetCount
- CControlBar [MFC], GetDockingFrame
- CControlBar [MFC], IsFloating
- CControlBar [MFC], OnUpdateCmdUI
- CControlBar [MFC], SetBarStyle
- CControlBar [MFC], SetBorders
- CControlBar [MFC], SetInPlaceOwner
- CControlBar [MFC], m_bAutoDelete
- CControlBar [MFC], m_pInPlaceOwner
ms.assetid: 4d668c55-9b42-4838-97ac-cf2b3000b82c
ms.openlocfilehash: e9fba929017edfe547f2cc20105ea4f4bcdc9c33
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50644391"
---
# <a name="ccontrolbar-class"></a>CControlBar Class

Die Basisklasse für die Steuerleistenklassen [CStatusBar](../../mfc/reference/cstatusbar-class.md), [CToolBar](../../mfc/reference/ctoolbar-class.md), [CDialogBar](../../mfc/reference/cdialogbar-class.md), [CReBar](../../mfc/reference/crebar-class.md), und [ COleResizeBar](../../mfc/reference/coleresizebar-class.md).

## <a name="syntax"></a>Syntax

```
class CControlBar : public CWnd
```

## <a name="members"></a>Member

### <a name="protected-constructors"></a>Geschützte Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CControlBar::CControlBar](#ccontrolbar)|Erstellt ein `CControlBar`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CControlBar::CalcDynamicLayout](#calcdynamiclayout)|Gibt die Größe einer dynamischen Steuerleiste als ein [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt.|
|[CControlBar::CalcFixedLayout](#calcfixedlayout)|Gibt die Größe der Steuerleiste als ein [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt.|
|[CControlBar::CalcInsideRect](#calcinsiderect)|Gibt die aktuellen Maße des Steuerleistenbereichs, einschließlich der Rahmen, zurück.|
|[CControlBar::DoPaint](#dopaint)|Rendert die Rahmen und das Ziehelement der Steuerleiste.|
|[CControlBar::DrawBorders](#drawborders)|Rendert die Rahmen der Steuerleiste.|
|[CControlBar::DrawGripper](#drawgripper)|Rendert das Ziehelement der Steuerleiste.|
|[CControlBar:: EnableDocking](#enabledocking)|Ermöglicht das Andocken bzw. eine unverankerte Steuerleiste.|
|[CControlBar::GetBarStyle](#getbarstyle)|Ruft die Formatvorlagen der Steuerleiste ab.|
|[CControlBar::GetBorders](#getborders)|Ruft die Rahmenwerte der Steuerleiste ab.|
|[CControlBar::GetCount](#getcount)|Gibt die Anzahl der nicht-HWND-Elemente in der Steuerleiste zurück.|
|[CControlBar::GetDockingFrame](#getdockingframe)|Gibt einen Zeiger auf den Frame zurück, an den eine Steuerleiste angedockt ist.|
|[CControlBar::IsFloating](#isfloating)|Gibt einen Wert ungleich 0 (null) zurück, wenn die fragliche Steuerleiste unverankert ist.|
|[CControlBar::OnUpdateCmdUI](#onupdatecmdui)|Ruft die Befehlshandler der Benutzeroberfläche ab.|
|[CControlBar::SetBarStyle](#setbarstyle)|Ändert die Formatvorlagen der Steuerleiste.|
|[CControlBar::SetBorders](#setborders)|Legt die Rahmenwerte der Steuerleiste fest.|
|[CControlBar::SetInPlaceOwner](#setinplaceowner)|Ändert den direkten Besitzer einer Steuerleiste.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CControlBar::m_bAutoDelete](#m_bautodelete)|Wenn der Wert ungleich 0 (null) ist, wird das `CControlBar`-Objekt gelöscht, sobald die Windows-Steuerleiste zerstört wird.|
|[CControlBar::m_pInPlaceOwner](#m_pinplaceowner)|Der direkte Besitzer der Steuerleiste.|

## <a name="remarks"></a>Hinweise

Eine Steuerleiste ist ein Fenster, das normalerweise am linken oder rechten Rand eines Rahmenfensters ausgerichtet wird. Sie kann untergeordnete Elemente enthalten, die entweder HWND-basierte Steuerelemente, Windows, die generiert und auf Windows-Nachrichten reagieren, oder nicht-HWND-basierte-Elemente, die sind keine Fenster und mithilfe von Anwendungs- oder Frameworkcode verwaltet werden. Listenfelder und Bearbeitungssteuerelemente sind Beispiele für HWND-basierte Steuerelemente. Statusleistenbereiche und Bitmapschaltflächen sind Beispiele für nicht-HWND-basierte Steuerelemente.

Bei Steuerleistenfenstern handelt es sich normalerweise um untergeordnete Fenster eines übergeordneten Rahmenfensters, und es sind normalerweise nebengeordnete Elemente der Clientansicht oder des MDI-Clients des Rahmenfensters. Ein `CControlBar`-Objekt verwendet zum eigenen Positionieren Informationen über das Clientrechteck des übergeordneten Fensters. Dem übergeordneten Fenster wird dann die Menge des Speicherplatzes im Clientbereich des übergeordneten Fensters mitgeteilt, die unzugeordnet bleibt.

Weitere Informationen zu `CControlBar` finden Sie unter:

- [Steuerleisten](../../mfc/control-bars.md)

- [Technischer Hinweis 31: Steuerleisten](../../mfc/tn031-control-bars.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CControlBar`

## <a name="requirements"></a>Anforderungen

**Header:** afxext.h

##  <a name="calcdynamiclayout"></a>  CControlBar::CalcDynamicLayout

Das Framework ruft diese Member-Funktion, um die Abmessungen des eine dynamische Werkzeugleiste zu berechnen.

```
virtual CSize CalcDynamicLayout(
    int nLength,
    DWORD nMode);
```

### <a name="parameters"></a>Parameter

*nLength*<br/>
Die angeforderte Dimension der Steuerleiste, horizontal oder vertikal, je nachdem *DwMode*.

*nMode*<br/>
Die folgenden vordefinierten Flags werden verwendet, um zu bestimmen, die Höhe und Breite der dynamischen Steuerleiste. Verwenden Sie das bitweise OR (&#124;) Operator, um die Flags kombinieren.

|Layout-Modus-flags|Bedeutung|
|-----------------------|-------------------|
|LM_STRETCH|Gibt an, ob die Steuerleiste, auf die Größe des Rahmens gestreckt wird. Festlegen Sie, wenn die Leiste keine andockleiste (nicht verfügbar für Andocken) wird. Nicht festgelegt, wenn die Leiste angedockt oder unverankert ist (zum Andocken verfügbar). Wenn festgelegt, LM_STRETCH ignoriert *nLength* und Dimensionen basierend auf dem LM_HORZ Status zurückgegeben. LM_STRETCH funktioniert ähnlich wie die *bStretch* in verwendeten Parameter [CalcFixedLayout](#calcfixedlayout); finden Sie unter dieser Memberfunktion Weitere Informationen über die Beziehung zwischen Strecken und Ausrichtung.|
|LM_HORZ|Gibt an, dass die Leiste horizontal oder vertikal ausgerichtet ist. Festlegen Sie, wenn die Leiste horizontal ausgerichtet ist, und wenn sie vertikal ausgerichtet ist, ist es nicht festgelegt. LM_HORZ funktioniert ähnlich wie die *bHorz* in verwendeten Parameter [CalcFixedLayout](#calcfixedlayout); finden Sie unter dieser Memberfunktion Weitere Informationen über die Beziehung zwischen Strecken und Ausrichtung.|
|LM_MRUWIDTH|Dynamische Breite zuletzt verwendete. Ignoriert *nLength* Parameter und verwendet die gespeicherte zuletzt verwendete Breite.|
|LM_HORZDOCK|Horizontal angedockt Dimensionen. Ignoriert *nLength* Parameter und gibt die dynamische Größe mit der größten Breite.|
|LM_VERTDOCK|Vertikale angedockt Dimensionen. Ignoriert *nLength* Parameter und gibt die dynamische Größe durch die Höhe des größten.|
|LM_LENGTHY|Wenn *nLength* gibt die Höhe (Y-Richtung) anstelle von Width.|
|LM_COMMIT|Setzt LM_MRUWIDTH auf aktuelle Breite der unverankerte Steuerleiste zurück.|

### <a name="return-value"></a>Rückgabewert

Die Steuerleiste Größe, in Pixel, der eine [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Memberfunktion, um Ihre eigenen dynamischen Layout in Klassen bieten Sie eine von Ableitung `CControlBar`. MFC-Klassen abgeleitet `CControlBar`, z. B. [CToolbar](../../mfc/reference/ctoolbar-class.md), überschreiben Sie diese Memberfunktion auf, und ihre eigene Implementierung bereitstellen.

##  <a name="calcfixedlayout"></a>  CControlBar::CalcFixedLayout

Rufen Sie diese Memberfunktion, um die horizontale Größe des eine Steuerleiste zu berechnen.

```
virtual CSize CalcFixedLayout(
    BOOL bStretch,
    BOOL bHorz);
```

### <a name="parameters"></a>Parameter

*bStretch*<br/>
Gibt an, ob die Leiste, auf die Größe des Rahmens gestreckt wird. Die *bStretch* Parameter ungleich NULL ist, wenn die Leiste keine andockleiste (nicht verfügbar für Andocken) und 0, ist wenn es angedockt oder unverankert ist (zum Andocken verfügbar).

*bHorz*<br/>
Gibt an, dass die Leiste horizontal oder vertikal ausgerichtet ist. Die *bHorz* Parameter ungleich NULL ist, wenn die Leiste horizontal ausgerichtet und 0, ist wenn es vertikal ausgerichtet ist.

### <a name="return-value"></a>Rückgabewert

Die Steuerleiste Größe, in Pixel, der eine `CSize` Objekt.

### <a name="remarks"></a>Hinweise

Steuerleisten, wie beispielsweise Symbolleisten können horizontal Strecken oder vertikal, berücksichtigen die Schaltflächen enthalten, in der Steuerleiste.

Wenn *bStretch* ist "true", dehnen Sie die Dimension auf die Ausrichtung von bereitgestellten *bHorz*. Das heißt, wenn *bHorz* ist "false", die Steuerleiste vertikal gestreckt wird. Wenn *bStretch* false festgelegt ist, tritt keine Stretch. Die folgende Tabelle zeigt die möglichen Permutationen und die resultierende Steuerleiste Stile der *bStretch* und *bHorz*.

|bStretch|bHorz|Strecken|Ausrichtung|Andocken "/" Not Andocken|
|--------------|-----------|----------------|-----------------|--------------------------|
|true|true|Horizontale Strecken|Horizontal ausgerichtet.|Nicht Andocken|
|true|false|Vertikale Strecken|Vertikal ausgerichtet.|Nicht Andocken|
|false|true|Keine größenanpassung verfügbar|Horizontal ausgerichtet.|Andocken|
|false|false|Keine größenanpassung verfügbar|Vertikal ausgerichtet.|Andocken|

##  <a name="calcinsiderect"></a>  CControlBar::CalcInsideRect

Das Framework ruft diese Funktion zum Berechnen der Clientbereich der Steuerleiste.

```
virtual void CalcInsideRect(
    CRect& rect,
    BOOL bHorz) const;
```

### <a name="parameters"></a>Parameter

*Rect*<br/>
Enthält die aktuellen Maße der Steuerleiste. einschließlich der Rahmen an.

*bHorz*<br/>
Gibt an, dass die Leiste horizontal oder vertikal ausgerichtet ist. Die *bHorz* Parameter ungleich NULL ist, wenn die Leiste horizontal ausgerichtet und 0, ist wenn es vertikal ausgerichtet ist.

### <a name="remarks"></a>Hinweise

Diese Funktion wird aufgerufen, bevor die Steuerleiste gezeichnet wird.

Überschreiben Sie diese Funktion, um das Rendering der Rahmen und Ziehpunktleiste der Steuerleiste anpassen.

##  <a name="ccontrolbar"></a>  CControlBar::CControlBar

Erstellt ein `CControlBar`-Objekt.

```
CControlBar();
```

##  <a name="dopaint"></a>  CControlBar::DoPaint

Wird aufgerufen, durch das Framework zum Rendern der Rahmen und Ziehpunktleiste der Steuerleiste.

```
virtual void DoPaint(CDC* pDC);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Verweist auf den Gerätekontext für das Rendern der Rahmen und das ziehelement der Steuerleiste verwendet werden.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion, um das zeichenverhalten der Steuerleiste anpassen.

Eine weitere Anpassungsmethode ist, überschreiben die `DrawBorders` und `DrawGripper` Funktionen und Hinzufügen von benutzerdefinierten Zeichnungscode für den Rahmen und das ziehelement. Da diese Methoden, die standardmäßig aufgerufen werden `DoPaint` -Methode, die eine Überschreibung der `DoPaint` ist nicht erforderlich.

##  <a name="drawborders"></a>  CControlBar::DrawBorders

Wird aufgerufen, durch das Framework zum Rendern der Rahmen der Steuerleiste.

```
virtual void DrawBorders(
    CDC* pDC,
    CRect& rect);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Verweist auf den Gerätekontext für das Rendern der Rahmen der Steuerleiste verwendet werden.

*Rect*<br/>
Ein `CRect` -Objekt, das die Abmessungen der Steuerleiste enthält.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion, um die Darstellung der Steuerelementrahmen Leiste anzupassen.

##  <a name="drawgripper"></a>  CControlBar::DrawGripper

Wird aufgerufen, durch das Framework das ziehelement der Steuerleiste zu rendern.

```
virtual void DrawGripper(
    CDC* pDC,
    const CRect& rect);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Verweist auf den Gerätekontext für das Rendern des ziehelements Leiste Steuerelement verwendet werden.

*Rect*<br/>
Ein `CRect` -Objekt, das die Abmessungen des ziehelements Leiste Steuerelement enthält.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion, um die Darstellung des Steuerelements Leiste ziehelements anpassen.

##  <a name="enabledocking"></a>  CControlBar:: EnableDocking

Mit dieser Funktion können Sie ermöglichen eine Steuerleiste angedockt werden.

```
void EnableDocking(DWORD dwDockStyle);
```

### <a name="parameters"></a>Parameter

*dwDockStyle*<br/>
Gibt an, ob die Steuerleiste unterstützt Andocken und den Seiten des übergeordneten Fensters auf die Steuerleiste angedockt werden kann, wenn unterstützt. Hierbei kann es sich um eine oder mehrere der folgenden sein:

- CBRS_ALIGN_TOP ermöglicht das Andocken am oberen Rand des Clientbereichs.

- CBRS_ALIGN_BOTTOM ermöglicht das Andocken am unteren Rand des Clientbereichs.

- CBRS_ALIGN_LEFT können auf der linken Seite des Clientbereichs andocken.

- CBRS_ALIGN_RIGHT können auf der rechten Seite des Clientbereichs andocken.

- CBRS_ALIGN_ANY ermöglicht das Andocken an jede Seite des Clientbereichs.

- CBRS_FLOAT_MULTI können mehrere Schiebeleisten-Steuerelemente, die in einer einzelnen Minirahmenfenster abgedockt werden.

Wenn der Wert 0 (d. h. keine Flags angibt), die Steuerleiste wird nicht angedockt.

### <a name="remarks"></a>Hinweise

Die Seiten mit dem angegebenen müssen einer der Seiten für die in der Ziel-Rahmenfenster Andocken aktiviert entsprechen, oder die Steuerleiste nicht zu diesem Frame Fenster angedockt werden.

##  <a name="getbarstyle"></a>  CControlBar::GetBarStyle

Mit dieser Funktion können Sie ermitteln, welche **CBRS_** (Steuerelementstile Leiste)-Einstellungen für die Steuerleiste derzeit festgelegt werden.

```
DWORD GetBarStyle();
```

### <a name="return-value"></a>Rückgabewert

Die aktuelle **CBRS_** (Steuerelementstile Leiste)-Einstellungen für die Steuerleiste. Finden Sie unter [CControlBar::SetBarStyle](#setbarstyle) für die vollständige Liste der verfügbaren Formate.

### <a name="remarks"></a>Hinweise

Verarbeitet keine **WS_** (Fensterstil) Stile.

##  <a name="getborders"></a>  CControlBar::GetBorders

Gibt die aktuellen rahmenwerte für die Steuerleiste zurück.

```
CRect GetBorders() const;
```

### <a name="return-value"></a>Rückgabewert

Ein `CRect` Objekt, das die aktuelle Breite (in Pixeln) der einzelnen Seiten des Steuerelementobjekts Leiste enthält. Z. B. den Wert von der *linken* Member, der [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt, das ist die Breite des linken Rahmens.

##  <a name="getcount"></a>  CControlBar::GetCount

Gibt die Anzahl der nicht-HWND-Elemente auf der `CControlBar` Objekt.

```
int GetCount() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der nicht-HWND-Elemente auf der `CControlBar` Objekt. Diese Funktion gibt 0 für eine [CDialogBar](../../mfc/reference/cdialogbar-class.md) Objekt.

### <a name="remarks"></a>Hinweise

Der Typ des Elements hängt vom abgeleiteten Objekt: Bereiche für [CStatusBar](../../mfc/reference/cstatusbar-class.md) -Objekte, und die Schaltflächen und die Trennzeichen für die [CToolBar](../../mfc/reference/ctoolbar-class.md) Objekte.

##  <a name="getdockingframe"></a>  CControlBar::GetDockingFrame

Rufen Sie diese Memberfunktion, um einen Zeiger auf das aktuelle Rahmenfenster zu erhalten, Ihre Steuerleiste angedockt ist.

```
CFrameWnd* GetDockingFrame() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein Rahmenfenster, wenn erfolgreich; andernfalls NULL.

Wenn die Steuerleiste nicht angedockt ist ein Rahmenfenster (d.h., wenn die Steuerleiste unverankert ist), die diese Funktion gibt einen Zeiger zum übergeordneten [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md).

### <a name="remarks"></a>Hinweise

Weitere Informationen zu andockbaren Steuerleisten, finden Sie unter [CControlBar:: EnableDocking](#enabledocking) und [CFrameWnd:: DockControlBar](../../mfc/reference/cframewnd-class.md#dockcontrolbar).

##  <a name="isfloating"></a>  CControlBar::IsFloating

Rufen Sie diese Memberfunktion, um festzustellen, ob die Steuerleiste frei verschiebbar oder angedockt ist.

```
BOOL IsFloating() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Steuerleiste unverankert ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Ändern Sie den Status einer Steuerleiste von floating angedockt, rufen Sie [CFrameWnd::FloatControlBar](../../mfc/reference/cframewnd-class.md#floatcontrolbar).

##  <a name="m_bautodelete"></a>  CControlBar::m_bAutoDelete

Wenn der Wert ungleich 0 (null) ist, wird das `CControlBar`-Objekt gelöscht, sobald die Windows-Steuerleiste zerstört wird.

```
BOOL m_bAutoDelete;
```

### <a name="remarks"></a>Hinweise

*M_bAutoDelete* ist eine öffentliche Variable des Typs "bool".

Eine Steuerleiste-Objekt ist in der Regel in einem Rahmenfenster Objekt eingebettet. In diesem Fall *M_bAutoDelete* ist 0, da das eingebettete Steuerleiste-Objekt zerstört wird, wenn das Rahmenfenster zerstört wird.

Legen Sie die Variable einen Wert ungleich NULL, wenn Sie Zuordnen einer `CControlBar` Objekt auf dem Heap, und Sie nicht planen, rufen Sie **löschen**.

##  <a name="m_pinplaceowner"></a>  CControlBar::m_pInPlaceOwner

Der direkte Besitzer der Steuerleiste.

```
CWnd* m_pInPlaceOwner;
```

##  <a name="onupdatecmdui"></a>  CControlBar::OnUpdateCmdUI

Diese Memberfunktion wird durch das Framework beim Aktualisieren des Status von der Symbolleiste oder der Statusleiste aufgerufen.

```
virtual void OnUpdateCmdUI(
    CFrameWnd* pTarget,
    BOOL bDisableIfNoHndler) = 0;
```

### <a name="parameters"></a>Parameter

*pTarget*<br/>
Zeigt an das Hauptrahmenfenster der Anwendung. This-Zeiger wird für Update Weiterleiten von Nachrichten verwendet.

*bDisableIfNoHndler*<br/>
Flag, die angibt, ob ein Steuerelement, das keine updatehandler wurde automatisch als deaktiviert angezeigt werden soll.

### <a name="remarks"></a>Hinweise

Um eine einzelne Schaltfläche oder einen Bereich zu aktualisieren, verwenden Sie die ON_UPDATE_COMMAND_UI-Makro in der meldungszuordnung, um einen updatehandler entsprechend festzulegen. Finden Sie unter [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui) für Weitere Informationen zum Verwenden dieses Makro.

`OnUpdateCmdUI` wird von Framework aufgerufen, wenn die Anwendung im Leerlauf befindet. Das Rahmenfenster aktualisiert werden, muss mindestens indirekt eines untergeordneten Fensters, Rand eines Rahmenfensters für sichtbar sein. `OnUpdateCmdUI` ist ein fortschrittlicher überschreibbar.

##  <a name="setbarstyle"></a>  CControlBar::SetBarStyle

Mit dieser Funktion können Sie die gewünschte festgelegt **CBRS_** Stile für die Steuerleiste.

```
void SetBarStyle(DWORD dwStyle);
```

### <a name="parameters"></a>Parameter

*dwStyle*<br/>
Die gewünschte Stile für die Steuerleiste. Hierbei kann es sich um eine oder mehrere der folgenden sein:

- CBRS_ALIGN_TOP ermöglicht die Steuerleiste am oberen Rand der Clientbereich eines Rahmenfensters angedockt werden.

- CBRS_ALIGN_BOTTOM ermöglicht die Steuerleiste am unteren Rand der Clientbereich eines Rahmenfensters angedockt werden.

- CBRS_ALIGN_LEFT können Steuerleiste an der linken Seite des Clientbereichs des ein Framefenster angedockt werden.

- CBRS_ALIGN_RIGHT ermöglicht es der Symbolleiste auf die rechte Seite des Clientbereichs eines Frame-Fensters angedockt werden.

- CBRS_ALIGN_ANY können Steuerleiste an jede Seite des Clientbereichs des ein Framefenster angedockt werden.

- CBRS_BORDER_TOP bewirkt, dass einen Rahmen gezeichnet werden soll, am oberen Rand des Steuerelements Balken-, wenn es sichtbar wäre.

- CBRS_BORDER_BOTTOM bewirkt, dass einen Rahmen gezeichnet werden soll, auf dem unteren Rand des Steuerelements Balken-, wenn es sichtbar wäre.

- CBRS_BORDER_LEFT bewirkt, dass einen Rahmen gezeichnet werden soll, am linken Rand des Steuerelements Balken-, wenn es sichtbar wäre.

- CBRS_BORDER_RIGHT bewirkt, dass einen Rahmen gezeichnet werden soll, am rechten Rand des Steuerelements Balken-, wenn es sichtbar wäre.

- CBRS_FLOAT_MULTI können mehrere Schiebeleisten-Steuerelemente, die in einer einzelnen Minirahmenfenster abgedockt werden.

- CBRS_TOOLTIPS bewirkt, dass QuickInfos für der Steuerleiste angezeigt werden soll.

- CBRS_FLYBY bewirkt, dass der Meldungstext als QuickInfos gleichzeitig aktualisiert werden.

- CBRS_GRIPPER bewirkt, dass ein ziehelements, ähnlich wie die Bänder in einer `CReBar` Objekt, das für alle gezeichnet werden `CControlBar`-abgeleitete Klasse.

### <a name="remarks"></a>Hinweise

Hat keine Auswirkungen auf die **WS_** (Fensterstil)-Einstellungen.

##  <a name="setborders"></a>  CControlBar::SetBorders

Rufen Sie diese Funktion, um die Größe der Steuerleiste Rahmen festgelegt.

```
void SetBorders(
    int cxLeft = 0,
    int cyTop = 0,
    int cxRight = 0,
    int cyBottom = 0);

void SetBorders(LPCRECT lpRect);
```

### <a name="parameters"></a>Parameter

*cxLeft*<br/>
Die Breite (in Pixel) des linken Rands der Steuerleiste.

*cyTop*<br/>
Die Höhe (in Pixel) des oberen Rands der Steuerleiste.

*cxRight*<br/>
Die Breite (in Pixel) des rechten Rands der Steuerleiste.

*cyBottom*<br/>
Die Höhe (in Pixel) für die untere Rahmenlinie der Steuerleiste.

*lpRect*<br/>
Ein Zeiger auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt, das die aktuelle Breite (in Pixeln) der einzelnen Rahmen der Steuerleistenobjekt enthält.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel legt die oberen und unteren Rahmen der Steuerleiste 5 Pixel und dem linken und rechten Rand auf 2 Pixel fest:

[!code-cpp[NVC_MFCControlLadenDialog#61](../../mfc/codesnippet/cpp/ccontrolbar-class_1.cpp)]

##  <a name="setinplaceowner"></a>  CControlBar::SetInPlaceOwner

Ändert den direkten Besitzer einer Steuerleiste.

```
void SetInPlaceOwner(CWnd* pWnd);
```

### <a name="parameters"></a>Parameter

*Aufnehmen*<br/>
Ein Zeiger auf ein `CWnd` -Objekt.

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[MFC-Muster CTRLBARS](../../visual-cpp-samples.md)<br/>
[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CToolBar-Klasse](../../mfc/reference/ctoolbar-class.md)<br/>
[CDialogBar-Klasse](../../mfc/reference/cdialogbar-class.md)<br/>
[CStatusBar-Klasse](../../mfc/reference/cstatusbar-class.md)<br/>
[CReBar-Klasse](../../mfc/reference/crebar-class.md)
