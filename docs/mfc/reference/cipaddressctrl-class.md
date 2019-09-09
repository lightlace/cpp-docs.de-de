---
title: Cipaddressctrl-Klasse
ms.date: 11/04/2016
f1_keywords:
- CIPAddressCtrl
- AFXCMN/CIPAddressCtrl
- AFXCMN/CIPAddressCtrl::CIPAddressCtrl
- AFXCMN/CIPAddressCtrl::ClearAddress
- AFXCMN/CIPAddressCtrl::Create
- AFXCMN/CIPAddressCtrl::CreateEx
- AFXCMN/CIPAddressCtrl::GetAddress
- AFXCMN/CIPAddressCtrl::IsBlank
- AFXCMN/CIPAddressCtrl::SetAddress
- AFXCMN/CIPAddressCtrl::SetFieldFocus
- AFXCMN/CIPAddressCtrl::SetFieldRange
helpviewer_keywords:
- CIPAddressCtrl [MFC], CIPAddressCtrl
- CIPAddressCtrl [MFC], ClearAddress
- CIPAddressCtrl [MFC], Create
- CIPAddressCtrl [MFC], CreateEx
- CIPAddressCtrl [MFC], GetAddress
- CIPAddressCtrl [MFC], IsBlank
- CIPAddressCtrl [MFC], SetAddress
- CIPAddressCtrl [MFC], SetFieldFocus
- CIPAddressCtrl [MFC], SetFieldRange
ms.assetid: 9764d2f4-cb14-4ba8-b799-7f57a55a47c6
ms.openlocfilehash: fe8e3109b110c27ab32dc1a4f9a132f1e1c18638
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69505818"
---
# <a name="cipaddressctrl-class"></a>Cipaddressctrl-Klasse

Stellt die Funktionalität des allgemeinen Windows-Steuerelements für IP-Adressen bereit.

## <a name="syntax"></a>Syntax

```
class CIPAddressCtrl : public CWnd
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CIPAddressCtrl::CIPAddressCtrl](#cipaddressctrl)|Erstellt ein `CIPAddressCtrl`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CIPAddressCtrl::ClearAddress](#clearaddress)|Löscht den Inhalt des Steuer Elements für die IP-Adresse.|
|[CIPAddressCtrl::Create](#create)|Erstellt ein IP-Adress Steuerelement und fügt es `CIPAddressCtrl` an ein-Objekt an.|
|[CIPAddressCtrl::CreateEx](#createex)|Erstellt ein IP-Adress Steuerelement mit den angegebenen erweiterten Windows-Stilen und fügt `CIPAddressCtrl` es an ein-Objekt an.|
|[CIPAddressCtrl::GetAddress](#getaddress)|Ruft die Adress Werte für alle vier Felder im IP-Adress Steuerelement ab.|
|[CIPAddressCtrl::IsBlank](#isblank)|Bestimmt, ob alle Felder im IP-Adress Steuerelement leer sind.|
|[CIPAddressCtrl::SetAddress](#setaddress)|Legt die Adress Werte für alle vier Felder im IP-Adress Steuerelement fest.|
|[CIPAddressCtrl::SetFieldFocus](#setfieldfocus)|Legt den Tastaturfokus auf das angegebene Feld im IP-Adress Steuerelement fest.|
|[CIPAddressCtrl::SetFieldRange](#setfieldrange)|Legt den Bereich im angegebenen Feld im IP-Adress Steuerelement fest.|

## <a name="remarks"></a>Hinweise

Ein IP-Adress Steuerelement, ein ähnliches Steuerelement wie ein Bearbeitungs Steuerelement, ermöglicht es Ihnen, eine numerische Adresse im IP-Format (Internet Protocol) einzugeben und zu bearbeiten.

Dieses Steuerelement (und damit `CIPAddressCtrl` auch die-Klasse) ist nur für Programme verfügbar, die unter Microsoft Internet Explorer 4,0 oder höher ausgeführt werden. Sie sind auch in zukünftigen Versionen von Windows und Windows NT verfügbar.

Weitere allgemeine Informationen zum IP-Adress Steuerelement finden Sie unter [IP-Adress Steuerelemente](/windows/win32/Controls/ip-address-controls) im Windows SDK.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CIPAddressCtrl`

## <a name="requirements"></a>Anforderungen

**Header:** afxcmn.h

##  <a name="cipaddressctrl"></a>Cipaddressctrl:: cipaddressctrl

