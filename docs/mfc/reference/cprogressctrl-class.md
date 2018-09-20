---
title: CProgressCtrl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CProgressCtrl
- AFXCMN/CProgressCtrl
- AFXCMN/CProgressCtrl::CProgressCtrl
- AFXCMN/CProgressCtrl::Create
- AFXCMN/CProgressCtrl::CreateEx
- AFXCMN/CProgressCtrl::GetBarColor
- AFXCMN/CProgressCtrl::GetBkColor
- AFXCMN/CProgressCtrl::GetPos
- AFXCMN/CProgressCtrl::GetRange
- AFXCMN/CProgressCtrl::GetState
- AFXCMN/CProgressCtrl::GetStep
- AFXCMN/CProgressCtrl::OffsetPos
- AFXCMN/CProgressCtrl::SetBarColor
- AFXCMN/CProgressCtrl::SetBkColor
- AFXCMN/CProgressCtrl::SetMarquee
- AFXCMN/CProgressCtrl::SetPos
- AFXCMN/CProgressCtrl::SetRange
- AFXCMN/CProgressCtrl::SetState
- AFXCMN/CProgressCtrl::SetStep
- AFXCMN/CProgressCtrl::StepIt
dev_langs:
- C++
helpviewer_keywords:
- CProgressCtrl [MFC], CProgressCtrl
- CProgressCtrl [MFC], Create
- CProgressCtrl [MFC], CreateEx
- CProgressCtrl [MFC], GetBarColor
- CProgressCtrl [MFC], GetBkColor
- CProgressCtrl [MFC], GetPos
- CProgressCtrl [MFC], GetRange
- CProgressCtrl [MFC], GetState
- CProgressCtrl [MFC], GetStep
- CProgressCtrl [MFC], OffsetPos
- CProgressCtrl [MFC], SetBarColor
- CProgressCtrl [MFC], SetBkColor
- CProgressCtrl [MFC], SetMarquee
- CProgressCtrl [MFC], SetPos
- CProgressCtrl [MFC], SetRange
- CProgressCtrl [MFC], SetState
- CProgressCtrl [MFC], SetStep
- CProgressCtrl [MFC], StepIt
ms.assetid: 222630f4-1598-4026-8198-51649b1192ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b6a5668a5d9c179f37e7056de6ae17a25c1b4ebe
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393498"
---
# <a name="cprogressctrl-class"></a>CProgressCtrl-Klasse

Stellt die Funktionalität des allgemeinen Windows-Statusanzeige-Steuerelements bereit.

## <a name="syntax"></a>Syntax

