---
title: CHotKeyCtrl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CHotKeyCtrl
- AFXCMN/CHotKeyCtrl
- AFXCMN/CHotKeyCtrl::CHotKeyCtrl
- AFXCMN/CHotKeyCtrl::Create
- AFXCMN/CHotKeyCtrl::CreateEx
- AFXCMN/CHotKeyCtrl::GetHotKey
- AFXCMN/CHotKeyCtrl::GetHotKeyName
- AFXCMN/CHotKeyCtrl::GetKeyName
- AFXCMN/CHotKeyCtrl::SetHotKey
- AFXCMN/CHotKeyCtrl::SetRules
helpviewer_keywords:
- CHotKeyCtrl [MFC], CHotKeyCtrl
- CHotKeyCtrl [MFC], Create
- CHotKeyCtrl [MFC], CreateEx
- CHotKeyCtrl [MFC], GetHotKey
- CHotKeyCtrl [MFC], GetHotKeyName
- CHotKeyCtrl [MFC], GetKeyName
- CHotKeyCtrl [MFC], SetHotKey
- CHotKeyCtrl [MFC], SetRules
ms.assetid: 896f9766-0718-4f58-aab2-20325e118ca6
ms.openlocfilehash: f7887b1c9ddaf9d51da584df371acbed6726643b
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57291300"
---
# <a name="chotkeyctrl-class"></a>CHotKeyCtrl-Klasse

Stellt die Funktionalität des allgemeinen Windows-Abkürzungstasten-Steuerelements bereit.

## <a name="syntax"></a>Syntax

```
class CHotKeyCtrl : public CWnd
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CHotKeyCtrl::CHotKeyCtrl](#chotkeyctrl)|Erstellt ein `CHotKeyCtrl`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CHotKeyCtrl::Create](#create)|Erstellt ein Abkürzungstasten-Steuerelements und fügt sie an einer `CHotKeyCtrl` Objekt.|
|[CHotKeyCtrl::CreateEx](#createex)|Erstellt ein Abkürzungstasten-Steuerelements mit der angegebenen erweiterten Windows-Stile und fügt sie an einer `CHotKeyCtrl` Objekt.|
|[CHotKeyCtrl::GetHotKey](#gethotkey)|Ruft die virtuellen Schlüssel und Modifiziererflags Flags auf, der einen Schlüssel für den direkten aus eines Abkürzungstasten-Steuerelements ab.|
|[CHotKeyCtrl::GetHotKeyName](#gethotkeyname)|Ruft den Schlüsselnamen an, in der lokalen Zeichensatz ausgewählt werden können, die eine Abkürzungstaste zugewiesen.|
|[CHotKeyCtrl::GetKeyName](#getkeyname)|Ruft den Schlüsselnamen an, in der lokalen Zeichensatz ausgewählt werden können, die den angegebenen virtueller Tastencode zugewiesen.|
|[CHotKeyCtrl::SetHotKey](#sethotkey)|Legt fest, die "Hot" Tastenkombination für eines Abkürzungstasten-Steuerelements.|
|[CHotKeyCtrl::SetRules](#setrules)|Definiert die ungültigen Kombinationen und die Modifizierer Standardkombination für eines Abkürzungstasten-Steuerelements.|

## <a name="remarks"></a>Hinweise

Eine "Abkürzungstasten-Steuerelements" ist ein Fenster, das dem Benutzer ermöglicht, einen Schlüssel "Hot" zu erstellen. Eine "Abkürzungstaste" ist eine Tastenkombination, die der Benutzer drücken kann, um eine Aktion schnell ausgeführt. (Z. B. kann ein Benutzer eine Abkürzungstaste, die ein bestimmtes Fenster aktiviert und schaltet sie am Anfang der Z-Reihenfolge erstellen.) Die Abkürzungstasten-Steuerelements zeigt Optionen an des Benutzers, und es wird sichergestellt, dass der Benutzer eine gültige Tastenkombination gewählt.

Dieses Steuerelement (und somit die `CHotKeyCtrl` Klasse) ist nur für Programme, die unter Windows 95/98 und Windows NT, Version 3.51 und höher.

Wenn der Benutzer eine Tastenkombination ausgewählt hat, kann die Anwendung die angegebene Tastenkombination aus dem Steuerelement abzurufen und verwenden die WM_SETHOTKEY-Nachricht im System den Schlüssel für den direkten einrichten. Wenn der Benutzer die Abkürzungstaste danach von einem beliebigen Teil des Systems drückt empfängt das Fenster, in der Meldung WM_SETHOTKEY angegebene eine Angabe SC_HOTKEY WM_SYSCOMMAND-Nachricht. Diese Nachricht wird das Fenster, das er empfängt aktiviert. Die Abkürzungstaste bleibt gültig, bis die Anwendung, die WM_SETHOTKEY beendet aufgerufen wird.

Dieser Mechanismus unterscheidet sich von "Hot" Key-Unterstützung, von denen abhängig von der WM_HOTKEY-Nachricht und die Windows [RegisterHotKey](/windows/desktop/api/winuser/nf-winuser-registerhotkey) und [UnregisterHotKey](/windows/desktop/api/winuser/nf-winuser-unregisterhotkey) Funktionen.

Weitere Informationen zur Verwendung von `CHotKeyCtrl`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md) und [Verwenden von CHotKeyCtrl](../../mfc/using-chotkeyctrl.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CHotKeyCtrl`