Erstellt ein `CIPAddressCtrl`-Objekt.

```
CIPAddressCtrl();
```

##  <a name="clearaddress"></a>Cipaddressctrl:: clearaddress

Löscht den Inhalt des Steuer Elements für die IP-Adresse.

```
void ClearAddress();
```

### <a name="remarks"></a>Hinweise

Diese Member-Funktion implementiert das Verhalten der Win32-Nachricht [IPM_CLEARADDRESS](/windows/win32/Controls/ipm-clearaddress), wie im Windows SDK beschrieben.

##  <a name="create"></a>Cipaddressctrl:: Create

Erstellt ein IP-Adress Steuerelement und fügt es `CIPAddressCtrl` an ein-Objekt an.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*dwStyle*<br/>
Der Stil des IP-Adress Steuer Elements. Eine Kombination von Fenster Stilen anwenden. Sie müssen den WS_CHILD-Stil einschließen, da das Steuerelement ein untergeordnetes Fenster sein muss. Eine Liste der Windows- [Stile finden Sie unter in](/windows/win32/api/winuser/nf-winuser-createwindoww) der Windows SDK.

*Rect*<br/>
Ein Verweis auf die Größe und Position des IP-Adress Steuer Elements. Dabei kann es sich entweder um ein [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt oder um eine [Rect](/previous-versions/dd162897\(v=vs.85\)) -Struktur handeln.

*pParentWnd*<br/>
Ein Zeiger auf das übergeordnete Fenster des IP-Adress Steuer Elements. Er darf nicht NULL sein.

*nID*<br/>
Die ID des IP-Adress Steuer Elements.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Initialisierung erfolgreich war. andernfalls 0.

### <a name="remarks"></a>Hinweise

Sie erstellen ein `CIPAddressCtrl` -Objekt in zwei Schritten.

1. Nennen Sie den-Konstruktor, der `CIPAddressCtrl` das-Objekt erstellt.

1. Ruft `Create`auf, wodurch das IP-Adress Steuerelement erstellt wird.

Wenn Sie erweiterte Windows-Stile mit dem Steuerelement verwenden möchten, müssen Sie anstelle von `Create`den Befehl " [kreateex](#createex) " aufrufen.

##  <a name="createex"></a>Cipaddressctrl:: kreateex

Rufen Sie diese Funktion auf, um ein-Steuerelement (ein untergeordnetes Fenster) `CIPAddressCtrl` zu erstellen und es dem-Objekt zuzuordnen.

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
Der Stil des IP-Adress Steuer Elements. Eine Kombination von Fenster Stilen anwenden. Sie müssen den WS_CHILD-Stil einschließen, da das Steuerelement ein untergeordnetes Fenster sein muss. Eine Liste der Windows- [Stile finden Sie unter in](/windows/win32/api/winuser/nf-winuser-createwindoww) der Windows SDK.

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

##  <a name="getaddress"></a>Cipaddressctrl:: GetAddress

Ruft die Adress Werte für alle vier Felder im IP-Adress Steuerelement ab.

```
int GetAddress(
    BYTE& nField0,
    BYTE& nField1,
    BYTE& nField2,
    BYTE& nField3);

int GetAddress(DWORD& dwAddress);
```

### <a name="parameters"></a>Parameter

*nField0*<br/>
Ein Verweis auf den Wert des Felds 0 aus einer gepackten IP-Adresse.

*nField1*<br/>
Ein Verweis auf den Wert Feld 1 von einer gepackten IP-Adresse.

*nField2*<br/>
Ein Verweis auf den Wert des Felds 2 aus einer gepackten IP-Adresse.

*nField3*<br/>
Ein Verweis auf den Wert des Felds 3 aus einer gepackten IP-Adresse.

*dwAddress*<br/>
Ein Verweis auf die Adresse eines DWORD-Werts, der die IP-Adresse empfängt. Siehe **Hinweise** für eine Tabelle, die zeigt, wie *dwaddress* ausgefüllt ist.

### <a name="return-value"></a>Rückgabewert

Die Anzahl der nicht leeren Felder im IP-Adress Steuerelement.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion implementiert das Verhalten der Win32-Nachricht [IPM_GETADDRESS](/windows/win32/Controls/ipm-getaddress), wie im Windows SDK beschrieben. Im ersten Prototyp oben füllen die Zahlen in den Feldern 0 bis 3 des Steuer Elements, von links nach rechts, die vier Parameter auf. Im zweiten Prototyp oben wird *dwaddress* wie folgt aufgefüllt.

|Feld|Bits, die den Feldwert enthalten|
|-----------|-------------------------------------|
|0|24 bis 31|
|1|16 bis 23|
|2|8 bis 15|
|3|0 bis 7|

##  <a name="isblank"></a>Cipaddressctrl:: isblank

Bestimmt, ob alle Felder im IP-Adress Steuerelement leer sind.

```
BOOL IsBlank() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich 0 (null), wenn alle IP-Adress Kontroll Felder leer sind. andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion implementiert das Verhalten der Win32-Nachricht [IPM_ISBLANK](/windows/win32/Controls/ipm-isblank), wie im Windows SDK beschrieben.

##  <a name="setaddress"></a>Cipaddressctrl:: setAddress

Legt die Adress Werte für alle vier Felder im IP-Adress Steuerelement fest.

```
void SetAddress(
    BYTE nField0,
    BYTE nField1,
    BYTE nField2,
    BYTE nField3);

void SetAddress(DWORD dwAddress);
```

### <a name="parameters"></a>Parameter

*nField0*<br/>
Der Wert von Feld 0 aus einer gepackten IP-Adresse.

*nField1*<br/>
Der Wert für Feld 1 aus einer gepackten IP-Adresse.

*nField2*<br/>
Der Wert von Feld 2 aus einer gepackten IP-Adresse.

*nField3*<br/>
Der Wert von Feld 3 aus einer gepackten IP-Adresse.

*dwAddress*<br/>
Ein DWORD-Wert, der die neue IP-Adresse enthält. Siehe **Hinweise** für eine Tabelle, die zeigt, wie der DWORD-Wert aufgefüllt wird.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion implementiert das Verhalten der Win32-Nachricht [IPM_SETADDRESS](/windows/win32/Controls/ipm-setaddress), wie im Windows SDK beschrieben. Im ersten Prototyp oben füllen die Zahlen in den Feldern 0 bis 3 des Steuer Elements, von links nach rechts, die vier Parameter auf. Im zweiten Prototyp oben wird *dwaddress* wie folgt aufgefüllt.

|Feld|Bits, die den Feldwert enthalten|
|-----------|-------------------------------------|
|0|24 bis 31|
|1|16 bis 23|
|2|8 bis 15|
|3|0 bis 7|

##  <a name="setfieldfocus"></a>Cipaddressctrl:: setfieldfocus

Legt den Tastaturfokus auf das angegebene Feld im IP-Adress Steuerelement fest.

```
void SetFieldFocus(WORD nField);
```

### <a name="parameters"></a>Parameter

*nField*<br/>
NULL basierter Feld Index, auf den der Fokus festgelegt werden soll. Wenn dieser Wert größer als die Anzahl der Felder ist, wird der Fokus auf das erste leere Feld festgelegt. Wenn alle Felder nicht leer sind, wird der Fokus auf das erste Feld festgelegt.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion implementiert das Verhalten der Win32-Nachricht [IPM_SETFOCUS](/windows/win32/Controls/ipm-setfocus), wie im Windows SDK beschrieben.

##  <a name="setfieldrange"></a>Cipaddressctrl:: setfieldrange

Legt den Bereich im angegebenen Feld im IP-Adress Steuerelement fest.

```
void SetFieldRange(
    int nField,
    BYTE nLower,
    BYTE nUpper);
```

### <a name="parameters"></a>Parameter

*nField*<br/>
NULL basierter Feld Index, auf den der Bereich angewendet wird.

*nLower*<br/>
Ein Verweis auf eine Ganzzahl, die die untere Grenze des angegebenen Felds in diesem IP-Adress Steuerelement empfängt.

*nUpper*<br/>
Ein Verweis auf eine Ganzzahl, die die Obergrenze des angegebenen Felds in diesem IP-Adress Steuerelement empfängt.

### <a name="remarks"></a>Hinweise

Diese Member-Funktion implementiert das Verhalten der Win32-Nachricht [IPM_SETRANGE](/windows/win32/Controls/ipm-setrange), wie im Windows SDK beschrieben. Verwenden Sie die beiden Parameter *nlower* und *nupper,* um die unteren und oberen Begrenzungen des Felds anzugeben, anstelle des *Wrange* -Parameters, der mit der Win32-Nachricht verwendet wird.

## <a name="see-also"></a>Siehe auch

[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
