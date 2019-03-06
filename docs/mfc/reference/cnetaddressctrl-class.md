---
title: CNetAddressCtrl-Klasse
ms.date: 11/19/2018
f1_keywords:
- CNetAddressCtrl
- AFXCMN/CNetAddressCtrl
- AFXCMN/CNetAddressCtrl::CNetAddressCtrl
- AFXCMN/CNetAddressCtrl::Create
- AFXCMN/CNetAddressCtrl::CreateEx
- AFXCMN/CNetAddressCtrl::DisplayErrorTip
- AFXCMN/CNetAddressCtrl::GetAddress
- AFXCMN/CNetAddressCtrl::GetAllowType
- AFXCMN/CNetAddressCtrl::SetAllowType
helpviewer_keywords:
- CNetAddressCtrl [MFC], CNetAddressCtrl
- CNetAddressCtrl [MFC], Create
- CNetAddressCtrl [MFC], CreateEx
- CNetAddressCtrl [MFC], DisplayErrorTip
- CNetAddressCtrl [MFC], GetAddress
- CNetAddressCtrl [MFC], GetAllowType
- CNetAddressCtrl [MFC], SetAllowType
ms.assetid: cb4c6aca-3f49-4b52-b76c-65f57096155b
ms.openlocfilehash: ec4d7aa6f2a1061e632b81a27a0233cf5fdd1c63
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57423559"
---
# <a name="cnetaddressctrl-class"></a>CNetAddressCtrl-Klasse

Die Klasse `CNetAddressCtrl` stellt das Netzwerkadressen-Steuerelement dar, das verwendet werden kann, um IPv4-, IPv6- und benannte DNS-Adressen einzugeben und ihr Format zu überprüfen.

## <a name="syntax"></a>Syntax