```
class CProgressCtrl : public CWnd
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CProgressCtrl::CProgressCtrl](#cprogressctrl)|Erstellt ein `CProgressCtrl`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CProgressCtrl](#create)|Erstellt ein Statusanzeige-Steuerelement, und fügt sie an einer `CProgressCtrl` Objekt.|
|[CProgressCtrl::CreateEx](#createex)|Erstellt ein Fortschritt-Steuerelement mit dem angegebenen erweiterten Stile für Windows und fügt sie an einer `CProgressCtrl` Objekt.|
|[CProgressCtrl::GetBarColor](#getbarcolor)|Ruft die Farbe der Statusleiste Indikator für den aktuellen Statusanzeige-Steuerelements ab.|
|[CProgressCtrl::GetBkColor](#getbkcolor)|Ruft die Hintergrundfarbe des aktuellen Statusanzeige ab.|
|[CProgressCtrl::GetPos](#getpos)|Ruft die aktuelle Position der Statusanzeige ab.|
|[CProgressCtrl::GetRange](#getrange)|Ruft den oberen und unteren Grenzwerten des Bereichs der Statusanzeige-Steuerelements ab.|
|[CProgressCtrl:: GetState](#getstate)|Ruft den Zustand der aktuellen Statusanzeige-Steuerelements ab.|
|[CProgressCtrl::GetStep](#getstep)|Ruft die Schrittweite für die Statusanzeige des aktuellen Statusanzeige-Steuerelements ab.|
|[CProgressCtrl::OffsetPos](#offsetpos)|Verschiebt die aktuelle Position der Statusanzeige-Steuerelement, um eine angegebene Schrittweite und zeichnet die Leiste, um die neue Position zu berücksichtigen.|
|[CProgressCtrl::SetBarColor](#setbarcolor)|Legt die Farbe der Statusleiste Indikator in der aktuellen Statusanzeige-Steuerelements fest.|
|[CProgressCtrl::SetBkColor](#setbkcolor)|Legt die Farbe des Hintergrunds für die Statusanzeige fest.|
|[CProgressCtrl::SetMarquee](#setmarquee)|Aktiviert die Marquee-Modus aktiviert oder deaktiviert für den aktuellen Statusanzeige-Steuerelements.|
|[CProgressCtrl::SetPos](#setpos)|Legt die aktuelle Position für ein Statusanzeige-Steuerelement, und zeichnet die Leiste, um die neue Position zu berücksichtigen.|
|[CProgressCtrl::SetRange](#setrange)|Legt die minimalen und maximalen Bereiche für ein Statusanzeige-Steuerelement, und zeichnet die Leiste, um die neue Bereiche widerspiegeln.|
|[CProgressCtrl::SetState](#setstate)|Legt den Status des aktuellen Statusanzeige-Steuerelements fest.|
|[CProgressCtrl::SetStep](#setstep)|Gibt an, die Schrittweite für ein Statusanzeige-Steuerelement.|
|[CProgressCtrl::StepIt](#stepit)|Verschiebt die aktuelle Position für ein Statusanzeige-Steuerelement durch die Schrittweite (finden Sie unter [SetStep](#setstep)) und zeichnet die Leiste, um die neue Position zu berücksichtigen.|

## <a name="remarks"></a>Hinweise

Ein Statusanzeige-Steuerelement ist ein Fenster, das eine Anwendung verwenden kann, um den Fortschritt einer längeren Operation angibt. Er besteht aus einem Rechteck, das allmählich von links nach rechts, mit dem System Fortschreiten eines Vorgangs die Hervorhebungsfarbe für gefüllt wird.

Ein Statusanzeige-Steuerelement verfügt über einen Bereich und eine aktuelle Position. Den Bereich darstellt, der Gesamtdauer des Vorgangs, und die aktuelle Position darstellt, den Status, die, den die Anwendung, zum Abschließen des Vorgangs erstellt hat. Die Fensterprozedur werden der Bereich und die aktuelle Position verwendet, um den Prozentsatz der Statusanzeige mit der Hervorhebungsfarbe füllen zu bestimmen. Da der Bereich und die Positionswerte der aktuellen als Ganzzahlen mit Vorzeichen ausgedrückt werden, ist der mögliche Wertebereich aktuelle Position von – 2.147.483.648 bis 2.147.483.647 einschließlich angezeigt.

Weitere Informationen zur Verwendung von `CProgressCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CProgressCtrl](../../mfc/using-cprogressctrl.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CProgressCtrl`

## <a name="requirements"></a>Anforderungen

**Header:** afxcmn.h

##  <a name="cprogressctrl"></a>  CProgressCtrl::CProgressCtrl

Erstellt ein `CProgressCtrl`-Objekt.

```
CProgressCtrl();
```

### <a name="remarks"></a>Hinweise

Nach dem Erstellen der `CProgressCtrl` Objekt, rufen Sie `CProgressCtrl::Create` das Statusanzeige-Steuerelement zu erstellen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CProgressCtrl#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_1.cpp)]

##  <a name="create"></a>  CProgressCtrl

Erstellt ein Statusanzeige-Steuerelement, und fügt sie an einer `CProgressCtrl` Objekt.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*dwStyle*<br/>
Gibt das Statusanzeige-Steuerelement Stil. Wenden Sie eine beliebige Kombination von Fenster Stylesdescribed in [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) im Windows SDK, zusätzlich zu den folgenden Statusanzeige Stile von Listensteuerelementen, an das Steuerelement:

- PBS_VERTICAL zeigt Statusinformationen vertikal, von oben nach unten. Ohne dieses Flag zeigt das Statusanzeige-Steuerelement horizontal "," links nach rechts.

- PBS_SMOOTH zeigt allmählichen, smooth das Statusanzeige-Steuerelement ausfüllen. Ohne dieses Flag wird das Steuerelement mit Blöcken füllen.

*Rect*<br/>
Gibt an, des Statusanzeige-Steuerelements die Größe und Position. Es kann sein, entweder eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder ein [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur. Da das Steuerelement ein untergeordnetes Fenster sein muss, werden die angegebenen Koordinaten relativ zum Clientbereich befinden die *pParentWnd*.

*pParentWnd*<br/>
Gibt an, der Statusanzeige übergeordnete Fenster des Steuerelements, in der Regel eine `CDialog`. Es darf nicht NULL sein.

*nID*<br/>
Gibt das Statusanzeige-Steuerelement ID an.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die `CProgressCtrl` Objekt wurde erfolgreich erstellt wird; andernfalls "false".

### <a name="remarks"></a>Hinweise

Sie erstellen eine `CProgressCtrl` Objekt in zwei Schritten. Rufen Sie zunächst den Konstruktor, der erstellt das `CProgressCtrl` Objekt aus, und rufen dann `Create`, erstellt das Statusanzeige-Steuerelement.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CProgressCtrl#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_2.cpp)]

##  <a name="createex"></a>  CProgressCtrl::CreateEx

Erstellt ein Steuerelement (ein untergeordnetes Fenster) und ordnet ihn dem `CProgressCtrl` Objekt.

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*dwExStyle*<br/>
Gibt den erweiterten Stil des Steuerelements erstellt wird. Eine Liste der erweiterten Windows-Stile, finden Sie unter den *DwExStyle* -Parameter für [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) im Windows SDK.

*dwStyle*<br/>
Gibt das Statusanzeige-Steuerelement Stil. Wenden Sie eine beliebige Kombination von Window-Stile, die in beschriebenen [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) im Windows SDK.

*Rect*<br/>
Ein Verweis auf eine [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die Größe und Position des Fensters erstellt werden, in Clientkoordinaten des beschreibt *pParentWnd*.

*pParentWnd*<br/>
Ein Zeiger auf das Fenster, das übergeordnete Element des Steuerelements ist.

*nID*<br/>
Der ID des Steuerelements untergeordneten Fensters mit.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Verwendung `CreateEx` anstelle von [erstellen](#create) anzuwendende Erweiterte Windows-Stile, angegeben durch den Wert der Windows-erweiterten Stil **WS_EX_**.

##  <a name="getbarcolor"></a>  CProgressCtrl::GetBarColor

Ruft die Farbe der Statusleiste Indikator für den aktuellen Statusanzeige-Steuerelements ab.

```
COLORREF GetBarColor() const;
```

### <a name="return-value"></a>Rückgabewert

Die Farbe des aktuellen Statusanzeige, dargestellt als eine [COLORREF](/windows/desktop/gdi/colorref) Wert oder CLR_DEFAULT ist die Farbe des Status Indicator die Standardfarbe.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [PBM_GETBARCOLOR](/windows/desktop/Controls/pbm-getbarcolor) -Nachricht, die im Windows SDK beschrieben wird.

##  <a name="getbkcolor"></a>  CProgressCtrl::GetBkColor

Ruft die Hintergrundfarbe des aktuellen Statusanzeige ab.

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>Rückgabewert

Die Hintergrundfarbe des aktuellen Statusanzeige, dargestellt als eine [COLORREF](/windows/desktop/gdi/colorref) Wert.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [PBM_GETBKCOLOR](/windows/desktop/Controls/pbm-getbkcolor) -Nachricht, die im Windows SDK beschrieben wird.

##  <a name="getpos"></a>  CProgressCtrl::GetPos

Ruft die aktuelle Position der Statusanzeige ab.

```
int GetPos();
```

### <a name="return-value"></a>Rückgabewert

Die Position der Statusanzeige-Steuerelements.

### <a name="remarks"></a>Hinweise

Die Position der Statusanzeige-Steuerelements nicht den physischen Speicherort auf dem Bildschirm, sondern vielmehr wird zwischen dem oberen und unteren Bereich in angegeben [SetRange](#setrange).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CProgressCtrl#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_3.cpp)]

##  <a name="getrange"></a>  CProgressCtrl::GetRange

Ruft den aktuellen oberen und unteren Grenzwerten oder Adressbereichs für das Statusanzeige-Steuerelement.

```
void GetRange(
    int& nLower,
    int& nUpper);
```

### <a name="parameters"></a>Parameter

*nLower*<br/>
Ein Verweis auf eine ganze Zahl, die die untere Grenze des das Statusanzeige-Steuerelement zu empfangen.

*nUpper*<br/>
Ein Verweis auf eine ganze Zahl, die die obere Grenze der das Statusanzeige-Steuerelement zu empfangen.

### <a name="remarks"></a>Hinweise

Diese Funktion kopiert die Werte der den oberen und unteren Grenzwerten für den ganzen Zahlen verweist *nLower* und *nUpper*bzw.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CProgressCtrl#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_4.cpp)]

##  <a name="getstate"></a>  CProgressCtrl:: GetState

Ruft den Zustand der aktuellen Statusanzeige-Steuerelements ab.

```
int GetState() const;
```

### <a name="return-value"></a>Rückgabewert

Der Status der der aktuellen Statusanzeige-Steuerelements, das eines der folgenden Werte:

|Wert|Zustand|
|-----------|-----------|
|PBST_NORMAL|In Bearbeitung|
|PBST_ERROR|Fehler|
|PBST_PAUSED|Paused|

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [PBM_GETSTATE](/windows/desktop/Controls/pbm-getstate) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable `m_progressCtrl`, die für den programmgesteuerten Zugriff auf das Statusanzeige-Steuerelement verwendet wird. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel ruft den Zustand des aktuellen Statusanzeige-Steuerelements ab.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_6.cpp)]

##  <a name="getstep"></a>  CProgressCtrl::GetStep

Ruft die Schrittweite für die Statusanzeige des aktuellen Statusanzeige-Steuerelements ab.

```
int GetStep() const;
```

### <a name="return-value"></a>Rückgabewert

Die Schrittweite der Statusanzeige.

### <a name="remarks"></a>Hinweise

Die Schrittweite ist der Betrag, einem Aufruf von [CProgressCtrl::StepIt](#stepit) erhöht die aktuelle Position der Statusanzeige.

Diese Methode sendet die [PBM_GETSTEP](/windows/desktop/Controls/pbm-getstep) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable `m_progressCtrl`, die für den programmgesteuerten Zugriff auf das Statusanzeige-Steuerelement verwendet wird. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel ruft die Schrittweite von der aktuellen Statusanzeige-Steuerelements ab.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#3](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_7.cpp)]

##  <a name="offsetpos"></a>  CProgressCtrl::OffsetPos

Verschiebt die Statusanzeige der aktuellen Position des Steuerelements durch das Inkrement, das anhand des *nPos* und zeichnet die Leiste, um die neue Position zu berücksichtigen.

```
int OffsetPos(int nPos);
```

### <a name="parameters"></a>Parameter

*nPos*<br/>
Betrag, um die Position fahren Sie fort.

### <a name="return-value"></a>Rückgabewert

Die vorherigen Position der Statusanzeige-Steuerelements.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CProgressCtrl#5](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_8.cpp)]

##  <a name="setbarcolor"></a>  CProgressCtrl::SetBarColor

Legt die Farbe der Statusleiste Indikator in der aktuellen Statusanzeige-Steuerelements fest.

```
COLORREF SetBarColor(COLORREF clrBar);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*clrBar*|[in] Ein [COLORREF](/windows/desktop/gdi/colorref) Wert, der die neue Farbe der Statusleiste Indikator angibt. Geben Sie CLR_DEFAULT um dazu führen, dass die Statusanzeige auf ihre Standardfarbe verwenden.|

### <a name="return-value"></a>Rückgabewert

Die vorherige Farbe der Indikator Statusanzeige, dargestellt als eine [COLORREF](/windows/desktop/gdi/colorref) Wert oder CLR_DEFAULT die Farbe der Statusleiste Indikator ist die Standardfarbe.

### <a name="remarks"></a>Hinweise

Die `SetBarColor` Methode wird die Statusanzeige nur Farbe, wenn eine Windows Vista [Design](/windows/desktop/Controls/visual-styles-overview) ist nicht aktiv.

Diese Methode sendet die [PBM_SETBARCOLOR](/windows/desktop/Controls/pbm-setbarcolor) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable `m_progressCtrl`, die für den programmgesteuerten Zugriff auf das Statusanzeige-Steuerelement verwendet wird. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Beispiel

Das folgende Codebeispiel ändert die Farbe der Statusleiste auf Rot, Grün, Blau oder die Standardeinstellung.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_9.cpp)]

