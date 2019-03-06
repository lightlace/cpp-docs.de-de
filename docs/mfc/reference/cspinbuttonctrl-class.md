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
ms.openlocfilehash: ff61fb4f918e25d430fc31ae55c3ad8794ce39f1
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57425028"
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
|[CSpinButtonCtrl::Create](#create)|Ein Drehfeld-Steuerelement erstellt, und fügt sie an einer `CSpinButtonCtrl` Objekt.|
|[CSpinButtonCtrl::CreateEx](#createex)|Erstellt ein Drehfeld-Steuerelement mit dem angegebenen erweiterten Stile für Windows und fügt sie an einer `CSpinButtonCtrl` Objekt.|
|[CSpinButtonCtrl::GetAccel](#getaccel)|Ruft die Acceleration-Informationen für ein Drehfeld-Steuerelement ab.|
|[CSpinButtonCtrl::GetBase](#getbase)|Ruft die aktuelle Basis für ein Drehfeld-Steuerelement ab.|
|[CSpinButtonCtrl::GetBuddy](#getbuddy)|Ruft einen Zeiger auf das aktuelle Buddyfenster ab.|
|[CSpinButtonCtrl::GetPos](#getpos)|Ruft die aktuelle Position des Drehfeld-Steuerelements ab.|
|[CSpinButtonCtrl::GetRange](#getrange)|Ruft die obere und untere Grenzwerte (Bereich) für ein Drehfeld-Steuerelement ab.|
|[CSpinButtonCtrl::SetAccel](#setaccel)|Legt die Hardwarebeschleunigung für ein Drehfeld-Steuerelement fest.|
|[CSpinButtonCtrl::SetBase](#setbase)|Legt die Basis für ein Drehfeld-Steuerelement fest.|
|[CSpinButtonCtrl::SetBuddy](#setbuddy)|Legt das Buddyfenster für ein Drehfeld-Steuerelement fest.|
|[CSpinButtonCtrl::SetPos](#setpos)|Legt die aktuelle Position für das Steuerelement fest.|
|[CSpinButtonCtrl::SetRange](#setrange)|Legt die obere und untere Grenzwerte (Bereich) für ein Drehfeld-Steuerelement fest.|

## <a name="remarks"></a>Hinweise

Ein "Drehfeld-Steuerelement" (auch als auf-ab-Steuerelement bezeichnet) ist ein Paar von Pfeilschaltflächen, die der Benutzer klicken kann, um inkrementiert oder dekrementiert einen Wert ein, z. B. eine Bildlaufposition oder eine Zahl, die in einem weiteren Steuerelement angezeigt werden. Ein Drehfeld-Steuerelement zugeordnete Wert ist die aktuelle Position aufgerufen. Ein Drehfeld-Steuerelement wird am häufigsten mit einem begleitenden-Steuerelement, bezeichnet als "Buddy-Fenster" verwendet.

Dieses Steuerelement (und somit die `CSpinButtonCtrl` Klasse) ist nur für Programme, die unter Windows 95/98 und Windows NT, Version 3.51 und höher.

Sehen für den Benutzer ein Drehfeld-Steuerelement oft das Buddyfenster wie ein einzelnes Steuerelement ein. Sie können angeben, dass ein Drehfeld-Steuerelement selbst automatisch neben der Buddy-Fenster platzieren und sie automatisch die Beschriftung des Buddy-Fensters auf der aktuellen Position festgelegt. Sie können ein Drehfeld-Steuerelement mit einem Bearbeitungssteuerelement verwenden, um den Benutzer für die numerischen Eingabe aufzufordern.

Klicken Sie auf den Pfeil nach oben verschiebt die aktuelle Position für die maximale Anzahl, und klicken Sie auf den Pfeil nach unten Verschiebt die aktuelle Position in Richtung Minimum. Der Mindestwert beträgt 100 Standardeinstellung und der Höchstwert beträgt 0. Jedes Mal, wenn der niedrigste Wert ist größer als das Maximum festlegen (z. B. wenn die Standardeinstellungen verwendet werden), klicken Sie auf den Stand Pfeil verringern den-Positionswerts, und klicken Sie auf den Pfeil nach unten wird vergrößert.

Ein Drehfeld-Steuerelement ohne als Buddy-Fenster fungiert als eine Art vereinfachte Bildlaufleiste angezeigt. Beispielsweise zeigt ein Registerkarten-Steuerelement, manchmal ein Drehfeldsteuerelement, damit der Benutzer zusätzliche Registerkarten in der Ansicht einen Bildlauf durchführen kann.

Weitere Informationen zur Verwendung von `CSpinButtonCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CSpinButtonCtrl](../../mfc/using-cspinbuttonctrl.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CSpinButtonCtrl`

## <a name="requirements"></a>Anforderungen

**Header:** afxcmn.h

##  <a name="create"></a>  CSpinButtonCtrl::Create

Ein Drehfeld-Steuerelement erstellt, und fügt sie an einer `CSpinButtonCtrl` Objekt...

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*dwStyle*<br/>
Gibt das Drehfeld-Steuerelement Stil. Eine beliebige Kombination von Drehfeld-Schaltflächenstile-Steuerelement auf das Steuerelement anzuwenden. Diese Formate werden in beschrieben [auf-ab-Steuerelementstile](/windows/desktop/Controls/up-down-control-styles) im Windows SDK.

*rect*<br/>
Gibt an, des Drehfeld-Steuerelements die Größe und Position. Es kann sein, entweder eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder ein [RECT](/previous-versions/dd162897\(v=vs.85\)) Struktur

*pParentWnd*<br/>
Ein Zeiger auf das Drehfeld-Steuerelement des übergeordneten Fensters, in der Regel eine `CDialog`. Es darf nicht NULL sein.

*nID*<br/>
Gibt das Drehfeld-Steuerelement ID an.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Initialisierung erfolgreich war; andernfalls 0.

### <a name="remarks"></a>Hinweise

Erstellen Sie eine `CSpinButtonCtrl` zunächst in zwei Schritten Objekt, rufen Sie den Konstruktor und rufen dann `Create`, die das Drehfeld-Steuerelement erstellt, und fügt es der `CSpinButtonCtrl` Objekt.

Rufen Sie zum Erstellen ein Drehfeld-Steuerelement mit erweiterten Fensterstile [CSpinButtonCtrl::CreateEx](#createex) anstelle von `Create`.

##  <a name="createex"></a>  CSpinButtonCtrl::CreateEx

Erstellt ein Steuerelement (ein untergeordnetes Fenster) und ordnet ihn dem `CSpinButtonCtrl` Objekt.

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
Gibt den erweiterten Stil des Steuerelements erstellt wird. Eine Liste der erweiterten Fensterstile, finden Sie unter den *DwExStyle* -Parameter für [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) im Windows SDK.

*dwStyle*<br/>
Gibt das Drehfeld-Steuerelement Stil. Eine beliebige Kombination von Drehfeld-Schaltflächenstile-Steuerelement auf das Steuerelement anzuwenden. Diese Formate werden in beschrieben [auf-ab-Steuerelementstile](/windows/desktop/Controls/up-down-control-styles) im Windows SDK.

*rect*<br/>
Ein Verweis auf eine [RECT](/previous-versions/dd162897\(v=vs.85\)) Struktur, die die Größe und Position des Fensters erstellt werden, in Clientkoordinaten des beschreibt *pParentWnd*.

*pParentWnd*<br/>
Ein Zeiger auf das Fenster, das übergeordnete Element des Steuerelements ist.

*nID*<br/>
Der ID des Steuerelements untergeordneten Fensters mit.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Verwendung `CreateEx` anstelle von [erstellen](#create) anzuwendende Erweiterte Windows-Stile, durch den erweiterten Stil-Wert des Windows WS_EX_ angegeben.

##  <a name="cspinbuttonctrl"></a>  CSpinButtonCtrl::CSpinButtonCtrl

Erstellt ein `CSpinButtonCtrl`-Objekt.

```
CSpinButtonCtrl();
```

##  <a name="getaccel"></a>  CSpinButtonCtrl::GetAccel

Ruft die Acceleration-Informationen für ein Drehfeld-Steuerelement ab.

```
UINT GetAccel(
    int nAccel,
    UDACCEL* pAccel) const;
```

### <a name="parameters"></a>Parameter

*nAccel*<br/>
Anzahl der Elemente im Array vom angegebenen *pAccel*.

*pAccel*<br/>
Zeiger auf ein Array von [UDACCEL](/windows/desktop/api/commctrl/ns-commctrl-_udaccel) Strukturen, die Beschleunigung Informationen empfängt.

### <a name="return-value"></a>Rückgabewert

Die Anzahl von Accelerator-Strukturen abgerufen.

##  <a name="getbase"></a>  CSpinButtonCtrl::GetBase

Ruft die aktuelle Basis für ein Drehfeld-Steuerelement ab.

```
UINT GetBase() const;
```

### <a name="return-value"></a>Rückgabewert

Der aktuelle Basiswert.

##  <a name="getbuddy"></a>  CSpinButtonCtrl::GetBuddy

Ruft einen Zeiger auf das aktuelle Buddyfenster ab.

```
CWnd* GetBuddy() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das aktuelle Buddyfenster.

##  <a name="getpos"></a>  CSpinButtonCtrl::GetPos

Ruft die aktuelle Position des Drehfeld-Steuerelements ab.

```
int GetPos() const;  int GetPos32(LPBOOL lpbError = NULL) const;
```

### <a name="parameters"></a>Parameter

*lpbError*<br/>
Ein Zeiger auf ein boolescher Wert, der auf NULL, wenn den Wert festgelegt ist, ist erfolgreich abgerufen oder ungleich NULL, wenn ein Fehler auftritt. Wenn dieser Parameter auf NULL festgelegt ist, werden Fehler nicht gemeldet.

### <a name="return-value"></a>Rückgabewert

Die erste Version gibt zurück, die 16-Bit für die aktuelle Position in das niederwertige Wort. Das höherwertige Wort ist ungleich NULL, wenn ein Fehler aufgetreten ist.

Die zweite Version gibt die 32-Bit-Position zurück.

### <a name="remarks"></a>Hinweise

Bei der Verarbeitung des zurückgegebene Werts, aktualisiert das Steuerelement seine aktuelle Position basierend auf die Beschriftung des Buddy-Fensters. Das Steuerelement wird ein Fehler zurückgegeben, wenn kein Buddyfenster vorhanden ist oder die Beschriftung einen Wert ungültigen ist oder außerhalb des gültigen Bereichs angibt.

##  <a name="getrange"></a>  CSpinButtonCtrl::GetRange

Ruft die obere und untere Grenzwerte (Bereich) für ein Drehfeld-Steuerelement ab.

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

*lower*<br/>
Verweis auf eine ganze Zahl, die die untere Grenze des Steuerelements empfängt.

*upper*<br/>
Verweis auf eine ganze Zahl, die die Obergrenze für das Steuerelement empfängt.

### <a name="return-value"></a>Rückgabewert

Die erste Version gibt einen 32-Bit-Wert, der die obere und untere Grenze enthält. Das niederwertige Wort ist die Obergrenze für das Steuerelement, und das höherwertige Wort wird die untere Grenze.

### <a name="remarks"></a>Hinweise

Die Memberfunktion `GetRange32` Ruft das Drehfeld-Steuerelement des Bereichs als 32-Bit-Ganzzahl.

##  <a name="setaccel"></a>  CSpinButtonCtrl::SetAccel

Legt die Hardwarebeschleunigung für ein Drehfeld-Steuerelement fest.

```
BOOL SetAccel(
    int nAccel,
    UDACCEL* pAccel);
```

### <a name="parameters"></a>Parameter

*nAccel*<br/>
Anzahl der [UDACCEL](/windows/desktop/api/commctrl/ns-commctrl-_udaccel) Strukturen, die anhand des *pAccel*.

*pAccel*<br/>
Zeiger auf ein Array von UDACCEL-Strukturen, die Beschleunigung Informationen enthalten. Elemente in aufsteigender Reihenfolge sortiert werden soll. die `nSec` Member.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

##  <a name="setbase"></a>  CSpinButtonCtrl::SetBase

Legt die Basis für ein Drehfeld-Steuerelement fest.

```
int SetBase(int nBase);
```

### <a name="parameters"></a>Parameter

*nBase*<br/>
Neue Basiswert für das Steuerelement. Es kann 10 für Dezimalzahlen oder 16 für hexadezimal sein.

### <a name="return-value"></a>Rückgabewert

Der vorherige Basiswert bei Erfolg, oder 0 (null), wenn ungültige Basis angegeben ist.

### <a name="remarks"></a>Hinweise

Der Basiswert bestimmt, ob es sich bei Buddy-Fensters Zahlen im Dezimal- oder Hexadezimalformat anzeigt. Hexadezimale Zahlen sind immer unsigniert; Dezimalzahlen werden signiert.

##  <a name="setbuddy"></a>  CSpinButtonCtrl::SetBuddy

Legt das Buddyfenster für ein Drehfeld-Steuerelement fest.

```
CWnd* SetBuddy(CWnd* pWndBuddy);
```

### <a name="parameters"></a>Parameter

*pWndBuddy*<br/>
Zeiger auf das neue Buddyfenster.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die vorherige Buddy-Fenster.

### <a name="remarks"></a>Hinweise

Ein Drehfeld-Steuerelement ist fast immer ein anderes Fenster, z. B. ein Bearbeitungssteuerelement, die Teil des Inhalts anzeigt zugeordnet. Diese anderen Fenster wird Ihrem "Kontakt" des Drehfeld-Steuerelements aufgerufen.

##  <a name="setpos"></a>  CSpinButtonCtrl::SetPos

Legt die aktuelle Position für ein Drehfeld-Steuerelement fest.

```
int SetPos(int nPos);
int SetPos32(int nPos);
```

### <a name="parameters"></a>Parameter

*nPos*<br/>
Neue Position für das Steuerelement. Dieser Wert muss im Bereich durch den oberen und unteren Grenzen für das Steuerelement angegeben sein.

### <a name="return-value"></a>Rückgabewert

Die vorherige Position (16-Bit-Genauigkeit für `SetPos`, 32-Bit-Präzision für `SetPos32`).

### <a name="remarks"></a>Hinweise

`SetPos32` die 32-Bit-Position festgelegt.

##  <a name="setrange"></a>  CSpinButtonCtrl:: SetRange

Legt die obere und untere Grenzwerte (Bereich) für ein Drehfeld-Steuerelement fest.

```
void SetRange(
    short nLower,
    short nUpper);

void SetRange32(
    int nLower,
    int nUpper);
```

### <a name="parameters"></a>Parameter

*nLower* und *nUpper*<br/>
Obere und untere Grenze für das Steuerelement. Für `SetRange`weder Grenzwert UD_MAXVAL größer bzw. kleiner als UD_MINVAL; darüber hinaus den Unterschied zwischen den zwei Grenzen nicht überschreiten UD_MAXVAL. `SetRange32` Schränkt die Grenzwerte; Verwenden Sie einen Integer.

### <a name="remarks"></a>Hinweise

Die Memberfunktion `SetRange32` legt den 32-Bit-Bereich für das Drehfeld-Steuerelement fest.

> [!NOTE]
>  Der Standardbereich für das Drehfeld hat das Maximum auf 0 (null) und das Minimum auf 100 festgelegt. Da der maximale Wert kleiner als der minimale Wert ist, klicken Sie auf den Pfeil nach oben die Position verringert, und klicken Sie auf den Pfeil nach unten, erhöhen sie. Verwendung `CSpinButtonCtrl::SetRange` zum Anpassen dieser Werte.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel CMNCTRL2](../../visual-cpp-samples.md)<br/>
[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CSliderCtrl-Klasse](../../mfc/reference/csliderctrl-class.md)