```
class CNetAddressCtrl : public CEdit
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CNetAddressCtrl::CNetAddressCtrl](#cnetaddressctrl)|Erstellt ein `CNetAddressCtrl`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CNetAddressCtrl::Create](#create)|Erstellt eine Netzwerkadressen-Steuerelement mit der angegebenen Formate und hängt es an der aktuellen `CNetAddressCtrl` Objekt.|
|[CNetAddressCtrl::CreateEx](#createex)|Erstellt eine Netzwerkadressen-Steuerelement mit dem angegebenen erweiterten Stile und hängt es an der aktuellen `CNetAddressCtrl` Objekt.|
|[CNetAddressCtrl::DisplayErrorTip](#displayerrortip)|Zeigt eine SprechblasenInfo für Fehler, wenn der Benutzer eine nicht unterstützte Netzwerkadresse in der aktuellen Netzwerkadressen-Steuerelement eingibt.|
|[CNetAddressCtrl::GetAddress](#getaddress)|Ruft eine Darstellung überprüft und analysiert die Netzwerkadresse, die die aktuellen Netzwerkadressen-Steuerelement zugeordnete ab.|
|[CNetAddressCtrl::GetAllowType](#getallowtype)|Ruft den Typ der Netzwerkadresse, die die aktuellen Netzwerkadressen-Steuerelement unterstützt werden.|
|[CNetAddressCtrl::SetAllowType](#setallowtype)|Legt fest, den Typ der Netzwerkadresse, die die aktuellen Netzwerkadressen-Steuerelement unterstützt werden.|

## <a name="remarks"></a>Hinweise

Das Netzwerkadressen-Steuerelement stellt sicher, dass das Format der vom Benutzer eingegebene Adresse richtig ist. Das Steuerelement ist nicht tatsächlich an die Netzwerkadresse eine Verbindung herstellen. Die [CNetAddressCtrl::SetAllowType](#setallowtype) Methode gibt einen oder mehrere Typen der Adresse, die die [CNetAddressCtrl::GetAddress](#getaddress) Methode analysieren und überprüfen kann. Eine Adresse kann in Form einer IPv4, IPv6- oder benannte Adresse für einen Server, Netzwerk, Host oder -Broadcastnachricht Ziel sein. Wenn das Format der Adresse falsch ist, können Sie die [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) Methode, um ein Meldungsfeld Infotipp anzuzeigen, die grafisch verweist auf das Textfeld ein, der das Netzwerkadressen-Steuerelement und zeigt eine vordefinierte Fehlermeldung.

Die `CNetAddressCtrl` abgeleitete Klasse wird die [CEdit](../../mfc/reference/cedit-class.md) Klasse. Das Netzwerkadressen-Steuerelement bietet daher den Zugriff auf alle Windows bearbeiten-Steuerelement-Nachrichten.

Die folgende Abbildung zeigt ein Dialogfeld, das eine Netzwerkadressen-Steuerelement enthält. Der Text Box (1) für das Netzwerkadressen-Steuerelement enthält eine ungültige Netzwerk-Adresse. Die QuickInfo-Meldung (2) wird angezeigt, wenn die Netzwerkadresse ungültig ist.

![Dialogfeld mit einem Netzwerkadressen-Steuerelement und Infotipps. ](../../mfc/reference/media/cnetaddctrl.png "Dialogfeld mit einem Netzwerkadressen-Steuerelement und Infotipps.")

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird ein Teil eines Dialogfelds, das eine Netzwerkadresse überprüft. Die Ereignishandler für drei Optionsfeldern angeben, dass die Netzwerkadresse auf einem von drei Adresstypen sein kann. Der Benutzer gibt eine Adresse in das Textfeld des Netzwerk-Steuerelements, und dann eine drückt, um die Adresse zu überprüfen. Wenn die Adresse gültig ist, wird eine Erfolgsmeldung angezeigt; Andernfalls wird die Fehlermeldung für den vordefinierten Infotipp angezeigt.

[!code-cpp[NVC_MFC_CNetAddressCtrl_s1#1](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_1.cpp)]

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird aus der Dialogfeld-Headerdatei definiert die [NC_ADDRESS](/windows/desktop/api/shellapi/ns-shellapi-tagnc_address) und [NET_ADDRESS_INFO](https://msdn.microsoft.com/library/windows/desktop/bb773346) Variablen, die erforderlich sind die [CNetAddressCtrl::GetAddress](#getaddress)Methode.

[!code-cpp[NVC_MFC_CNetAddressCtrl_s1#2](../../mfc/reference/codesnippet/cpp/cnetaddressctrl-class_2.h)]

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

`CNetAddressCtrl`

## <a name="requirements"></a>Anforderungen

**Header:** afxcmn.h

Diese Klasse wird in Windows Vista und höheren Versionen unterstützt.

Zusätzliche Anforderungen für diese Klasse werden in beschrieben [erstellen Anforderungen für Windows Vista-Standardsteuerelementen](../../mfc/build-requirements-for-windows-vista-common-controls.md).

##  <a name="cnetaddressctrl"></a>  CNetAddressCtrl::CNetAddressCtrl

Erstellt ein `CNetAddressCtrl`-Objekt.

```
CNetAddressCtrl();
```

### <a name="remarks"></a>Hinweise

Verwenden der [CNetAddressCtrl::Create](#create) oder [CNetAddressCtrl::CreateEx](#createex) Methode zum Erstellen eines Netzwerk-Steuerelements, und fügen Sie ihn auf die `CNetAddressCtrl` Objekt.

##  <a name="create"></a>  CNetAddressCtrl::Create

Erstellt eine Netzwerkadressen-Steuerelement mit der angegebenen Formate und hängt es an der aktuellen `CNetAddressCtrl` Objekt.

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
|*dwStyle*|[in] Eine bitweise Kombination der Formate auf das Steuerelement angewendet werden. Weitere Informationen finden Sie unter [Stile bearbeiten](../../mfc/reference/styles-used-by-mfc.md#edit-styles).|
|*rect*|[in] Ein Verweis auf eine [RECT](/previous-versions/dd162897\(v=vs.85\)) Struktur, die die Position und Größe des Steuerelements enthält.|
|*pParentWnd*|[in] Ein nicht-Null-Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das das übergeordnete Fenster des Steuerelements ist.|
|*nID*|[in] Die ID des Steuerelements.|

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

##  <a name="createex"></a>  CNetAddressCtrl::CreateEx

Erstellt eine Netzwerkadressen-Steuerelement mit dem angegebenen erweiterten Stile und hängt es an der aktuellen `CNetAddressCtrl` Objekt.

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
|*dwExStyle*|[in] Eine bitweise Kombination (OR) von erweiterten Stile, die auf das Steuerelement angewendet werden. Weitere Informationen finden Sie unter den *DwExStyle* Parameter, der die [CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Funktion.|
|*dwStyle*|[in] Eine bitweise Kombination (OR) von Formatvorlagen, die auf das Steuerelement angewendet werden. Weitere Informationen finden Sie unter [Stile bearbeiten](../../mfc/reference/styles-used-by-mfc.md#edit-styles).|
|*rect*|[in] Ein Verweis auf eine [RECT](/previous-versions/dd162897\(v=vs.85\)) Struktur, die die Position und Größe des Steuerelements enthält.|
|*pParentWnd*|[in] Ein nicht-Null-Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) -Objekt, das das übergeordnete Fenster des Steuerelements ist.|
|*nID*|[in] Die ID des Steuerelements.|

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

##  <a name="displayerrortip"></a>  CNetAddressCtrl::DisplayErrorTip

Zeigt eine Fehlermeldung in der QuickInfo-Sprechblase, die die aktuellen Netzwerkadressen-Steuerelement zugeordnet ist.

```
HRESULT DisplayErrorTip();
```

### <a name="return-value"></a>Rückgabewert

Der Wert `S_OK` , wenn diese Methode erfolgreich; andernfalls ist ein Fehlercode.

### <a name="remarks"></a>Hinweise

Verwenden der [CNetAddressCtrl::SetAllowType](#setallowtype) Methode, um die Typen von Adressen anzugeben, die die aktuellen Netzwerkadressen-Steuerelement unterstützt werden. Verwenden der [CNetAddressCtrl::GetAddress](#getaddress) Methode, um zu überprüfen und analysieren die Netzwerkadresse, die der Benutzer eingibt. Verwenden der [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) Methode einen Fehler Nachricht Infotipp anzuzeigen, wenn die [CNetAddressCtrl::GetAddress](#getaddress) Methode nicht erfolgreich ist.

Diese Nachricht Ruft die [NetAddr_DisplayErrorTip](/windows/desktop/api/shellapi/nf-shellapi-netaddr_displayerrortip) Makro, das im Windows SDK beschrieben wird. Dieses Makro sendet die `NCM_DISPLAYERRORTIP` Nachricht.

##  <a name="getaddress"></a>  CNetAddressCtrl::GetAddress

Ruft eine Darstellung überprüfte und analysierte die Netzwerkadresse, die die aktuellen Netzwerkadressen-Steuerelement zugeordnet ist.

```
HRESULT GetAddress(PNC_ADDRESS pAddress) const;
```

### <a name="parameters"></a>Parameter

*pAddress*<br/>
[in, out] Zeiger auf ein [NC_ADDRESS](/windows/desktop/api/shellapi/ns-shellapi-tagnc_address) Struktur.  Legen Sie die *pAddrInfo* Member der Struktur an die Adresse des eine [NET_ADDRESS_INFO](https://msdn.microsoft.com/library/windows/desktop/bb773346) strukturieren, bevor Sie die GetAddress-Methode aufrufen.

### <a name="return-value"></a>Rückgabewert

Der Wert S_OK zurück, wenn diese Methode erfolgreich ist; andernfalls, eine COM-Fehlercode. Weitere Informationen zu den möglichen Fehlercodes finden Sie im Abschnitt Rückgabewert der [NetAddr_GetAddress](/windows/desktop/api/shellapi/nf-shellapi-netaddr_getaddress) Makro.

### <a name="remarks"></a>Hinweise

Wenn diese Methode erfolgreich ist, ist die [NET_ADDRESS_INFO](https://msdn.microsoft.com/library/windows/desktop/bb773346) Struktur enthält zusätzliche Informationen über die Netzwerkadresse.

Verwenden der [CNetAddressCtrl::SetAllowType](#setallowtype) Methode, um die Typen von Adressen anzugeben, kann die aktuellen Netzwerkadressen-Steuerelement zu unterstützen. Verwenden der [CNetAddressCtrl::GetAddress](#getaddress) Methode, um zu überprüfen und analysieren die Netzwerkadresse, die der Benutzer eingibt. Verwenden der [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) Methode einen Fehler Nachricht Infotipp anzuzeigen, wenn die [CNetAddressCtrl::GetAddress](#getaddress) Methode nicht erfolgreich ist.

Diese Methode ruft die [NetAddr_GetAddress](/windows/desktop/api/shellapi/nf-shellapi-netaddr_getaddress) Makro, das im Windows SDK beschrieben wird. Dieses Makro sendet die Nachricht NCM_GETADDRESS.

##  <a name="getallowtype"></a>  CNetAddressCtrl::GetAllowType

Ruft den Typ der Netzwerkadresse, die die aktuellen Netzwerkadressen-Steuerelement unterstützt werden.

```
DWORD GetAllowType() const;
```

### <a name="return-value"></a>Rückgabewert

Eine bitweise Kombination (OR) von Flags, die angibt, die Typen von Adressen unterstützen das Netzwerkadressen-Steuerelement. Weitere Informationen finden Sie unter [NET_STRING](https://msdn.microsoft.com/library/windows/desktop/bb762586).

### <a name="remarks"></a>Hinweise

Diese Nachricht Ruft die [NetAddr_GetAllowType](/windows/desktop/api/shellapi/nf-shellapi-netaddr_getallowtype) Makro, das im Windows SDK beschrieben wird. Dieses Makro sendet die Nachricht NCM_GETALLOWTYPE.

##  <a name="setallowtype"></a>  CNetAddressCtrl::SetAllowType

Legt fest, den Typ der Netzwerkadresse, die die aktuellen Netzwerkadressen-Steuerelement unterstützt werden.

```
HRESULT SetAllowType(DWORD dwAddrMask);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*dwAddrMask*|[in] Eine bitweise Kombination (OR) von Flags, die angibt, die Typen von Adressen unterstützen das Netzwerkadressen-Steuerelement. Weitere Informationen finden Sie unter [NET_STRING](https://msdn.microsoft.com/library/windows/desktop/bb762586).|

### <a name="return-value"></a>Rückgabewert

S_OK, wenn diese Methode erfolgreich ist; andernfalls, eine COM-Fehlercode.

### <a name="remarks"></a>Hinweise

Verwenden der [CNetAddressCtrl::SetAllowType](#setallowtype) Methode, um die Typen von Adressen anzugeben, die die aktuellen Netzwerkadressen-Steuerelement unterstützt werden. Verwenden der [CNetAddressCtrl::GetAddress](#getaddress) Methode, um zu überprüfen und analysieren die Netzwerkadresse, die der Benutzer eingibt. Verwenden der [CNetAddressCtrl::DisplayErrorTip](#displayerrortip) Methode einen Fehler Nachricht Infotipp anzuzeigen, wenn die [CNetAddressCtrl::GetAddress](#getaddress) Methode nicht erfolgreich ist.

Diese Nachricht Ruft die [NetAddr_SetAllowType](/windows/desktop/api/shellapi/nf-shellapi-netaddr_setallowtype) Makro, das im Windows SDK beschrieben wird. Dieses Makro sendet die Nachricht NCM_SETALLOWTYPE.

## <a name="see-also"></a>Siehe auch

[CNetAddressCtrl-Klasse](../../mfc/reference/cnetaddressctrl-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CEdit-Klasse](../../mfc/reference/cedit-class.md)
