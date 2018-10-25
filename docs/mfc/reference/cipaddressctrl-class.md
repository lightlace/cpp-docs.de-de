---
title: CIPAddressCtrl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b6699e0b8a37bba0505e9f6dde3d457f2230bd2
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055020"
---
# <a name="cipaddressctrl-class"></a>CIPAddressCtrl-Klasse

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
|[CIPAddressCtrl::ClearAddress](#clearaddress)|Löscht den Inhalt des Steuerelements IP-Adresse.|
|[CIPAddressCtrl::Create](#create)|Erstellt ein Steuerelement der IP-Adresse und fügt sie an einer `CIPAddressCtrl` Objekt.|
|[CIPAddressCtrl::CreateEx](#createex)|Erstellt ein Steuerelement für die IP-Adresse mit der angegebenen erweiterten Windows-Stile und fügt sie an einer `CIPAddressCtrl` Objekt.|
|[CIPAddressCtrl::GetAddress](#getaddress)|Ruft die Adresswerte für alle vier Felder im IP-Adresse-Steuerelement.|
|[CIPAddressCtrl::IsBlank](#isblank)|Bestimmt, ob alle Felder in die IP-Adressensteuerelement leer sind.|
|[CIPAddressCtrl::SetAddress](#setaddress)|Legt die Adresswerte für alle vier Felder in die IP-Adressensteuerelement fest.|
|[CIPAddressCtrl::SetFieldFocus](#setfieldfocus)|Legt den Tastaturfokus auf das angegebene Feld in die IP-Adressensteuerelement fest.|
|[CIPAddressCtrl::SetFieldRange](#setfieldrange)|Legt den Bereich in das angegebene Feld in die IP-Adressensteuerelement fest.|

## <a name="remarks"></a>Hinweise

Ein Steuerelement ein Steuerelement, das ein Bearbeitungssteuerelement, ähnlich wie IP-Adresse können Sie eine numerische Adresse im Format der IP (Internet Protocol) zu geben.

Dieses Steuerelement (und somit die `CIPAddressCtrl` Klasse) ist nur für Programme, die ausgeführt wird, in Microsoft Internet Explorer 4.0 und höher verfügbar. Sie werden auch unter zukünftigen Versionen von Windows und Windows NT verfügbar sein.

Weitere allgemeine Informationen zu den IP-Adressensteuerelement, finden Sie unter [IP-Adresse Steuerelemente](/windows/desktop/Controls/ip-address-controls) im Windows SDK.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CIPAddressCtrl`

## <a name="requirements"></a>Anforderungen

**Header:** afxcmn.h

##  <a name="cipaddressctrl"></a>  CIPAddressCtrl::CIPAddressCtrl

Erstellt ein `CIPAddressCtrl`-Objekt.

```
CIPAddressCtrl();
```

##  <a name="clearaddress"></a>  CIPAddressCtrl::ClearAddress

Löscht den Inhalt des Steuerelements IP-Adresse.

```
void ClearAddress();
```

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [IPM_CLEARADDRESS](/windows/desktop/Controls/ipm-clearaddress), wie im Windows SDK beschrieben.

##  <a name="create"></a>  CIPAddressCtrl::Create

Erstellt ein Steuerelement der IP-Adresse und fügt sie an einer `CIPAddressCtrl` Objekt.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*dwStyle*<br/>
Format des IP-Adresse-Steuerelements. Wenden Sie eine Kombination von Window-Stile. Sie müssen das Format WS_CHILD einschließen, da das Steuerelement ein untergeordnetes Fenster sein muss. Finden Sie unter [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) im Windows SDK für eine Liste der Windows-Formate.

*Rect*<br/>
Ein Verweis auf die IP-Adresse des Steuerelements Größe und Position. Es kann sein, entweder eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder ein [RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur.

*pParentWnd*<br/>
Ein Zeiger auf die IP-Adresse des Steuerelements übergeordnete Fenster. Es darf nicht NULL sein.

*nID*<br/>
Die IP-Adresse-Steuerelements.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Initialisierung erfolgreich war; andernfalls 0.

### <a name="remarks"></a>Hinweise

Sie erstellen eine `CIPAddressCtrl` Objekt in zwei Schritten.

1. Rufen Sie den Konstruktor, der erstellt das `CIPAddressCtrl` Objekt.

1. Rufen Sie `Create`, die IP-Adressensteuerelement erstellt.

Wenn Sie erweiterte Fensterstile mit dem Steuerelement verwenden möchten, rufen Sie [CreateEx](#createex) anstelle von `Create`.

##  <a name="createex"></a>  CIPAddressCtrl::CreateEx

Mit dieser Funktion wird zum Erstellen eines Steuerelements (ein untergeordnetes Fenster), und ordnen sie die `CIPAddressCtrl` Objekt.

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
Format des IP-Adresse-Steuerelements. Wenden Sie eine Kombination von Window-Stile. Sie müssen das Format WS_CHILD einschließen, da das Steuerelement ein untergeordnetes Fenster sein muss. Finden Sie unter [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) im Windows SDK für eine Liste der Windows-Formate.

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

##  <a name="getaddress"></a>  CIPAddressCtrl::GetAddress

Ruft die Adresswerte für alle vier Felder im IP-Adresse-Steuerelement.

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
Ein Verweis auf den Feldwert 0 durch eine gepackte IP-Adresse.

*nField1*<br/>
Ein Verweis auf den Feldwert 1 durch eine gepackte IP-Adresse.

*nField2*<br/>
Ein Verweis auf den Feldwert 2 durch eine gepackte IP-Adresse.

*nField3*<br/>
Ein Verweis auf den Feldwert 3 durch eine gepackte IP-Adresse.

*dwAddress*<br/>
Ein Verweis auf die Adresse des DWORD-Wert, der die IP-Adresse empfängt. Finden Sie unter **"Hinweise"** für eine Tabelle, die zeigt, wie *DwAddress* gefüllt wird.

### <a name="return-value"></a>Rückgabewert

Die Anzahl der nicht leeren Feldern im IP-Adresse-Steuerelement.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [IPM_GETADDRESS](/windows/desktop/Controls/ipm-getaddress), wie im Windows SDK beschrieben. Klicken Sie im oben genannten ersten Prototyp die Zahlen in Feldern von 0 bis 3 des Steuerelements, Lesen von links nach rechts bzw., füllen Sie die vier Parameter. Im zweiten oben genannten Prototyp *DwAddress* wird folgendermaßen aufgefüllt.

|Feld|Bits, die den Wert des Felds enthält.|
|-----------|-------------------------------------|
|0|24 bis 31|
|1|16 bis 23|
|2|8 bis 15|
|3|0 bis 7|

##  <a name="isblank"></a>  CIPAddressCtrl::IsBlank

Bestimmt, ob alle Felder in die IP-Adressensteuerelement leer sind.

```
BOOL IsBlank() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn alle IP-Adressensteuerelement Felder leer sind; andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [IPM_ISBLANK](/windows/desktop/Controls/ipm-isblank), wie im Windows SDK beschrieben.

##  <a name="setaddress"></a>  CIPAddressCtrl::SetAddress

Legt die Adresswerte für alle vier Felder in die IP-Adressensteuerelement fest.

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
Der 0 Feldwert aus eine gepackte IP-Adresse.

*nField1*<br/>
Der Feld 1-Wert aus einer gepackte IP-Adresse.

*nField2*<br/>
Der 2 Feldwert aus eine gepackte IP-Adresse.

*nField3*<br/>
Der 3 Feldwert aus eine gepackte IP-Adresse.

*dwAddress*<br/>
Eine DWORD-Wert, der die neue IP-Adresse enthält. Finden Sie unter **"Hinweise"** für eine Tabelle, die zeigt, wie der DWORD-Wert ausgefüllt wird.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [IPM_SETADDRESS](/windows/desktop/Controls/ipm-setaddress), wie im Windows SDK beschrieben. Klicken Sie im oben genannten ersten Prototyp die Zahlen in Feldern von 0 bis 3 des Steuerelements, Lesen von links nach rechts bzw., füllen Sie die vier Parameter. Im zweiten oben genannten Prototyp *DwAddress* wird folgendermaßen aufgefüllt.

|Feld|Bits, die den Wert des Felds enthält.|
|-----------|-------------------------------------|
|0|24 bis 31|
|1|16 bis 23|
|2|8 bis 15|
|3|0 bis 7|

##  <a name="setfieldfocus"></a>  CIPAddressCtrl::SetFieldFocus

Legt den Tastaturfokus auf das angegebene Feld in die IP-Adressensteuerelement fest.

```
void SetFieldFocus(WORD nField);
```

### <a name="parameters"></a>Parameter

*nField*<br/>
Null basierenden feldindexes, auf denen der Fokus festgelegt werden soll. Wenn dieser Wert größer als die Anzahl von Feldern ist, wird der Fokus auf das erste leere Feld gesetzt. Wenn alle Felder nicht leer sind, wird der Fokus auf das erste Feld festgelegt.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [IPM_SETFOCUS](/windows/desktop/Controls/ipm-setfocus), wie im Windows SDK beschrieben.

##  <a name="setfieldrange"></a>  CIPAddressCtrl::SetFieldRange

Legt den Bereich in das angegebene Feld in die IP-Adressensteuerelement fest.

```
void SetFieldRange(
    int nField,
    BYTE nLower,
    BYTE nUpper);
```

### <a name="parameters"></a>Parameter

*nField*<br/>
Null basierenden feldindexes auf die der Bereich angewendet werden soll.

*nLower*<br/>
Ein Verweis auf eine ganze Zahl, die die untere Grenze des angegebenen Felds in diesem Steuerelement der IP-Adresse empfangen.

*nUpper*<br/>
Ein Verweis auf eine ganze Zahl, die die obere Grenze des angegebenen Felds in diesem Steuerelement der IP-Adresse empfangen.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [IPM_SETRANGE](/windows/desktop/Controls/ipm-setrange), wie im Windows SDK beschrieben. Verwenden Sie die zwei Parameter, *nLower* und *nUpper*, an den oberen und unteren Grenzwerten des Felds, statt die *wRange* die Win32-Nachricht als Parameter.

## <a name="see-also"></a>Siehe auch

[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)