##  <a name="setbkcolor"></a>  CProgressCtrl::SetBkColor

Legt die Farbe des Hintergrunds für die Statusanzeige fest.

```
COLORREF SetBkColor(COLORREF clrNew);
```

### <a name="parameters"></a>Parameter

*clrNew*<br/>
Eine COLORREF-Wert, der die neue Hintergrundfarbe angibt. Geben Sie den CLR_DEFAULT-Wert, um die Standardhintergrundfarbe für die Statusanzeige zu verwenden.

### <a name="return-value"></a>Rückgabewert

Die [COLORREF](/windows/desktop/gdi/colorref) Wert, der angibt, die vorherige Background-Farbe oder CLR_DEFAULT die Hintergrundfarbe ist die Standardfarbe.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CProgressCtrl#6](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_10.cpp)]

##  <a name="setmarquee"></a>  CProgressCtrl::SetMarquee

Aktiviert die Marquee-Modus aktiviert oder deaktiviert für den aktuellen Statusanzeige-Steuerelements.

```
BOOL SetMarquee(
    BOOL fMarqueeMode,
    int nInterval);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*fMarqueeMode*|[in] "True" Turn Marquee-Modus an, oder "false" zum Marquee-Modus zu deaktivieren.|
|*Nintervall*|[in] Zeit in Millisekunden zwischen den Updates der Marquee-Animation.|

### <a name="return-value"></a>Rückgabewert

Diese Methode gibt immer "true" zurück.

### <a name="remarks"></a>Hinweise

Wenn Marquee-Modus aktiviert ist, die Statusanzeige animiert wird und wie einen Bildlauf eine Anmeldung über einen Auswahlbereich Theater.

Diese Methode sendet die [PBM_SETMARQUEE](/windows/desktop/Controls/pbm-setmarquee) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable `m_progressCtrl`, die für den programmgesteuerten Zugriff auf das Statusanzeige-Steuerelement verwendet wird. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird gestartet und beendet die Laufschrift Animation.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_11.cpp)]

##  <a name="setpos"></a>  CProgressCtrl::SetPos

Legt den Status Balken der aktuellen Position des Steuerelements gemäß *nPos* und zeichnet die Leiste, um die neue Position zu berücksichtigen.

```
int SetPos(int nPos);
```

### <a name="parameters"></a>Parameter

*nPos*<br/>
Neue Position der Statusanzeige-Steuerelements.

### <a name="return-value"></a>Rückgabewert

Die vorherigen Position der Statusanzeige-Steuerelements.

### <a name="remarks"></a>Hinweise

Die Position der Statusanzeige-Steuerelements nicht den physischen Speicherort auf dem Bildschirm, sondern vielmehr wird zwischen dem oberen und unteren Bereich in angegeben [SetRange](#setrange).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CProgressCtrl#7](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_12.cpp)]

##  <a name="setrange"></a>  CProgressCtrl::SetRange

Legt die obere und untere Grenze der Statusanzeige Bereichs des Steuerelements fest und zeichnet die Leiste, um die neue Bereiche widerspiegeln.

```
void SetRange(
    short nLower,
    short nUpper);


