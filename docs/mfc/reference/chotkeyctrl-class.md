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
ms.openlocfilehash: 9818c32a7779d646ca5a9485a1331dfa393408ba
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69506152"
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
|[CHotKeyCtrl::Create](#create)|Erstellt ein Hot Key-Steuerelement und fügt es `CHotKeyCtrl` an ein-Objekt an.|
|[CHotKeyCtrl::CreateEx](#createex)|Erstellt ein Hot Key-Steuerelement mit den angegebenen erweiterten Windows-Stilen und fügt `CHotKeyCtrl` es an ein-Objekt an.|
|[CHotKeyCtrl::GetHotKey](#gethotkey)|Ruft den Code des virtuellen Schlüssels und die Modifiziererflags eines Abkürzungs Schlüssels von einem Steuerelement für den Hot Key ab.|
|[CHotKeyCtrl::GetHotKeyName](#gethotkeyname)|Ruft den Schlüsselnamen im lokalen Zeichensatz ab, der einem Hot Key zugewiesen ist.|
|[CHotKeyCtrl::GetKeyName](#getkeyname)|Ruft den Schlüsselnamen im lokalen Zeichensatz ab, der dem angegebenen virtuellen Schlüsselcode zugewiesen ist.|
|[CHotKeyCtrl::SetHotKey](#sethotkey)|Legt die Tastenkombination für ein Hot Key-Steuerelement fest.|
|[CHotKeyCtrl::SetRules](#setrules)|Definiert die ungültigen Kombinationen und die standardmodifiziererkombination für ein Hot Key-Steuerelement.|

## <a name="remarks"></a>Hinweise

Ein "Hot Key Control" ist ein Fenster, mit dem der Benutzer eine Abkürzungs Taste erstellen kann. Eine "heiße Taste" ist eine Tastenkombination, die der Benutzer drücken kann, um eine Aktion schnell auszuführen. (Beispielsweise kann ein Benutzer einen Hot-Schlüssel erstellen, der ein bestimmtes Fenster aktiviert und an den Anfang der Z-Reihenfolge bringt.) Das Steuerelement "Hot Key" zeigt die Auswahl des Benutzers an und stellt sicher, dass der Benutzer eine gültige Tastenkombination auswählt.

Dieses Steuerelement (und damit `CHotKeyCtrl` auch die-Klasse) ist nur für Programme verfügbar, die unter Windows 95/98 und Windows NT, Version 3,51 und höher, ausgeführt werden.

Wenn der Benutzer eine Tastenkombination ausgewählt hat, kann die Anwendung die angegebene Tastenkombination aus dem-Steuerelement abrufen und die WM_SETHOTKEY-Nachricht verwenden, um den Hot-Schlüssel im System einzurichten. Sobald der Benutzer die Taste gedrückt drückt, empfängt das in der WM_SETHOTKEY-Nachricht angegebene Fenster in jedem Teil des Systems eine WM_SYSCOMMAND-Meldung, die SC_HOTKEY angibt. Diese Meldung aktiviert das Fenster, in dem Sie empfangen wird. Die Hot-Taste bleibt gültig, bis die Anwendung, die WM_SETHOTKEY aufgerufen hat, beendet wird.

Dieser Mechanismus unterscheidet sich von der Unterstützung für heiße Schlüssel, die von der WM_HOTKEY-Nachricht und den Windows [RegisterHotKey](/windows/win32/api/winuser/nf-winuser-registerhotkey) -und [unregisterhotkey](/windows/win32/api/winuser/nf-winuser-unregisterhotkey) -Funktionen abhängt.

Weitere Informationen zum Verwenden von `CHotKeyCtrl`finden Sie unter Steuer [Elemente](../../mfc/controls-mfc.md) und [Verwenden von CHotKeyCtrl](../../mfc/using-chotkeyctrl.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CHotKeyCtrl`

## <a name="requirements"></a>Anforderungen

**Header:** afxcmn.h

##  <a name="chotkeyctrl"></a>CHotKeyCtrl:: CHotKeyCtrl

Erstellt ein `CHotKeyCtrl`-Objekt.

```
CHotKeyCtrl();
```

##  <a name="create"></a>CHotKeyCtrl:: Create

Erstellt ein Hot Key-Steuerelement und fügt es `CHotKeyCtrl` an ein-Objekt an.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*dwStyle*<br/>
Gibt den Stil des Hot Key-Steuer Elements an. Wenden Sie eine beliebige Kombination von Steuerelement Stilen an. Weitere Informationen finden Sie unter [allgemeine Steuerelement Stile](/windows/win32/Controls/common-control-styles) in der Windows SDK.

*Rect*<br/>
Gibt die Größe und Position des Hot Key-Steuer Elements an. Dabei kann es sich entweder um ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt oder um eine [Rect-Struktur](/windows/win32/api/windef/ns-windef-rect)handeln.

*pParentWnd*<br/>
Gibt das übergeordnete Fenster des Hot Key-Steuer Elements an, in der Regel ein [CDialog](../../mfc/reference/cdialog-class.md). Er darf nicht NULL sein.

*nID*<br/>
Gibt die ID des Hot Key-Steuer Elements an.

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn die Initialisierung erfolgreich war. andernfalls 0.

### <a name="remarks"></a>Hinweise

Sie erstellen ein `CHotKeyCtrl` -Objekt in zwei Schritten. Zuerst wird der-Konstruktor aufgerufen und dann `Create`aufgerufen, wodurch das Steuerelement für den Hot Key erstellt und `CHotKeyCtrl` an das-Objekt angefügt wird.

Wenn Sie erweiterte Windows-Stile mit dem Steuerelement verwenden möchten, müssen Sie anstelle von `Create`den Befehl " [kreateex](#createex) " aufrufen.

##  <a name="createex"></a>CHotKeyCtrl:: kreateex

Rufen Sie diese Funktion auf, um ein-Steuerelement (ein untergeordnetes Fenster) `CHotKeyCtrl` zu erstellen und es dem-Objekt zuzuordnen.

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
Gibt den Stil des Hot Key-Steuer Elements an. Wenden Sie eine beliebige Kombination von Steuerelement Stilen an. Weitere Informationen finden Sie unter [allgemeine Steuerelement Stile](/windows/win32/Controls/common-control-styles) in der Windows SDK.

*Rect*<br/>
Ein Verweis auf eine [Rect](/previous-versions/dd162897\(v=vs.85\)) -Struktur, die die Größe und Position des zu erstellenden Fensters in Client Koordinaten von *pparser*beschreibt.

*pParentWnd*<br/>
Ein Zeiger auf das Fenster, das das übergeordnete Element des Steuer Elements ist.

*nID*<br/>
Die ID des untergeordneten Fensters des Steuer Elements.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Verwenden `CreateEx` Sie anstelle von [Create](#create) , um erweiterte Windows-Stile anzuwenden, die durch den erweiterten Windows-Stil **WS_EX_** angegeben werden.

##  <a name="gethotkey"></a>CHotKeyCtrl:: GetHotKey

Ruft den Code des virtuellen Schlüssels und die Modifiziererflags einer Tastenkombination von einem Steuerelement für den Hot Key ab.

```
DWORD GetHotKey() const;

void GetHotKey(
    WORD& wVirtualKeyCode,
    WORD& wModifiers) const;
```

### <a name="parameters"></a>Parameter

*wVirtualKeyCode*<br/>
vorgenommen Der Code für den virtuellen Schlüssel der Tastenkombination. Eine Liste der virtuellen Standardschlüssel Codes finden Sie unter Winuser. h.

*wModifiers*<br/>
vorgenommen Eine bitweise Kombination (or) von Flags, die die Modifizierertasten in der Tastenkombination angeben.

Die Modifiziererflags lauten wie folgt:

|Flag|Entsprechender Schlüssel|
|----------|-----------------------|
|HOTKEYF_ALT|ALT-TASTE|
|HOTKEYF_CONTROL|STRG-Taste|
|HOTKEYF_EXT|Erweiterter Schlüssel|
|HOTKEYF_SHIFT|Umschalttaste|

### <a name="return-value"></a>Rückgabewert

In der ersten überladenen Methode ein DWORD, das den Code und die Modifiziererflags des virtuellen Schlüssels enthält. Das nieder wertige Byte des nieder wertigen Worts enthält den Code des virtuellen Schlüssels, das hochwertige Byte des nieder wertigen Worts enthält die Modifiziererflags, und das höchst wertige Wort ist 0 (null).

### <a name="remarks"></a>Hinweise

Der virtuelle Schlüsselcode und die Modifizierertasten definieren die Tastenkombination.

##  <a name="gethotkeyname"></a>CHotKeyCtrl:: gethotkeyname

Mit dieser Member-Funktion können Sie den lokalisierten Namen des Abkürzungs Schlüssels abrufen.

```
CString GetHotKeyName() const;
```

### <a name="return-value"></a>Rückgabewert

Der lokalisierte Name der aktuell ausgewählten Hot-Taste. Wenn keine "Hot"-Taste ausgewählt `GetHotKeyName` ist, wird eine leere Zeichenfolge zurückgegeben.

### <a name="remarks"></a>Hinweise

Der Name, der von dieser Member-Funktion zurückgegeben wird, stammt aus dem Tastaturtreiber. Sie können einen nicht lokalisierten Tastaturtreiber in einer lokalisierten Version von Windows installieren und umgekehrt.

##  <a name="getkeyname"></a>CHotKeyCtrl:: getkeyname

Mit dieser Member-Funktion können Sie den lokalisierten Namen des Schlüssels abrufen, der einem angegebenen virtuellen Schlüsselcode zugewiesen ist.

```
static CString GetKeyName(
    UINT vk,
    BOOL fExtended);
```

### <a name="parameters"></a>Parameter

*vk*<br/>
Der virtuelle Schlüsselcode.

*fExtended*<br/>
Wenn es sich bei dem virtuellen Schlüsselcode um einen erweiterten Schlüssel handelt, gilt: andernfalls false.

### <a name="return-value"></a>Rückgabewert

Der lokalisierte Name des Schlüssels, der durch den *VK* -Parameter angegeben wird. Wenn der Schlüssel über keinen zugeordneten Namen `GetKeyName` verfügt, wird eine leere Zeichenfolge zurückgegeben.

### <a name="remarks"></a>Hinweise

Der Schlüssel Name, der von dieser Funktion zurückgegeben wird, stammt aus dem Tastaturtreiber, sodass Sie einen nicht lokalisierten Tastaturtreiber in einer lokalisierten Version von Windows installieren können und umgekehrt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCControlLadenDialog#69](../../mfc/codesnippet/cpp/chotkeyctrl-class_1.cpp)]

##  <a name="sethotkey"></a>CHotKeyCtrl:: abkthotkey

Legt die Tastenkombination für ein Hot Key-Steuerelement fest.

```
void SetHotKey(
    WORD wVirtualKeyCode,
    WORD wModifiers);
```

### <a name="parameters"></a>Parameter

*wVirtualKeyCode*<br/>
in Der Code für den virtuellen Schlüssel der Tastenkombination. Eine Liste der virtuellen Standardschlüssel Codes finden Sie unter Winuser. h.

*wModifiers*<br/>
in Eine bitweise Kombination (or) von Flags, die die Modifizierertasten in der Tastenkombination angeben.

Die Modifiziererflags lauten wie folgt:

|Flag|Entsprechender Schlüssel|
|----------|-----------------------|
|HOTKEYF_ALT|ALT-TASTE|
|HOTKEYF_CONTROL|STRG-Taste|
|HOTKEYF_EXT|Erweiterter Schlüssel|
|HOTKEYF_SHIFT|Umschalttaste|

### <a name="remarks"></a>Hinweise

Der virtuelle Schlüsselcode und die Modifizierertasten definieren die Tastenkombination.

##  <a name="setrules"></a>CHotKeyCtrl:: ttrules

Mit dieser Funktion können Sie die ungültigen Kombinationen und die standardmodifiziererkombination für ein Hot Key-Steuerelement definieren.

```
void SetRules(
    WORD wInvalidComb,
    WORD wModifiers);
```

### <a name="parameters"></a>Parameter

*wInvalidComb*<br/>
Ein Array von Flags, das ungültige Tastenkombinationen angibt. Dabei kann es sich um eine Kombination der folgenden Werte handeln:

- HKCOMB_A ALT

- HKCOMB_C CTRL

- HKCOMB_CA STRG + ALT

- HKCOMB_NONE nicht geänderte Schlüssel

- HKCOMB_S SHIFT

- HKCOMB_SA UMSCHALT + ALT

- HKCOMB_SC UMSCHALT + STRG

- HKCOMB_SCA UMSCHALT + STRG + ALT

*wModifiers*<br/>
Ein Array von Flags, das die zu verwendende Tastenkombination angibt, wenn der Benutzer eine ungültige Kombination eingibt. Weitere Informationen zu den Modifiziererflags finden Sie unter [GetHotKey](#gethotkey).

### <a name="remarks"></a>Hinweise

Wenn ein Benutzer eine ungültige Tastenkombination eingibt, die durch in *winvalidcomb*angegebene Flags definiert ist, verwendet das System den or-Operator, um die Schlüssel, die vom Benutzer eingegeben wurden, mit den in *wmodifiers*angegebenen Flags zu kombinieren. Die resultierende Tastenkombination wird in eine Zeichenfolge konvertiert und dann im Steuerelement "Hot Key" angezeigt.

## <a name="see-also"></a>Siehe auch

[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
