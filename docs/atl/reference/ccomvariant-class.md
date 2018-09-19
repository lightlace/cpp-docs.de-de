---
title: CComVariant-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComVariant
- ATLCOMCLI/ATL::CComVariant
- ATLCOMCLI/ATL::CComVariant::CComVariant
- ATLCOMCLI/ATL::CComVariant::Attach
- ATLCOMCLI/ATL::CComVariant::ChangeType
- ATLCOMCLI/ATL::CComVariant::Clear
- ATLCOMCLI/ATL::CComVariant::Copy
- ATLCOMCLI/ATL::CComVariant::CopyTo
- ATLCOMCLI/ATL::CComVariant::Detach
- ATLCOMCLI/ATL::CComVariant::GetSize
- ATLCOMCLI/ATL::CComVariant::ReadFromStream
- ATLCOMCLI/ATL::CComVariant::SetByRef
- ATLCOMCLI/ATL::CComVariant::WriteToStream
dev_langs:
- C++
helpviewer_keywords:
- VARIANT macro
- CComVariant class
- VARIANT macro, ATL
ms.assetid: 4d31149c-d005-44b5-a509-10f84afa2b61
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 89b1dbfe9dcf00582f5f8736a4706a18439b51c6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042545"
---
# <a name="ccomvariant-class"></a>CComVariant-Klasse

Diese Klasse umschließt den VARIANT-Datentyp, der einen Member, der angibt, der den Typ der gespeicherten Daten bereitstellt.

## <a name="syntax"></a>Syntax