void SetRange32(
    int nLower,
    int nUpper);
```

### <a name="parameters"></a>Parameter

*nLower*<br/>
Gibt die untere Grenze des Bereichs (die Standardeinstellung ist 0 (null)).

*nUpper*<br/>
Gibt an, die obere Grenze des Bereichs (die Standardeinstellung ist 100).

### <a name="remarks"></a>Hinweise

Die Memberfunktion `SetRange32` legt den 32-Bit-Bereich für das Statussteuerelement fest.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CProgressCtrl#8](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_13.cpp)]

##  <a name="setstate"></a>  CProgressCtrl::SetState

Legt den Status des aktuellen Statusanzeige-Steuerelements fest.

```
int SetState(int iState);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*iState*|[in] Der Zustand die Statusanzeige festlegen. Verwenden Sie einen der folgenden Werte:<br /><br /> -PBST_NORMAL – In Bearbeitung<br />-PBST_ERROR - Fehler<br />-PBST_PAUSED - angehalten|

### <a name="return-value"></a>Rückgabewert

Der vorherige Status des aktuellen Statusanzeige-Steuerelements.

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [PBM_SETSTATE](/windows/desktop/Controls/pbm-setstate) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert die Variable `m_progressCtrl`, die für den programmgesteuerten Zugriff auf das Statusanzeige-Steuerelement verwendet wird. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_5.h)]