## <a name="requirements"></a>Anforderungen

**Header:** afxcmn.h

##  <a name="chotkeyctrl"></a>  CHotKeyCtrl::CHotKeyCtrl

Erstellt ein `CHotKeyCtrl`-Objekt.

```
CHotKeyCtrl();
```

##  <a name="create"></a>  CHotKeyCtrl::Create

Erstellt ein Abkürzungstasten-Steuerelements und fügt sie an einer `CHotKeyCtrl` Objekt.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*dwStyle*<br/>
Gibt die Abkürzungstasten-Steuerelements die Art an. Wenden Sie eine beliebige Kombination der Stile von Listensteuerelementen. Finden Sie unter [allgemeinen Stile von Listensteuerelementen](/windows/desktop/Controls/common-control-styles) im Windows SDK für Weitere Informationen.

*rect*<br/>
Gibt an, die Abkürzungstasten-Steuerelements die Größe und Position. Es kann sein, entweder eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder ein [RECT-Struktur](/windows/desktop/api/windef/ns-windef-tagrect).

*pParentWnd*<br/>
Gibt an, die Abkürzungstasten-Steuerelements des übergeordneten Fensters, in der Regel eine [CDialog](../../mfc/reference/cdialog-class.md). Es darf nicht NULL sein.

*nID*<br/>
Gibt die Abkürzungstasten-Steuerelement ID an.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Initialisierung erfolgreich war; andernfalls 0.

### <a name="remarks"></a>Hinweise

Sie erstellen eine `CHotKeyCtrl` Objekt in zwei Schritten. Zunächst rufen Sie den Konstruktor, und rufen Sie anschließend `Create`, die die Abkürzungstasten-Steuerelements erstellt und fügt es der `CHotKeyCtrl` Objekt.