```cpp
class CComVariant : public tagVARIANT
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComVariant::CComVariant](#ccomvariant)|Der Konstruktor.|
|[CComVariant:: ~ CComVariant](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComVariant::Attach](#attach)|Fügt eine Variante an die `CComVariant` Objekt.|
|[CComVariant::ChangeType](#changetype)|Konvertiert die `CComVariant` Objekt in einen neuen Typ.|
|[CComVariant::Clear](#clear)|Löscht die `CComVariant` Objekt.|
|[CComVariant::Copy](#copy)|Eine Variante, kopiert der `CComVariant` Objekt.|
|[CComVariant::CopyTo](#copyto)|Kopiert den Inhalt der `CComVariant` Objekt.|
|[CComVariant::Detach](#detach)|Trennt die zugrunde liegende Variante aus der `CComVariant` Objekt.|
|[CComVariant::GetSize](#getsize)|Gibt die Größe in Anzahl von Bytes des Inhalts der `CComVariant` Objekt.|
|[CComVariant::ReadFromStream](#readfromstream)|Lädt eine Variante aus einem Stream.|
|[CComVariant::SetByRef](#setbyref)|Initialisiert die `CComVariant` -Objekt und legt die `vt` VT_BYREF Member.|
|[CComVariant:: WriteToStream](#writetostream)|Speichert die zugrunde liegende Variante in einem Stream.|

### <a name="public-operators"></a>Öffentliche Operatoren

|||
|-|-|
|[CComVariant <](#operator_lt)|Gibt an, ob die `CComVariant` Objekt ist kleiner als die angegebene Variante.|
|[CComVariant >](#operator_gt)|Gibt an, ob die `CComVariant` -Quellobjekt ist größer als die angegebene Variante.|
|[Operator! =](#operator_neq)|Gibt an, ob die `CComVariant` Objekt entspricht nicht die angegebene Variante.|
|[operator =](#operator_eq)|Weist einen Wert, der `CComVariant` Objekt.|
|[operator ==](#operator_eq_eq)|Gibt an, ob die `CComVariant` Objekt gleich die angegebene Variante.|

## <a name="remarks"></a>Hinweise

`CComVariant` Dient als Wrapper für die VARIANT und VARIANTARG-Typ, der besteht aus einer Union und einen Member, der angibt, der des Typs der in der Union gespeicherten Daten. Varianten werden in der Regel in Automation verwendet werden.

`CComVariant` wird aus dem VARIANT-Typ abgeleitet, damit sie verwendet werden kann, wo eine Variante verwendet werden kann. Z. B. können Sie das Makro V_VT extrahieren Sie den Typ des eine `CComVariant` oder Sie können den Zugriff auf die `vt` Member direkt so, wie Sie eine Variante können.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`tagVARIANT`

`CComVariant`

## <a name="requirements"></a>Anforderungen

**Header:** "atlcomcli.h"

##  <a name="attach"></a>  CComVariant::Attach

Sichere löscht den aktuellen Inhalt des der `CComVariant` Objekt, das kopiert den Inhalt des *pSrc* in dieses Objekt, legt dann die Varianten-Typ des *pSrc* auf VT_EMPTY.

```
HRESULT Attach(VARIANT* pSrc);
```

### <a name="parameters"></a>Parameter

*pSrc*<br/>
[in] Verweist auf die [VARIANT](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) an das Objekt angefügt werden.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Besitz von gespeicherten Daten *pSrc* wird zum Übertragen der `CComVariant` Objekt.

##  <a name="ccomvariant"></a>  CComVariant::CComVariant

Jeder Konstruktor übernimmt die threadsichere Initialisierung der `CComVariant` -Objekt durch Aufrufen der `VariantInit` Win32-Funktion oder durch Festlegen des Objekts Wert und Typ gemäß den Parametern übergeben.

```
CComVariant() throw();
CComVariant(const CComVariant& varSrc);
CComVariant(const VARIANT& varSrc);
CComVariant(LPCOLESTR lpszSrc);
CComVariant(LPCSTR lpszSrc);
CComVariant(bool bSrc);
CComVariant(BYTE nSrc) throw();
CComVariant(int nSrc, VARTYPE vtSrc = VT_I4) throw();
CComVariant(unsigned int  nSrc, VARTYPE vtSrc = VT_UI4) throw();
CComVariant(shor  nSrc) throw();
CComVariant(unsigned short nSrc) throw();
CComVariant(long  nSrc, VARTYPE vtSrc = VT_I4) throw();
CComVariant(unsigned long  nSrc) throw();
CComVariant(LONGLONG  nSrc) throw();
CComVariant(ULONGLONG  nSrc) throw();
CComVariant(float  fltSrc) throw();
CComVariant(double  dblSrc, VARTYPE vtSrc = VT_R8) throw();
CComVariant(CY  cySrc) throw();
CComVariant(IDispatch* pSrc) throw();
CComVariant(IUnknown* pSrc) throw();
CComVariant(const SAFEARRAY* pSrc);
CComVariant(char  cSrc) throw();
CComVariant(const CComBSTR& bstrSrc);
```

### <a name="parameters"></a>Parameter

*varSrc*<br/>
[in] Die `CComVariant` oder Variante, die zum Initialisieren der `CComVariant` Objekt. Der Inhalt der Variante Quelle werden an das Ziel ohne Konvertierung kopiert.

*lpszSrc*<br/>
[in] Die Zeichenfolge, die zum Initialisieren der `CComVariant` Objekt. Sie können (0 (null) endende Breite Unicode)-Zeichenfolge an die LPCOLESTR-Version von den Konstruktor oder eine ANSI-Zeichenfolge auf die Version LPCSTR übergeben. In beiden Fällen wird die Zeichenfolge in ein Unicode BSTR mit reserviert konvertiert `SysAllocString`. Der Typ des der `CComVariant` Objekt werden VT_BSTR.

*bSrc*<br/>
[in] Die **"bool"** zum Initialisieren der `CComVariant` Objekt. Die **"bool"** Argument wird in einer VARIANT_BOOL konvertiert, bevor Sie gespeichert wird. Der Typ des der `CComVariant` Objekt werden VT_BOOL.

*nSrc*<br/>
[in] Die **Int**, **BYTE**, **kurze**, **lange**, LONGLONG, ULONGLONG, **unsigned short**, **unsigned long**, oder **ganze Zahl ohne Vorzeichen** zum Initialisieren der `CComVariant` Objekt. Der Typ des der `CComVariant` Objekt werden VT_I4, VT_UI1, VT_I2, VT_I4, VT_I8, VT_UI8, VT_UI2, VT_UI4 oder VT_UI4, bzw.

*vtSrc*<br/>
[in] Der Typ der Variante. Wenn der erste Parameter ist **Int**, gültigen Typen sind VT_I4 und VT_INT. Wenn der erste Parameter ist **lange**, gültigen Typen sind VT_I4 und VT_ERROR. Wenn der erste Parameter ist **doppelte**, gültigen Typen sind VT_R8 und VT_DATE. Wenn der erste Parameter ist **ganze Zahl ohne Vorzeichen**, gültige Typen sind, VT_UI4 und VT_UINT.

*fltSrc*<br/>
[in] Die **"float"** zum Initialisieren der `CComVariant` Objekt. Der Typ des der `CComVariant` Objekt werden VT_R4.

*dblSrc*<br/>
[in] Die **doppelte** zum Initialisieren der `CComVariant` Objekt. Der Typ des der `CComVariant` Objekt werden VT_R8.

*cySrc*<br/>
[in] Die `CY` zum Initialisieren der `CComVariant` Objekt. Der Typ des der `CComVariant` Objekt werden VT_CY.

*pSrc*<br/>
[in] Die `IDispatch` oder `IUnknown` Zeiger, die zum Initialisieren der `CComVariant` Objekt. `AddRef` wird für den Schnittstellenzeiger aufgerufen werden. Der Typ des der `CComVariant` Objekt fungiert als "VT_DISPATCH" oder "VT_UNKNOWN", bzw.

Oder der SAFERRAY-Zeiger, die zum Initialisieren der `CComVariant` Objekt. Eine Kopie des SafeArray-Elements befindet sich in der `CComVariant` Objekt. Der Typ des der `CComVariant` Objekt wird eine Kombination aus den ursprünglichen Typ der SAFEARRAY und VT_ARRAY sein.

*cSrc*<br/>
[in] Die **Char** zum Initialisieren der `CComVariant` Objekt. Der Typ des der `CComVariant` Objekt werden VT_I1.

*bstrSrc*<br/>
[in] BSTR, das zum Initialisieren verwendet die `CComVariant` Objekt. Der Typ des der `CComVariant` Objekt werden VT_BSTR.

### <a name="remarks"></a>Hinweise

Der Destruktor verwaltet Bereinigung durch Aufrufen von [CComVariant::Clear](#clear).

##  <a name="dtor"></a>  CComVariant:: ~ CComVariant

Der Destruktor.

```
~CComVariant() throw();
```

### <a name="remarks"></a>Hinweise

Diese Methode verwaltet die Bereinigung durch Aufrufen von [CComVariant::Clear](#clear).

##  <a name="changetype"></a>  CComVariant::ChangeType

Konvertiert die `CComVariant` Objekt in einen neuen Typ.

```
HRESULT ChangeType(VARTYPE vtNew, const VARIANT* pSrc = NULL);
```

### <a name="parameters"></a>Parameter

*vtNew*<br/>
[in] Der neue Typ für die `CComVariant` Objekt.

*pSrc*<br/>
[in] Ein Zeiger auf den Variant-Wert, dessen Wert auf den neuen Typ konvertiert werden soll. Der Standardwert ist NULL, Bedeutung der `CComVariant` direktes Objekt konvertiert.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Wenn Sie einen Wert, für die übergeben *pSrc*, `ChangeType` diese Variante wird als Quelle für die Konvertierung verwenden. Andernfalls die `CComVariant` Objekt wird die Quelle sein.

##  <a name="clear"></a>  CComVariant::Clear

Löscht die `CComVariant` -Objekt durch Aufrufen der `VariantClear` Win32-Funktion.

```
HRESULT Clear();
```

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Ruft der Destruktor automatisch `Clear`.

##  <a name="copy"></a>  CComVariant::Copy

Gibt frei, die `CComVariant` Objekt aus, und klicken Sie dann eine Kopie der angegebenen Variante zugewiesen.

```
HRESULT Copy(const VARIANT* pSrc);
```

### <a name="parameters"></a>Parameter

*pSrc*<br/>
[in] Ein Zeiger auf die [VARIANT](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) kopiert werden soll.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

##  <a name="copyto"></a>  CComVariant::CopyTo

Kopiert den Inhalt der `CComVariant` Objekt.

```
HRESULT CopyTo(BSTR* pstrDest);
```

### <a name="parameters"></a>Parameter

*pstrDest*<br/>
Verweist auf ein BSTR, das eine Kopie des Inhalts der erhält die `CComVariant` Objekt.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die `CComVariant` Objekt muss vom Typ VT_BSTR sein.

##  <a name="detach"></a>  CComVariant::Detach

Trennt die zugrunde liegende Variante aus der `CComVariant` -Objekt und legt den Typ des Objekts auf VT_EMPTY.

```
HRESULT Detach(VARIANT* pDest);
```

### <a name="parameters"></a>Parameter

*pDest*<br/>
[out] Gibt den zugrunde liegenden VARIANT-Wert des Objekts zurück.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Beachten Sie, die den Inhalt der Variante von referenziert *pDest* wird automatisch gelöscht werden, bevor die gruppenzuweisung für den Wert und Typ des aufrufenden `CComVariant` Objekt.

##  <a name="getsize"></a>  CComVariant::GetSize

Für einfache fester Größenvarianten, diese Methode gibt die **"sizeof"** der zugrunde liegende Datentyp plus **sizeof(VARTYPE)**.

```
ULONG GetSize() const;
```

### <a name="return-value"></a>Rückgabewert

Die Größe in Bytes, der den aktuellen Inhalt des der `CComVariant` Objekt.

### <a name="remarks"></a>Hinweise

Wenn die Variante einen Schnittstellenzeiger enthält `GetSize` fragt nach `IPersistStream` oder `IPersistStreamInit`. Wenn erfolgreich, der Rückgabewert die 32 niedrigwertigen Bits der den Rückgabewert von `GetSizeMax` sowie die **"sizeof"** CLSID und **sizeof(VARTYPE)**. Wenn der Schnittstellenzeiger auf NULL, `GetSize` gibt die **"sizeof"** plus CLSID **sizeof(VARTYPE)**. Wenn die Gesamtgröße ULONG_MAX, übersteigt `GetSize` gibt **sizeof(VARTYPE)** gibt einen Fehler an.

In allen anderen Fällen wird eine temporäre Variante vom Typ VT_BSTR aus der aktuellen Variant-Wert umgewandelt. Die Länge dieses BSTR wird berechnet, als die Größe der die Länge der Zeichenfolge plus die Länge der Zeichenfolge selbst zuzüglich der Größe des Null-Zeichens plus **sizeof(VARTYPE)**. Wenn die Variante kann, auf eine Variante vom Typ VT_BSTR umgewandelt werden, `GetSize` gibt **sizeof(VARTYPE)**.

Die Größe, die von dieser Methode zurückgegebene entspricht die Anzahl der Bytes, die von verwendeten [CComVariant:: WriteToStream](#writetostream) erfolgreich ausgelastet.

##  <a name="operator_eq"></a>  CComVariant =

Weist einen Wert und den entsprechenden Typ als die `CComVariant` Objekt.

```
CComVariant& operator=(const CComVariant& varSrc);
CComVariant& operator=(const VARIANT& varSrc);
CComVariant& operator=(const CComBSTR& bstrSrc);
CComVariant& operator=(LPCOLESTR lpszSrc);
CComVariant& operator=(LPCSTR lpszSrc);
CComVariant& operator=(bool bSrc);
CComVariant& operator=(BYTE nSrc) throw();
CComVariant& operator=int nSrc) throw();
CComVariant& operator=(unsigned int nSrc) throw();
CComVariant& operator=(short nSrc) throw();
CComVariant& operator=(unsigned short nSrc) throw();
CComVariant& operator=(long nSrc) throw();
CComVariant& operator=(unsigned long nSrc) throw();
CComVariant& operator=(LONGLONG nSrc) throw();
CComVariant& operator=(ULONGLONG nSrc) throw();
CComVariant& operator=(float fltSrc) throw();
CComVariant& operator=(double dblSrc) throw();
CComVariant& operator=(CY cySrc) throw();
CComVariant& operator=(IDispatch* pSrc) throw();
CComVariant& operator=(IUnknown* pSrc) throw();
CComVariant& operator=(const SAFEARRAY* pSrc);
CComVariant& operator=(char cSrc) throw();
```

### <a name="parameters"></a>Parameter

*varSrc*<br/>
[in] Die `CComVariant` oder [VARIANT](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) zugewiesen werden die `CComVariant` Objekt. Der Inhalt der Variante Quelle werden an das Ziel ohne Konvertierung kopiert.

*bstrSrc*<br/>
[in] BSTR, zugewiesen werden soll die `CComVariant` Objekt. Der Typ des der `CComVariant` Objekt werden VT_BSTR.

*lpszSrc*<br/>
[in] Die Zeichenfolge, die zugewiesen werden die `CComVariant` Objekt. Sie können (0 (null) endende Breite Unicode)-Zeichenfolge auf die LPCOLESTR-Version, der der Operator oder eine ANSI-Zeichenfolge auf die Version LPCSTR übergeben. In beiden Fällen wird die Zeichenfolge in ein Unicode BSTR mit reserviert konvertiert `SysAllocString`. Der Typ des der `CComVariant` Objekt werden VT_BSTR.

*bSrc*<br/>
[in] Die **"bool"** zugewiesen werden die `CComVariant` Objekt. Die **"bool"** Argument wird in einer VARIANT_BOOL konvertiert, bevor Sie gespeichert wird. Der Typ des der `CComVariant` Objekt werden VT_BOOL.

*nSrc*<br/>
[in] Die **Int**, BYTE, **kurze**, **lange**, LONGLONG, ULONGLONG, **unsigned short**, **unsigned long**, oder **ganze Zahl ohne Vorzeichen** zugewiesen werden die `CComVariant` Objekt. Der Typ des der `CComVariant` Objekt werden VT_I4, VT_UI1, VT_I2, VT_I4, VT_I8, VT_UI8, VT_UI2, VT_UI4 oder VT_UI4, bzw.

*fltSrc*<br/>
[in] Die **"float"** zugewiesen werden die `CComVariant` Objekt. Der Typ des der `CComVariant` Objekt werden VT_R4.

*dblSrc*<br/>
[in] Die **doppelte** zugewiesen werden die `CComVariant` Objekt. Der Typ des der `CComVariant` Objekt werden VT_R8.

*cySrc*<br/>
[in] Die `CY` zugewiesen werden die `CComVariant` Objekt. Der Typ des der `CComVariant` Objekt werden VT_CY.

*pSrc*<br/>
[in] Die `IDispatch` oder `IUnknown` Zeiger zugewiesen werden die `CComVariant` Objekt. `AddRef` wird für den Schnittstellenzeiger aufgerufen werden. Der Typ des der `CComVariant` Objekt fungiert als "VT_DISPATCH" oder "VT_UNKNOWN", bzw.

Oder, ein SAFEARRAY-Zeiger zugewiesen werden die `CComVariant` Objekt. Eine Kopie des SafeArray-Elements befindet sich in der `CComVariant` Objekt. Der Typ des der `CComVariant` Objekt wird eine Kombination aus den ursprünglichen Typ der SAFEARRAY und VT_ARRAY sein.

*cSrc*<br/>
[in] Der Zeichenwert zugewiesen werden die `CComVariant` Objekt. Der Typ des der `CComVariant` Objekt werden VT_I1.

##  <a name="operator_eq_eq"></a>  CComVariant ==

Gibt an, ob die `CComVariant` Objekt gleich die angegebene Variante.

```
bool operator==(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Hinweise

Gibt "true" zurück, wenn der Wert und Typ des *VarSrc* gleich dem Wert und Typ, jeweils die `CComVariant` Objekt. Andernfalls "false". Der Operator verwendet Standard-Gebietsschema des Benutzers zum Ausführen des Vergleichs an.

Der Operator vergleicht nur den Wert der variant-Typen. Es vergleicht Zeichenfolgen, Ganzzahlen und unverankerte verweist, jedoch keine Arrays oder Datensätze.

##  <a name="operator_neq"></a>  CComVariant! =

Gibt an, ob die `CComVariant` Objekt entspricht nicht die angegebene Variante.

```
bool operator!=(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Hinweise

Gibt "true" zurück, wenn entweder der Wert oder den Typ des *VarSrc* entspricht nicht dem Wert oder Typ, von der `CComVariant` Objekt. Andernfalls "false". Der Operator verwendet Standard-Gebietsschema des Benutzers zum Ausführen des Vergleichs an.

Der Operator vergleicht nur den Wert der variant-Typen. Es vergleicht Zeichenfolgen, Ganzzahlen und unverankerte verweist, jedoch keine Arrays oder Datensätze.

##  <a name="operator_lt"></a>  CComVariant &lt;

Gibt an, ob die `CComVariant` Objekt ist kleiner als die angegebene Variante.

```
bool operator<(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Hinweise

Gibt "true" zurück, wenn der Wert des der `CComVariant` Objekt ist kleiner als der Wert des *VarSrc*. Andernfalls "false". Der Operator verwendet Standard-Gebietsschema des Benutzers zum Ausführen des Vergleichs an.

##  <a name="operator_gt"></a>  CComVariant &gt;

Gibt an, ob die `CComVariant` -Quellobjekt ist größer als die angegebene Variante.

```
bool operator>(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Hinweise

Gibt "true" zurück, wenn der Wert des der `CComVariant` -Quellobjekt ist größer als der Wert des *VarSrc*. Andernfalls "false". Der Operator verwendet Standard-Gebietsschema des Benutzers zum Ausführen des Vergleichs an.

##  <a name="readfromstream"></a>  CComVariant::ReadFromStream

Legt fest, die zugrunde liegende Variante auf die Variante, die in den angegebenen Stream enthalten sind.

```
HRESULT ReadFromStream(IStream* pStream);
```

### <a name="parameters"></a>Parameter

*pStream*<br/>
[in] Ein Zeiger auf die [IStream](/windows/desktop/api/objidl/nn-objidl-istream) Schnittstelle für den Stream, der die Daten enthält.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

`ReadToStream` erfordert einen vorherigen Aufruf [WriteToStream](#writetostream).

##  <a name="setbyref"></a>  CComVariant::SetByRef

Initialisiert die `CComVariant` -Objekt und legt die `vt` VT_BYREF Member.

```
template < typename T >
void SetByRef(T* pT) throw();
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ des Variant-Wert, z. B. BSTR, **Int**, oder **Char**.

*pT*<br/>
Der Zeiger, der zum Initialisieren der `CComVariant` Objekt.

### <a name="remarks"></a>Hinweise

`SetByRef` Eine Funktionsvorlage, die initialisiert die `CComVariant` Objekt, das der Zeiger *pT* und legt die `vt` Member VT_BYREF. Zum Beispiel:

[!code-cpp[NVC_ATL_Utilities#76](../../atl/codesnippet/cpp/ccomvariant-class_1.cpp)]

##  <a name="writetostream"></a>  CComVariant:: WriteToStream

Speichert die zugrunde liegende Variante in einem Stream.

```
HRESULT WriteToStream(IStream* pStream);
```

### <a name="parameters"></a>Parameter

*pStream*<br/>
[in] Ein Zeiger auf die [IStream](/windows/desktop/api/objidl/nn-objidl-istream) Schnittstelle für einen Datenstrom.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)