### <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird der Status des aktuellen Statusanzeige-Steuerelements auf angehalten oder In Bearbeitung festgelegt.

[!code-cpp[NVC_MFC_CProgressCtrl_s1#4](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_14.cpp)]

##  <a name="setstep"></a>  CProgressCtrl::SetStep

Gibt an, die Schrittweite für ein Statusanzeige-Steuerelement.

```
int SetStep(int nStep);
```

### <a name="parameters"></a>Parameter

*nStep*<br/>
Neuen Schritt Inkrement.

### <a name="return-value"></a>Rückgabewert

Der vorherige Schritt Inkrement.

### <a name="remarks"></a>Hinweise

Die Schrittweite ist der Betrag, einen Aufruf von `CProgressCtrl::StepIt` den Fortschritt erhöht die aktuelle Position.

Die Schrittweite der Standardwert ist 10.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CProgressCtrl#9](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_15.cpp)]

##  <a name="stepit"></a>  CProgressCtrl::StepIt

Verschiebt die aktuelle Position für ein Statusanzeige-Steuerelement durch die Schrittweite und zeichnet die Leiste, um die neue Position zu berücksichtigen.

```
int StepIt();
```

### <a name="return-value"></a>Rückgabewert

Die vorherigen Position der Statusanzeige-Steuerelements.

### <a name="remarks"></a>Hinweise

Die Schrittweite wird festgelegt, indem die `CProgressCtrl::SetStep` Member-Funktion.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CProgressCtrl#10](../../mfc/reference/codesnippet/cpp/cprogressctrl-class_16.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel CMNCTRL2](../../visual-cpp-samples.md)<br/>
[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)


