---
title: CSpinButtonCtrl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl::CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl::Create
- AFXCMN/CSpinButtonCtrl::CreateEx
- AFXCMN/CSpinButtonCtrl::GetAccel
- AFXCMN/CSpinButtonCtrl::GetBase
- AFXCMN/CSpinButtonCtrl::GetBuddy
- AFXCMN/CSpinButtonCtrl::GetPos
- AFXCMN/CSpinButtonCtrl::GetRange
- AFXCMN/CSpinButtonCtrl::SetAccel
- AFXCMN/CSpinButtonCtrl::SetBase
- AFXCMN/CSpinButtonCtrl::SetBuddy
- AFXCMN/CSpinButtonCtrl::SetPos
- AFXCMN/CSpinButtonCtrl::SetRange
helpviewer_keywords:
- CSpinButtonCtrl [MFC], CSpinButtonCtrl
- CSpinButtonCtrl [MFC], Create
- CSpinButtonCtrl [MFC], CreateEx
- CSpinButtonCtrl [MFC], GetAccel
- CSpinButtonCtrl [MFC], GetBase
- CSpinButtonCtrl [MFC], GetBuddy
- CSpinButtonCtrl [MFC], GetPos
- CSpinButtonCtrl [MFC], GetRange
- CSpinButtonCtrl [MFC], SetAccel
- CSpinButtonCtrl [MFC], SetBase
- CSpinButtonCtrl [MFC], SetBuddy
- CSpinButtonCtrl [MFC], SetPos
- CSpinButtonCtrl [MFC], SetRange
ms.assetid: 509bfd76-1c5a-4af6-973f-e133c0b87734
ms.openlocfilehash: c167745eed45b7081e62a2c3be225a33e7ee0520
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502438"
---
# <a name="cspinbuttonctrl-class"></a>CSpinButtonCtrl-Klasse

Stellt die Funktionalität des allgemeinen Windows-Drehfeld-Steuerelements bereit.

## <a name="syntax"></a>Syntax

```
class CSpinButtonCtrl : public CWnd
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CSpinButtonCtrl::CSpinButtonCtrl](#cspinbuttonctrl)|Erstellt ein `CSpinButtonCtrl`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSpinButtonCtrl::Create](#create)|Erstellt ein Drehfeld-Steuerelement und fügt es `CSpinButtonCtrl` an ein-Objekt an.|
|[CSpinButtonCtrl::CreateEx](#createex)|Erstellt ein Drehfeld-Steuerelement mit den angegebenen erweiterten Windows-Stilen und fügt `CSpinButtonCtrl` es an ein-Objekt an.|
|[CSpinButtonCtrl::GetAccel](#getaccel)|Ruft Beschleunigungs Informationen für ein Drehfeld-Steuerelement ab.|
|[CSpinButtonCtrl::GetBase](#getbase)|Ruft die aktuelle Basis für ein Drehfeld-Steuerelement ab.|
|[CSpinButtonCtrl::GetBuddy](#getbuddy)|Ruft einen Zeiger auf das aktuelle Buddy-Fenster ab.|
|[CSpinButtonCtrl::GetPos](#getpos)|Ruft die aktuelle Position eines Drehfeld-Steuer Elements ab.|
|[CSpinButtonCtrl::GetRange](#getrange)|Ruft die obere und untere Grenze (Bereich) für ein Drehfeld-Steuerelement ab.|
|[CSpinButtonCtrl::SetAccel](#setaccel)|Legt die Beschleunigung für ein Drehfeld-Steuerelement fest.|
|[CSpinButtonCtrl::SetBase](#setbase)|Legt die Basis für ein Drehfeld-Steuerelement fest.|
|[CSpinButtonCtrl::SetBuddy](#setbuddy)|Legt das Buddy-Fenster für ein Drehfeld-Steuerelement fest.|
|[CSpinButtonCtrl::SetPos](#setpos)|Legt die aktuelle Position für das-Steuerelement fest.|
|[CSpinButtonCtrl::SetRange](#setrange)|Legt die obere und untere Begrenzung (Bereich) für ein Drehfeld-Steuerelement fest.|

## <a name="remarks"></a>Hinweise

Ein Drehfeld-Steuerelement (auch als auf-ab-Steuerelement bezeichnet) ist ein paar von Pfeil Schaltflächen, auf die der Benutzer klicken kann, um einen Wert zu erhöhen oder zu verringern, z. b. eine Bild Lauf Position oder eine Zahl, die in einem Begleit Steuerelement angezeigt wird. Der Wert, der einem Drehfeld-Steuerelement zugeordnet ist, wird als aktuelle Position bezeichnet. Ein Drehfeld-Steuerelement wird am häufigsten mit einem Begleit Steuerelement verwendet, das als "Buddy-Fenster" bezeichnet wird.

Dieses Steuerelement (und damit `CSpinButtonCtrl` auch die-Klasse) ist nur für Programme verfügbar, die unter Windows 95/98 und Windows NT, Version 3,51 und höher, ausgeführt werden.

Für den Benutzer sehen ein Drehfeld-Steuerelement und das zugehörige Buddy-Fenster oft wie ein einzelnes Steuerelement aus. Sie können angeben, dass sich ein Drehfeld-Steuerelement automatisch neben seinem Buddy-Fenster positioniert, und dass die Beschriftung des Buddy-Fensters automatisch auf die aktuelle Position festgelegt wird. Sie können ein Drehfeld-Steuerelement mit einem Bearbeitungs Steuerelement verwenden, um den Benutzer zur Eingabe der numerischen Eingabe aufzufordern.

Wenn Sie auf den Pfeil nach oben klicken, wird die aktuelle Position in Richtung des maximalen Werts verschoben, und durch Klicken auf den Pfeil nach unten wird die aktuelle Position in Richtung Standardmäßig ist der Minimalwert 100, der Höchstwert ist 0. Jedes Mal, wenn die minimale Einstellung größer ist als die maximale Einstellung (z. b. wenn die Standardeinstellungen verwendet werden), wird durch Klicken auf den Pfeil nach oben der Positionswert verringert und durch Klicken auf den Pfeil nach unten vergrößert.

Ein Drehfeld-Steuerelement ohne ein Buddy-Fenster fungiert als eine Art vereinfachter Bild Lauf Leiste. Beispielsweise wird in einem Registerkarten-Steuerelement manchmal ein Drehfeld-Steuerelement angezeigt, um dem Benutzer zu ermöglichen, zusätzliche Registerkarten in die Ansicht zu

Weitere Informationen zum Verwenden von `CSpinButtonCtrl`finden Sie unter Steuer [Elemente](../../mfc/controls-mfc.md) und [Verwenden von CSpinButtonCtrl](../../mfc/using-cspinbuttonctrl.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CSpinButtonCtrl`

