---
title: CComVariant-Klasse
ms.date: 11/04/2016
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
helpviewer_keywords:
- VARIANT macro
- CComVariant class
- VARIANT macro, ATL
ms.assetid: 4d31149c-d005-44b5-a509-10f84afa2b61
ms.openlocfilehash: b4c157435aaffab5f1315fd4636f55f9d4e0d5b4
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496862"
---
# <a name="ccomvariant-class"></a>CComVariant-Klasse

Diese Klasse umschließt den Variant-Typ und stellt einen Member bereit, der den Typ der gespeicherten Daten angibt.

## <a name="syntax"></a>Syntax

```cpp
class CComVariant : public tagVARIANT
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComVariant::CComVariant](#ccomvariant)|Der Konstruktor.|
|[CComVariant::~CComVariant](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComVariant::Attach](#attach)|Fügt eine Variante an das `CComVariant` -Objekt an.|
|[CComVariant::ChangeType](#changetype)|Konvertiert das `CComVariant` -Objekt in einen neuen Typ.|
|[CComVariant::Clear](#clear)|Löscht das `CComVariant` -Objekt.|
|[CComVariant::Copy](#copy)|Kopiert eine Variante in das `CComVariant` -Objekt.|
|[CComVariant::CopyTo](#copyto)|Kopiert den Inhalt des `CComVariant` -Objekts.|
|[CComVariant::Detach](#detach)|Trennt die zugrunde liegende Variante vom `CComVariant` -Objekt.|
|[CComVariant::GetSize](#getsize)|Gibt die Größe in Byte für den Inhalt `CComVariant` des-Objekts zurück.|
|[CComVariant::ReadFromStream](#readfromstream)|Lädt eine Variante aus einem Stream.|
|[CComVariant::SetByRef](#setbyref)|Initialisiert das `CComVariant` -Objekt und legt `vt` das-Element auf VT_BYREF fest.|
|[CComVariant::WriteToStream](#writetostream)|Speichert die zugrunde liegende Variante in einem Stream.|

### <a name="public-operators"></a>Öffentliche Operatoren

|||
|-|-|
|[CComVariant:: Operator <](#operator_lt)|Gibt an, `CComVariant` ob das Objekt kleiner als der angegebene Variant ist.|
|[CComVariant:: Operator >](#operator_gt)|Gibt an, `CComVariant` ob das Objekt größer als der angegebene Variant ist.|
|[Operator! =](#operator_neq)|Gibt an, `CComVariant` ob das Objekt dem angegebenen Variant nicht entspricht.|
|[operator =](#operator_eq)|Weist dem `CComVariant` -Objekt einen Wert zu.|
|[operator ==](#operator_eq_eq)|Gibt an, `CComVariant` ob das Objekt dem angegebenen Variant-Objekt gleicht.|

## <a name="remarks"></a>Hinweise

`CComVariant`umschließt den Variant-und VARIANTARG-Typ, der aus einer Union und einem Member besteht, der den Typ der in der Union gespeicherten Daten angibt. Varianten werden in der Regel in Automation verwendet.

`CComVariant`wird vom Variant-Typ abgeleitet, sodass er überall dort verwendet werden kann, wo ein Variant verwendet werden kann. Sie können z. b. das V_VT-Makro verwenden, um den Typ eines `CComVariant` zu extrahieren, oder Sie `vt` können direkt auf den Member zugreifen, genauso wie bei einem Variant.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`tagVARIANT`

`CComVariant`

## <a name="requirements"></a>Anforderungen

**Header:** atlcomcli. h

##  <a name="attach"></a>CComVariant:: Attach

Löscht den aktuellen Inhalt des `CComVariant` Objekts sicher, kopiert den Inhalt von *psrc* in dieses Objekt und legt dann den Variant-Typ von *psrc* auf VT_EMPTY fest.

```
HRESULT Attach(VARIANT* pSrc);
```

### <a name="parameters"></a>Parameter

*pSrc*<br/>
in Verweist auf die [Variante](/windows/win32/api/oaidl/ns-oaidl-variant) , die an das-Objekt angefügt werden soll.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

### <a name="remarks"></a>Hinweise

Der Besitz der von *psrc* gehaltenen Daten wird auf das `CComVariant` -Objekt übertragen.

##  <a name="ccomvariant"></a>CComVariant:: CComVariant

Jeder Konstruktor verarbeitet die sichere Initialisierung des `CComVariant` Objekts durch Aufrufen der `VariantInit` Win32-Funktion oder durch Festlegen des Werts und Typs des Objekts gemäß den bestandenen Parametern.

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
in Der `CComVariant` -oder-Variant, der zum `CComVariant` Initialisieren des Objekts verwendet wird. Der Inhalt der Quell Variante wird ohne Konvertierung in das Ziel kopiert.

*lpszSrc*<br/>
in Die Zeichenfolge, die zum Initialisieren `CComVariant` des-Objekts verwendet wird. Sie können eine NULL-terminierte Breite (Unicode)-Zeichenfolge an die lpcolestr-Version des Konstruktors oder eine ANSI-Zeichenfolge an die LPCSTR-Version übergeben. In beiden Fällen wird die Zeichenfolge in ein mit `SysAllocString`zugeordneter Unicode BSTR konvertiert. Der Typ des `CComVariant` Objekts ist VT_BSTR.

*bSrc*<br/>
in Der boolesche, der zum Initialisieren des `CComVariant` Objekts verwendet wird. Das **bool** -Argument wird vor der Speicherung in VARIANT_BOOL konvertiert. Der Typ des `CComVariant` Objekts ist VT_BOOL.

*nSrc*<br/>
in Int, **Byte**, **Short**, **Long**, Longlong, ULONGLONG, **Ganzzahl ohne Vorzeichen Short**, **Ganzzahl ohne Vorzeichen long**oder **Ganzzahl ohne Vorzeichen int** , der zum Initialisieren des `CComVariant` Objekts verwendet wird. Der Typ des `CComVariant` Objekts ist VT_I4, VT_UI1, VT_I2, VT_I4, VT_I8, VT_UI8, VT_UI2, VT_UI4 bzw. VT_UI4.

*vtSrc*<br/>
in Der Typ der Variante. Wenn der erste Parameter **int**ist, sind gültige Typen VT_I4 und VT_INT. Wenn der erste Parameter **lang**ist, sind gültige Typen VT_I4 und VT_ERROR. Wenn der erste Parameter **Double**ist, sind gültige Typen VT_R8 und VT_DATE. Wenn der erste Parameter **Ganzzahl ohne Vorzeichen int**ist, sind gültige Typen VT_UI4 und VT_UINT.

*fltSrc*<br/>
in Der **float** -Wert, der zum `CComVariant` Initialisieren des Objekts verwendet wird. Der Typ des `CComVariant` Objekts ist VT_R4.

*dblSrc*<br/>
in Der **Double** -, der zum Initialisieren des `CComVariant` -Objekts verwendet wird. Der Typ des `CComVariant` Objekts ist VT_R8.

*cySrc*<br/>
in Der `CY` , der zum Initialisieren `CComVariant` des-Objekts verwendet wird. Der Typ des `CComVariant` Objekts ist VT_CY.

*pSrc*<br/>
in Der `IDispatch` - `IUnknown` oder-Zeiger, der zum `CComVariant` Initialisieren des Objekts verwendet wird. `AddRef`wird für den Schnittstellen Zeiger aufgerufen. Der Typ des `CComVariant` Objekts ist VT_DISPATCH bzw. VT_UNKNOWN.

Oder der saferray-Zeiger, der zum Initialisieren `CComVariant` des Objekts verwendet wird. Eine Kopie von SAFEARRAY wird im `CComVariant` -Objekt gespeichert. Der Typ des `CComVariant` Objekts wird eine Kombination aus dem ursprünglichen Typ von SAFEARRAY und VT_ARRAY sein.

*cSrc*<br/>
in Das Zeichen, das zum Initialisieren `CComVariant` des-Objekts verwendet wird. Der Typ des `CComVariant` Objekts ist VT_I1.

*bstrSrc*<br/>
in Der BSTR, der zum Initialisieren `CComVariant` des-Objekts verwendet wird. Der Typ des `CComVariant` Objekts ist VT_BSTR.

### <a name="remarks"></a>Hinweise

Der Dekonstruktor verwaltet die Bereinigung durch Aufrufen von [CComVariant:: Clear](#clear).

##  <a name="dtor"></a>CComVariant:: ~ CComVariant

Der Destruktor.

```
~CComVariant() throw();
```

### <a name="remarks"></a>Hinweise

Diese Methode verwaltet die Bereinigung durch Aufrufen von [CComVariant:: Clear](#clear).

##  <a name="changetype"></a>CComVariant:: ChangeType

Konvertiert das `CComVariant` -Objekt in einen neuen Typ.

```
HRESULT ChangeType(VARTYPE vtNew, const VARIANT* pSrc = NULL);
```

### <a name="parameters"></a>Parameter

*vtNew*<br/>
in Der neue Typ für das `CComVariant` -Objekt.

*pSrc*<br/>
in Ein Zeiger auf die Variante, deren Wert in den neuen Typ konvertiert wird. Der Standardwert ist NULL, was bedeutet `CComVariant` , dass das Objekt direkt konvertiert wird.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

### <a name="remarks"></a>Hinweise

Wenn Sie einen Wert für *psrc*übergeben, `ChangeType` wird diese Variante von als Quelle für die Konvertierung verwendet. Andernfalls wird das `CComVariant` Objekt als Quelle verwendet.

##  <a name="clear"></a>CComVariant:: Clear

Löscht das `CComVariant` -Objekt, indem `VariantClear` die Win32-Funktion aufgerufen wird.

```
HRESULT Clear();
```

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

### <a name="remarks"></a>Hinweise

Der Dekonstruktor ruft `Clear`automatisch auf.

##  <a name="copy"></a>CComVariant:: Copy

Gibt das `CComVariant` -Objekt frei und weist diesem dann eine Kopie der angegebenen Variante zu.

```
HRESULT Copy(const VARIANT* pSrc);
```

### <a name="parameters"></a>Parameter

*pSrc*<br/>
in Ein Zeiger auf die zu kopierende [Variante](/windows/win32/api/oaidl/ns-oaidl-variant) .

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

##  <a name="copyto"></a>CComVariant:: CopyTo

Kopiert den Inhalt des `CComVariant` -Objekts.

```
HRESULT CopyTo(BSTR* pstrDest);
```

### <a name="parameters"></a>Parameter

*pstrDest*<br/>
Verweist auf ein BSTR, das eine Kopie des Inhalts des `CComVariant` -Objekts empfängt.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

### <a name="remarks"></a>Hinweise

Das `CComVariant` Objekt muss den Typ "VT_BSTR" aufweisen.

##  <a name="detach"></a>CComVariant::D Etach

Trennt die zugrunde liegende Variante vom `CComVariant` -Objekt und legt den Typ des-Objekts auf VT_EMPTY fest.

```
HRESULT Detach(VARIANT* pDest);
```

### <a name="parameters"></a>Parameter

*pDest*<br/>
vorgenommen Gibt den zugrunde liegenden Variant-Wert des-Objekts zurück.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

### <a name="remarks"></a>Hinweise

Beachten Sie, dass der Inhalt der Variant, auf die von *pdest* verwiesen wird, automatisch gelöscht wird, bevor ihm der Wert `CComVariant` und der Typ des aufrufenden Objekts zugewiesen werden.

##  <a name="getsize"></a>CComVariant:: GetSize

Bei Varianten mit einfacher fester Größe gibt diese Methode den **sizeof** des zugrunde liegenden Datentyps Plus **sizeof (VarType)** zurück.

```
ULONG GetSize() const;
```

### <a name="return-value"></a>Rückgabewert

Die Größe des aktuellen Inhalts des `CComVariant` -Objekts in Bytes.

### <a name="remarks"></a>Hinweise

Wenn die Variante einen Schnittstellen Zeiger enthält, `GetSize` werden Abfragen `IPersistStream` für `IPersistStreamInit`oder. Bei erfolgreicher Ausführung ist der Rückgabewert die nieder wertigen 32 Bits des Werts, der von `GetSizeMax` zurückgegeben wird, zuzüglich der **sizeof** a CLSID und **sizeof (VarType)** . Wenn der Schnittstellen Zeiger NULL ist, `GetSize` wird der **sizeof** einer CLSID plus **sizeof (VarType)** zurückgegeben. Wenn die Gesamtgröße größer als ULONG_MAX ist, `GetSize` wird **sizeof (VarType)** zurückgegeben, das auf einen Fehler hinweist.

In allen anderen Fällen wird eine temporäre Variante vom Typ VT_BSTR aus der aktuellen Variante erzwungen. Die Länge dieses BSTR wird als Größe der Länge der Zeichenfolge zuzüglich der Länge der Zeichenfolge selbst zuzüglich der Größe des NULL-Zeichens Plus **sizeof (VarType)** berechnet. Wenn der Variant nicht in eine Variante vom Typ VT_BSTR umgewandelt werden kann, `GetSize` wird **sizeof (VarType)** zurückgegeben.

Die von dieser Methode zurückgegebene Größe entspricht der Anzahl der Bytes, die von [CComVariant:: Write-to-Stream](#writetostream) unter erfolgreichen Bedingungen verwendet werden.

##  <a name="operator_eq"></a>CComVariant:: Operator =

Weist dem-Objekt einen Wert und den `CComVariant` entsprechenden Typ zu.

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
in Die `CComVariant` -oder- [Variante](/windows/win32/api/oaidl/ns-oaidl-variant) , die dem `CComVariant` -Objekt zugewiesen werden soll. Der Inhalt der Quell Variante wird ohne Konvertierung in das Ziel kopiert.

*bstrSrc*<br/>
in Der BSTR, der dem `CComVariant` -Objekt zugewiesen werden soll. Der Typ des `CComVariant` Objekts ist VT_BSTR.

*lpszSrc*<br/>
in Die Zeichenfolge, die dem `CComVariant` -Objekt zugewiesen werden soll. Sie können eine NULL-terminierte Breite (Unicode)-Zeichenfolge an die lpcolestr-Version des Operators oder eine ANSI-Zeichenfolge an die LPCSTR-Version übergeben. In beiden Fällen wird die Zeichenfolge in ein mit `SysAllocString`zugeordneter Unicode BSTR konvertiert. Der Typ des `CComVariant` Objekts ist VT_BSTR.

*bSrc*<br/>
in Der boolesche, der dem `CComVariant` -Objekt zugewiesen werden soll. Das **bool** -Argument wird vor der Speicherung in VARIANT_BOOL konvertiert. Der Typ des `CComVariant` Objekts ist VT_BOOL.

*nSrc*<br/>
in Int, Byte, **Short**, **Long**, Longlong, ULONGLONG, **Ganzzahl ohne Vorzeichen Short**, **Ganzzahl ohne Vorzeichen long**oder **Ganzzahl ohne Vorzeichen int** , die dem `CComVariant` -Objekt zugewiesen werden sollen. Der Typ des `CComVariant` Objekts ist VT_I4, VT_UI1, VT_I2, VT_I4, VT_I8, VT_UI8, VT_UI2, VT_UI4 bzw. VT_UI4.

*fltSrc*<br/>
in Der **float** -Wert, der dem `CComVariant` -Objekt zugewiesen werden soll. Der Typ des `CComVariant` Objekts ist VT_R4.

*dblSrc*<br/>
in Der **Double** -, der dem `CComVariant` -Objekt zugewiesen werden soll. Der Typ des `CComVariant` Objekts ist VT_R8.

*cySrc*<br/>
in Das `CY` , das dem `CComVariant` -Objekt zugewiesen werden soll. Der Typ des `CComVariant` Objekts ist VT_CY.

*pSrc*<br/>
in Der `IDispatch` - `IUnknown` oder-Zeiger, der dem `CComVariant` -Objekt zugewiesen werden soll. `AddRef`wird für den Schnittstellen Zeiger aufgerufen. Der Typ des `CComVariant` Objekts ist VT_DISPATCH bzw. VT_UNKNOWN.

Oder, ein SAFEARRAY-Zeiger, der dem `CComVariant` -Objekt zugewiesen werden soll. Eine Kopie von SAFEARRAY wird im `CComVariant` -Objekt gespeichert. Der Typ des `CComVariant` Objekts wird eine Kombination aus dem ursprünglichen Typ von SAFEARRAY und VT_ARRAY sein.

*cSrc*<br/>
in Das Char, das dem `CComVariant` -Objekt zugewiesen werden soll. Der Typ des `CComVariant` Objekts ist VT_I1.

##  <a name="operator_eq_eq"></a>CComVariant:: Operator = =

Gibt an, `CComVariant` ob das Objekt dem angegebenen Variant-Objekt gleicht.

```
bool operator==(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Hinweise

Gibt true zurück, wenn der Wert und der Typ von *varSrc* gleich dem Wert bzw. dem Typ des `CComVariant` Objekts sind. Andernfalls false. Der-Operator verwendet das Standard Gebiets Schema des Benutzers, um den Vergleich durchzuführen.

Der-Operator vergleicht nur den Wert der Variant-Typen. Es vergleicht Zeichen folgen, ganze Zahlen und Gleit Komma Zahlen, aber keine Arrays oder Datensätze.

##  <a name="operator_neq"></a>CComVariant:: Operator! =

Gibt an, `CComVariant` ob das Objekt dem angegebenen Variant nicht entspricht.

```
bool operator!=(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Hinweise

Gibt true zurück, wenn entweder der Wert oder der Typ von *varSrc* nicht gleich dem Wert bzw. Typ des `CComVariant` Objekts ist. Andernfalls false. Der-Operator verwendet das Standard Gebiets Schema des Benutzers, um den Vergleich durchzuführen.

Der-Operator vergleicht nur den Wert der Variant-Typen. Es vergleicht Zeichen folgen, ganze Zahlen und Gleit Komma Zahlen, aber keine Arrays oder Datensätze.

##  <a name="operator_lt"></a>CComVariant::-Operator&lt;

Gibt an, `CComVariant` ob das Objekt kleiner als der angegebene Variant ist.

```
bool operator<(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Hinweise

Gibt true zurück, wenn der Wert `CComVariant` des-Objekts kleiner als der Wert von *varSrc*ist. Andernfalls false. Der-Operator verwendet das Standard Gebiets Schema des Benutzers, um den Vergleich durchzuführen.

##  <a name="operator_gt"></a>CComVariant::-Operator&gt;

Gibt an, `CComVariant` ob das Objekt größer als der angegebene Variant ist.

```
bool operator>(const VARIANT& varSrc) const throw();
```

### <a name="remarks"></a>Hinweise

Gibt true zurück, wenn der Wert `CComVariant` des-Objekts größer als der Wert von *varSrc*ist. Andernfalls false. Der-Operator verwendet das Standard Gebiets Schema des Benutzers, um den Vergleich durchzuführen.

##  <a name="readfromstream"></a>CComVariant:: Read FromStream

Legt die zugrunde liegende Variante auf die im angegebenen Stream enthaltene Variante fest.

```
HRESULT ReadFromStream(IStream* pStream);
```

### <a name="parameters"></a>Parameter

*pStream*<br/>
in Ein Zeiger auf die [IStream](/windows/win32/api/objidl/nn-objidl-istream) -Schnittstelle im Stream, der die Daten enthält.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

### <a name="remarks"></a>Hinweise

`ReadToStream`erfordert einen vorherigen-Befehl von " [Write-tostream](#writetostream)".

##  <a name="setbyref"></a>CComVariant:: setbyref

Initialisiert das `CComVariant` -Objekt und legt `vt` das-Element auf VT_BYREF fest.

```
template < typename T >
void SetByRef(T* pT) throw();
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ der Variante, z. b. BSTR, **int**oder **char**.

*pT*<br/>
Der Zeiger, der zum Initialisieren `CComVariant` des-Objekts verwendet wird.

### <a name="remarks"></a>Hinweise

`SetByRef`ist eine Funktions Vorlage, die das `CComVariant` -Objekt mit dem Zeiger *PT* initialisiert und `vt` den Member auf VT_BYREF festlegt. Beispiel:

[!code-cpp[NVC_ATL_Utilities#76](../../atl/codesnippet/cpp/ccomvariant-class_1.cpp)]

##  <a name="writetostream"></a>CComVariant:: Write-to-Stream

Speichert die zugrunde liegende Variante in einem Stream.

```
HRESULT WriteToStream(IStream* pStream);
```

### <a name="parameters"></a>Parameter

*pStream*<br/>
in Ein Zeiger auf die [IStream](/windows/win32/api/objidl/nn-objidl-istream) -Schnittstelle in einem Stream.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)