Wenn Sie erweiterte Fensterstile mit dem Steuerelement verwenden möchten, rufen Sie [CreateEx](#createex) anstelle von `Create`.

##  <a name="createex"></a>  CHotKeyCtrl::CreateEx

Mit dieser Funktion wird zum Erstellen eines Steuerelements (ein untergeordnetes Fenster), und ordnen sie die `CHotKeyCtrl` Objekt.

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
Gibt die Abkürzungstasten-Steuerelements die Art an. Wenden Sie eine beliebige Kombination der Stile von Listensteuerelementen. Weitere Informationen finden Sie unter [allgemeinen Stile von Listensteuerelementen](/windows/desktop/Controls/common-control-styles) im Windows SDK.

*rect*<br/>
Ein Verweis auf eine [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die die Größe und Position des Fensters erstellt werden, in Clientkoordinaten des beschreibt *pParentWnd*.

*pParentWnd*<br/>
Ein Zeiger auf das Fenster, das übergeordnete Element des Steuerelements ist.

*nID*<br/>
Der ID des Steuerelements untergeordneten Fensters mit.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Verwendung `CreateEx` anstelle von [erstellen](#create) anzuwendende Erweiterte Windows-Stile, angegeben durch den Wert der Windows-erweiterten Stil **WS_EX_**.

##  <a name="gethotkey"></a>  CHotKeyCtrl::GetHotKey

Ruft die virtuellen Schlüssel und Modifiziererflags Flags auf, der eine Tastenkombination aus eines Abkürzungstasten-Steuerelements ab.

```
DWORD GetHotKey() const;

void GetHotKey(
    WORD& wVirtualKeyCode,
    WORD& wModifiers) const;
```

### <a name="parameters"></a>Parameter

*wVirtualKeyCode*<br/>
[out] Virtuellem Tastencode der Tastenkombination. Eine Liste der standardmäßige virtuelle Tastencodes finden Sie unter "Winuser.h".

*wModifiers*<br/>
[out] Eine bitweise Kombination (OR) von Flags, die die Zusatztasten in die Tastenkombination angeben.

Die Modifiziererflags lauten wie folgt aus:

|Flag|Entsprechenden Schlüssel|
|----------|-----------------------|
|HOTKEYF_ALT|ALT-TASTE|
|HOTKEYF_CONTROL|STRG-Taste|
|HOTKEYF_EXT|Erweiterte Schlüssel|
|HOTKEYF_SHIFT|UMSCHALT-Taste|

### <a name="return-value"></a>Rückgabewert

Überladen in der ersten Methode, ein DWORD, das die virtuellen Schlüssel und Modifiziererflags Flags enthält. Das niedrige Byte das niederwertige Wort enthält den virtuellen Tastencode, das höherwertige Byte das niederwertige Wort enthält die Modifiziererflags und das höherwertige Wort ist 0 (null).

### <a name="remarks"></a>Hinweise

Definieren Sie die Tastenkombination ein, den virtueller Tastencode und der Zusatztasten, die zusammen.

##  <a name="gethotkeyname"></a>  CHotKeyCtrl::GetHotKeyName

Rufen Sie diese Memberfunktion um den lokalisierten Namen des Schlüssels "Hot" zu erhalten.

```
CString GetHotKeyName() const;
```

### <a name="return-value"></a>Rückgabewert

Der lokalisierte Name des aktuell ausgewählten aktiven Schlüssels. Es ist kein Schlüssel für den ausgewählten direkten, `GetHotKeyName` eine leere Zeichenfolge zurückgegeben.

### <a name="remarks"></a>Hinweise

Der Name, die von dieser Memberfunktion zurückgegeben wird von der Tastaturtreiber. Sie können einen nicht lokalisierten Tastaturtreiber installieren, in einer lokalisierten Version von Windows, und umgekehrt.

##  <a name="getkeyname"></a>  CHotKeyCtrl::GetKeyName

Rufen Sie diese Memberfunktion zum Abrufen des lokalisierten Namens des Schlüssels, die einem angegebenen virtuellem Tastencode zugewiesen.

```
static CString GetKeyName(
    UINT vk,
    BOOL fExtended);
```

### <a name="parameters"></a>Parameter

*vk*<br/>
Den virtueller Tastencode.

*fExtended*<br/>
Wenn der virtuelle Tastencode einen erweiterten-Schlüssel "true" ist. andernfalls "false".

### <a name="return-value"></a>Rückgabewert

Der lokalisierte Name des Schlüssels innerhalb der *Vk* Parameter. Wenn der Schlüssel keinen zugeordneten Namen besitzt, `GetKeyName` eine leere Zeichenfolge zurückgegeben.

### <a name="remarks"></a>Hinweise

Den Namen des Schlüssels, der diese Funktion gibt auf der Tastaturtreiber stammen, damit in einer lokalisierten Version von Windows, einen nicht lokalisierten Tastaturtreiber installiert werden kann und umgekehrt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCControlLadenDialog#69](../../mfc/codesnippet/cpp/chotkeyctrl-class_1.cpp)]

##  <a name="sethotkey"></a>  CHotKeyCtrl::SetHotKey

Legt die Tastenkombination für eines Abkürzungstasten-Steuerelements fest.

```
void SetHotKey(
    WORD wVirtualKeyCode,
    WORD wModifiers);
```

### <a name="parameters"></a>Parameter

*wVirtualKeyCode*<br/>
[in] Virtuellem Tastencode der Tastenkombination. Eine Liste der standardmäßige virtuelle Tastencodes finden Sie unter "Winuser.h".

*wModifiers*<br/>
[in] Eine bitweise Kombination (OR) von Flags, die die Zusatztasten in die Tastenkombination angeben.

Die Modifiziererflags lauten wie folgt aus:

|Flag|Entsprechenden Schlüssel|
|----------|-----------------------|
|HOTKEYF_ALT|ALT-TASTE|
|HOTKEYF_CONTROL|STRG-Taste|
|HOTKEYF_EXT|Erweiterte Schlüssel|
|HOTKEYF_SHIFT|UMSCHALT-Taste|

### <a name="remarks"></a>Hinweise

Definieren Sie die Tastenkombination ein, den virtueller Tastencode und der Zusatztasten, die zusammen.

##  <a name="setrules"></a>  CHotKeyCtrl::SetRules

Rufen Sie diese Funktion, um die ungültigen Kombinationen und die Modifizierer Standardkombination für eines Abkürzungstasten-Steuerelements zu definieren.

```
void SetRules(
    WORD wInvalidComb,
    WORD wModifiers);
```

### <a name="parameters"></a>Parameter

*wInvalidComb*<br/>
Ein Array von Flags, die ungültige Schlüsselkombinationen angibt. Sie können eine Kombination der folgenden Werte sein:

- HKCOMB_A ALT

- HKCOMB_C CTRL

- HKCOMB_CA CTRL+ALT

- Unveränderte HKCOMB_NONE Schlüssel

- HKCOMB_S UMSCHALT

- HKCOMB_SA UMSCHALT + ALT

- HKCOMB_SC UMSCHALT + STRG

- HKCOMB_SCA UMSCHALT + STRG + ALT

*wModifiers*<br/>
Ein Array von Flags, der angibt, die Tastenkombination verwendet werden, wenn der Benutzer eine ungültige Kombination eingibt. Weitere Informationen zu den Modifiziererflags, finden Sie unter [GetHotKey](#gethotkey).

### <a name="remarks"></a>Hinweise

Wenn der Benutzer eine ungültige Tastenkombination eingibt, gemäß der Flags, die im angegebenen *wInvalidComb*, das System verwendet den OR-Operator, die mit den Flags, die im angegebenen vom Benutzer eingegebenen Schlüssel kombinieren *wModifiers*. Die resultierende Tastenkombination wird in eine Zeichenfolge konvertiert und dann in die Abkürzungstasten-Steuerelements angezeigt.

## <a name="see-also"></a>Siehe auch

[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