## <a name="requirements"></a>Anforderungen

**Header:** afxcmn.h

##  <a name="create"></a>CSpinButtonCtrl:: Create

Erstellt ein Drehfeld-Steuerelement und fügt es `CSpinButtonCtrl` an ein-Objekt an.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*dwStyle*<br/>
Gibt den Stil des Drehfeld-Steuer Elements an. Anwenden einer beliebigen Kombination von Drehfeld-Steuerelement Stilen auf das-Steuerelement. Diese Stile werden in den [Steuer](/windows/win32/Controls/up-down-control-styles) Element Formaten im Windows SDK beschrieben.

*Rect*<br/>
Gibt die Größe und Position des Drehfeld-Steuer Elements an. Dies kann entweder ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt oder eine [Rect](/previous-versions/dd162897\(v=vs.85\)) -Struktur sein.

*pParentWnd*<br/>
Ein Zeiger auf das übergeordnete Fenster des Drehfeld-Steuer Elements `CDialog`, normalerweise ein. Er darf nicht NULL sein.

*nID*<br/>
Gibt die ID des Drehfeld-Steuer Elements an.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Initialisierung erfolgreich war. andernfalls 0.

### <a name="remarks"></a>Hinweise

Zuerst erstellen Sie `CSpinButtonCtrl` ein-Objekt in zwei Schritten, nennen den-Konstruktor, und `Create`dann wird aufgerufen, wodurch das Drehfeld-Steuerelement erstellt `CSpinButtonCtrl` und an das-Objekt angefügt wird.

Um ein Drehfeld-Steuerelement mit erweiterten Fenster Stilen zu erstellen, rufen Sie [CSpinButtonCtrl:: createex](#createex) anstelle von `Create`auf.

##  <a name="createex"></a>CSpinButtonCtrl:: createex

Erstellt ein-Steuerelement (ein untergeordnetes Fenster) und ordnet `CSpinButtonCtrl` es dem-Objekt zu.

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
Gibt die erweiterte Art des zu erstellenden Steuer Elements an. Eine Liste erweiterter Windows-Stile finden Sie unter dem *dwExStyle* -Parameter für " [kreatewindowex](/windows/win32/api/winuser/nf-winuser-createwindowexw) " in der Windows SDK.

*dwStyle*<br/>
Gibt den Stil des Drehfeld-Steuer Elements an. Anwenden einer beliebigen Kombination von Drehfeld-Steuerelement Stilen auf das-Steuerelement. Diese Stile werden in den [Steuer](/windows/win32/Controls/up-down-control-styles) Element Formaten im Windows SDK beschrieben.

*Rect*<br/>
Ein Verweis auf eine [Rect](/previous-versions/dd162897\(v=vs.85\)) -Struktur, die die Größe und Position des zu erstellenden Fensters in Client Koordinaten von *pparser*beschreibt.

*pParentWnd*<br/>
Ein Zeiger auf das Fenster, das das übergeordnete Element des Steuer Elements ist.

*nID*<br/>
Die ID des untergeordneten Fensters des Steuer Elements.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Verwenden `CreateEx` Sie anstelle von [Create](#create) , um erweiterte Windows-Stile anzuwenden, die durch den erweiterten Windows-Stil WS_EX_ angegeben werden.

##  <a name="cspinbuttonctrl"></a>CSpinButtonCtrl:: CSpinButtonCtrl

Erstellt ein `CSpinButtonCtrl`-Objekt.

```
CSpinButtonCtrl();
```

##  <a name="getaccel"></a>CSpinButtonCtrl:: GetAccel

Ruft Beschleunigungs Informationen für ein Drehfeld-Steuerelement ab.

```
UINT GetAccel(
    int nAccel,
    UDACCEL* pAccel) const;
```

### <a name="parameters"></a>Parameter

*nAccel*<br/>
Anzahl der Elemente im Array, das von *paccel*angegeben wird.

*pAccel*<br/>
Ein Zeiger auf ein Array von [udaccel](/windows/win32/api/commctrl/ns-commctrl-udaccel) -Strukturen, das Beschleunigungs Informationen empfängt.

### <a name="return-value"></a>Rückgabewert

Anzahl der abgerufenen Zugriffstasten Strukturen.

##  <a name="getbase"></a>CSpinButtonCtrl:: GetBase

Ruft die aktuelle Basis für ein Drehfeld-Steuerelement ab.

```
UINT GetBase() const;
```

### <a name="return-value"></a>Rückgabewert

Der aktuelle Basiswert.

##  <a name="getbuddy"></a>CSpinButtonCtrl:: GetBuddy

Ruft einen Zeiger auf das aktuelle Buddy-Fenster ab.

```
CWnd* GetBuddy() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das aktuelle Buddy-Fenster.

##  <a name="getpos"></a>CSpinButtonCtrl:: GetPos

Ruft die aktuelle Position eines Drehfeld-Steuer Elements ab.

```
int GetPos() const;  int GetPos32(LPBOOL lpbError = NULL) const;
```

### <a name="parameters"></a>Parameter

*lpbError*<br/>
Ein Zeiger auf einen booleschen Wert, der auf 0 (null) festgelegt wird, wenn der Wert erfolgreich abgerufen wird, oder ungleich 0 (null), wenn ein Fehler auftritt. Wenn dieser Parameter auf NULL festgelegt ist, werden keine Fehler gemeldet.

### <a name="return-value"></a>Rückgabewert

Die erste Version gibt die 16-Bit-aktuelle Position in dem nieder wertigen Wort zurück. Wenn ein Fehler aufgetreten ist, ist das hochwertige Wort ungleich NULL.

Die zweite Version gibt die 32-Bit-Position zurück.

### <a name="remarks"></a>Hinweise

Wenn der zurückgegebene Wert verarbeitet wird, aktualisiert das Steuerelement seine aktuelle Position basierend auf der Beschriftung des Buddy-Fensters. Das-Steuerelement gibt einen Fehler zurück, wenn kein Buddy-Fenster vorhanden ist oder wenn die Beschriftung einen ungültigen Wert oder einen Wert außerhalb des gültigen Bereichs angibt.

##  <a name="getrange"></a>CSpinButtonCtrl:: GetRange

Ruft die obere und untere Grenze (Bereich) für ein Drehfeld-Steuerelement ab.

```
DWORD GetRange() const;

void GetRange(
    int& lower,
    int& upper) const;

void GetRange32(
    int& lower,
    int &upper) const;
```

### <a name="parameters"></a>Parameter

*günstigere*<br/>
Verweis auf eine Ganzzahl, die die untere Grenze für das-Steuerelement empfängt.

*weite*<br/>
Verweis auf eine Ganzzahl, die die Obergrenze für das-Steuerelement empfängt.

### <a name="return-value"></a>Rückgabewert

Die erste Version gibt einen 32-Bit-Wert zurück, der die oberen und unteren Grenzwerte enthält. Das nieder wertige Wort ist die Obergrenze für das Steuerelement, und das höchst wertige Wort ist die untere Grenze.

### <a name="remarks"></a>Hinweise

Die Member- `GetRange32` Funktion Ruft den Bereich des Drehfeld-Steuer Elements als 32-Bit-Ganzzahl ab.

##  <a name="setaccel"></a>CSpinButtonCtrl:: SetAccel

Legt die Beschleunigung für ein Drehfeld-Steuerelement fest.

```
BOOL SetAccel(
    int nAccel,
    UDACCEL* pAccel);
```

### <a name="parameters"></a>Parameter

*nAccel*<br/>
Anzahl der durch *paccel*angegebenen [udaccel](/windows/win32/api/commctrl/ns-commctrl-udaccel) -Strukturen.

*pAccel*<br/>
Zeiger auf ein Array von udaccel-Strukturen, die Beschleunigungs Informationen enthalten. Elemente müssen in aufsteigender Reihenfolge basierend auf dem `nSec` Element sortiert werden.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

##  <a name="setbase"></a>CSpinButtonCtrl:: setbase

Legt die Basis für ein Drehfeld-Steuerelement fest.

```
int SetBase(int nBase);
```

### <a name="parameters"></a>Parameter

*nBase*<br/>
Neuer Basiswert für das Steuerelement. Sie kann für "Decimal" oder "16" für hexadezimale 10 lauten.

### <a name="return-value"></a>Rückgabewert

Der vorherige Basiswert, wenn erfolgreich, oder 0 (null), wenn eine ungültige Basis angegeben wird.

### <a name="remarks"></a>Hinweise

Der Basiswert bestimmt, ob das Buddy-Fenster Zahlen in Dezimal-oder hexadezimal Ziffern anzeigt. Hexadezimale Zahlen sind immer unsigniert. Dezimalzahlen werden signiert.

##  <a name="setbuddy"></a>CSpinButtonCtrl:: SetBuddy

Legt das Buddy-Fenster für ein Drehfeld-Steuerelement fest.

```
CWnd* SetBuddy(CWnd* pWndBuddy);
```

### <a name="parameters"></a>Parameter

*pWndBuddy*<br/>
Zeiger auf das neue Buddy-Fenster.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das vorherige Buddy-Fenster.

### <a name="remarks"></a>Hinweise

Ein Drehfeld-Steuerelement ist fast immer einem anderen Fenster zugeordnet, z. b. einem Bearbeitungs Steuerelement, das Inhalte anzeigt. Dieses andere Fenster wird als "Buddy" des Dreh Steuer Elements bezeichnet.

##  <a name="setpos"></a>CSpinButtonCtrl:: SetPos

Legt die aktuelle Position für ein Drehfeld-Steuerelement fest.

```
int SetPos(int nPos);
int SetPos32(int nPos);
```

### <a name="parameters"></a>Parameter

*nPos*<br/>
Neue Position für das-Steuerelement. Dieser Wert muss im Bereich liegen, der durch die obere und untere Grenze für das Steuerelement angegeben wird.

### <a name="return-value"></a>Rückgabewert

Die vorherige Position (16-Bit-Genauigkeit `SetPos`für, 32-Bit- `SetPos32`Genauigkeit für).

### <a name="remarks"></a>Hinweise

`SetPos32`legt die 32-Bit-Position fest.

##  <a name="setrange"></a>CSpinButtonCtrl:: abge

Legt die obere und untere Begrenzung (Bereich) für ein Drehfeld-Steuerelement fest.

```
void SetRange(
    short nLower,
    short nUpper);

void SetRange32(
    int nLower,
    int nUpper);
```

### <a name="parameters"></a>Parameter

*nlower* und *nupper*<br/>
Obere und untere Grenze für das Steuerelement. Für `SetRange`kann keines der Limits größer als UD_MAXVAL oder kleiner als UD_MINVAL sein. Außerdem darf der Unterschied zwischen den beiden Grenzwerten UD_MAXVAL nicht überschreiten. `SetRange32`gibt keine Einschränkungen für die Grenzen an. Verwenden Sie ganze Zahlen.

### <a name="remarks"></a>Hinweise

Die Member- `SetRange32` Funktion legt den 32-Bit-Bereich für das Drehfeld-Steuerelement fest.

> [!NOTE]
>  Der Standardbereich für die Drehfeld Schaltfläche ist auf NULL (0) und auf 100 festgelegt. Da der Höchstwert kleiner als der minimale Wert ist, wird durch Klicken auf den Pfeil nach oben die Position verringert, und durch Klicken auf den Pfeil nach unten wird der Wert vergrößert. Verwenden `CSpinButtonCtrl::SetRange` Sie, um diese Werte anzupassen.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CSliderCtrl-Klasse](../../mfc/reference/csliderctrl-class.md)
