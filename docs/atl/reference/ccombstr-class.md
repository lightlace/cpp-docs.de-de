---
title: CComBSTR-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComBSTR
- ATLBASE/ATL::CComBSTR
- ATLBASE/ATL::CComBSTR::CComBSTR
- ATLBASE/ATL::CComBSTR::Append
- ATLBASE/ATL::CComBSTR::AppendBSTR
- ATLBASE/ATL::CComBSTR::AppendBytes
- ATLBASE/ATL::CComBSTR::ArrayToBSTR
- ATLBASE/ATL::CComBSTR::AssignBSTR
- ATLBASE/ATL::CComBSTR::Attach
- ATLBASE/ATL::CComBSTR::BSTRToArray
- ATLBASE/ATL::CComBSTR::ByteLength
- ATLBASE/ATL::CComBSTR::Copy
- ATLBASE/ATL::CComBSTR::CopyTo
- ATLBASE/ATL::CComBSTR::Detach
- ATLBASE/ATL::CComBSTR::Empty
- ATLBASE/ATL::CComBSTR::Length
- ATLBASE/ATL::CComBSTR::LoadString
- ATLBASE/ATL::CComBSTR::ReadFromStream
- ATLBASE/ATL::CComBSTR::ToLower
- ATLBASE/ATL::CComBSTR::ToUpper
- ATLBASE/ATL::CComBSTR::WriteToStream
- ATLBASE/ATL::CComBSTR::m_str
helpviewer_keywords:
- BSTRs, wrapper
- CComBSTR class
- CComBSTR
ms.assetid: 8fea1879-a05e-47a5-a803-8dec60eaa534
ms.openlocfilehash: 52e8472e315932978af38d405c753b0a62fcbe45
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475646"
---
# <a name="ccombstr-class"></a>CComBSTR-Klasse

Diese Klasse ist ein Wrapper für [BSTR](/previous-versions/windows/desktop/automat/bstr)s.

## <a name="syntax"></a>Syntax

```
class CComBSTR
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComBSTR::CComBSTR](#ccombstr)|Der Konstruktor.|
|[CComBSTR:: ~ CComBSTR](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComBSTR::Append](#append)|Fügt eine Zeichenfolge, die `m_str`.|
|[CComBSTR::AppendBSTR](#appendbstr)|Fügt eine BSTR an `m_str`.|
|[CComBSTR::AppendBytes](#appendbytes)|Fügt eine angegebene Anzahl von Bytes, `m_str`.|
|[CComBSTR::ArrayToBSTR](#arraytobstr)|Erstellt einen BSTR vom ersten Zeichen der einzelnen Elemente im Safearray und fügt es der `CComBSTR` Objekt.|
|[CComBSTR::AssignBSTR](#assignbstr)|Weist eine BSTR an `m_str`.|
|[CComBSTR::Attach](#attach)|Fügt eine BSTR an den `CComBSTR` Objekt.|
|[CComBSTR::BSTRToArray](#bstrtoarray)|Erstellt ein nullbasierte eindimensionale Safearray, wobei jedes Element des Arrays ist ein Zeichen aus dem `CComBSTR` Objekt.|
|[CComBSTR::ByteLength](#bytelength)|Gibt die Länge des `m_str` in Byte.|
|[CComBSTR::Copy](#copy)|Gibt eine Kopie des `m_str`.|
|[CComBSTR::CopyTo](#copyto)|Gibt eine Kopie des `m_str` über eine **[Out]** Parameter|
|[CComBSTR::Detach](#detach)|Trennt `m_str` aus der `CComBSTR` Objekt.|
|[CComBSTR::Empty](#empty)|Frei `m_str`.|
|[CComBSTR::Length](#length)|Gibt die Länge des `m_str`.|
|[CComBSTR::LoadString](#loadstring)|Lädt eine Zeichenfolgenressource.|
|[CComBSTR::ReadFromStream](#readfromstream)|Lädt eine BSTR-Objekt aus einem Stream.|
|[CComBSTR::ToLower](#tolower)|Konvertiert die Zeichenfolge in Kleinbuchstaben.|
|[CComBSTR::ToUpper](#toupper)|Konvertiert die Zeichenfolge in Großbuchstaben.|
|[CComBSTR::WriteToStream](#writetostream)|Speichert `m_str` in einen Stream.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CComBSTR::operator BSTR](#operator_bstr)|Wandelt eine `CComBSTR` Objekt auf ein BSTR.|
|[CComBSTR::operator!](#operator_not)|Gibt "true" oder "false", je nachdem, ob `m_str`ist NULL.|
|[CComBSTR::operator! =](#operator_neq)|Vergleicht einen `CComBSTR` mit einer Zeichenfolge.|
|[CComBSTR::operator &](#operator_amp)|Gibt die Adresse der `m_str`.|
|[CComBSTR::operator +=](#operator_add_eq)|Fügt eine `CComBSTR` auf das Objekt.|
|[CComBSTR::operator <](#operator_lt)|Vergleicht einen `CComBSTR` mit einer Zeichenfolge.|
|[CComBSTR::operator =](#operator_eq)|Ein Wert zugewiesen `m_str`.|
|[CComBSTR::operator ==](#operator_eq_eq)|Vergleicht einen `CComBSTR` mit einer Zeichenfolge.|
|[CComBSTR::operator >](#operator_gt)|Vergleicht einen `CComBSTR` mit einer Zeichenfolge.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CComBSTR::m_str](#m_str)|Enthält die zugeordneten BSTR-Wert der `CComBSTR` Objekt.|

## <a name="remarks"></a>Hinweise

Die `CComBSTR` Klasse ist ein Wrapper für BSTR, das Längenpräfix Zeichenfolgen sind. Die Länge wird als eine ganze Zahl an der Speicheradresse, die die Daten in der Zeichenfolge vor gespeichert.

Ein [BSTR](/previous-versions/windows/desktop/automat/bstr) ist Null-terminierte nach dem letzten Zeichen gezählt werden jedoch möglicherweise auch in die Zeichenfolge eingebettete Null-Zeichen enthalten. Die Länge der Zeichenfolge wird durch die Anzahl der Zeichen, nicht der ersten Null-Zeichen bestimmt.

> [!NOTE]
>  Die `CComBSTR` -Klasse bietet eine Anzahl von Elementen (Konstruktoren, Zuweisungsoperatoren und Vergleichsoperatoren), die entweder als ANSI- oder Unicode-Zeichenfolgen als Argumente annehmen. Die ANSI-Versionen dieser Funktionen sind weniger effizient als ihre Gegenstücke Unicode, da temporäre Unicode-Zeichenfolgen intern häufig erstellt werden. Aus Effizienzgründen verwenden Sie möglichst die Unicode-Versionen.

> [!NOTE]
>  Aufgrund der verbesserten Suchverhalten, die in Visual Studio .NET implementiert, z. B. code `bstr = L"String2" + bstr;`, die in früheren Versionen kompiliert haben möglicherweise sollte stattdessen implementiert werden, als `bstr = CStringW(L"String2") + bstr`.

Eine Liste mit Vorsichtsmaßnahmen, die Verwendung von `CComBSTR`, finden Sie unter [Programmieren mit CComBSTR](../../atl/programming-with-ccombstr-atl.md).

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="append"></a>  CComBSTR::Append

Fügt eine *Lpsz* oder das BSTR-Mitglied *BstrSrc* zu [M_str](#m_str).

```
HRESULT Append(const CComBSTR& bstrSrc) throw();
HRESULT Append(wchar_t ch) throw();
HRESULT Append(char ch) throw();
HRESULT Append(LPCOLESTR lpsz) throw();
HRESULT Append(LPCSTR lpsz) throw();
HRESULT Append(LPCOLESTR lpsz, int nLen) throw();
```

### <a name="parameters"></a>Parameter

*bstrSrc*<br/>
[in] Ein `CComBSTR` anzufügende Objekt.

*ch*<br/>
[in] Ein Zeichen, angefügt werden soll.

*lpsz*<br/>
[in] Eine NULL-terminierte Zeichenfolge angefügt. Sie können eine Unicode-Zeichenfolge über die Überladung LPCOLESTR oder über die Version LPCSTR eine ANSI-Zeichenfolge übergeben.

*nLen*<br/>
[in] Die Anzahl von Zeichen aus *Lpsz* , angefügt werden soll.

### <a name="return-value"></a>Rückgabewert

S_OK bei Erfolg oder einen standard HRESULT-Fehlerwert.

### <a name="remarks"></a>Hinweise

Eine ANSI-Zeichenfolge wird in Unicode konvertiert werden, bevor angefügt wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#32](../../atl/codesnippet/cpp/ccombstr-class_1.cpp)]

##  <a name="appendbstr"></a>  CComBSTR::AppendBSTR

Fügt der angegebene BSTR [M_str](#m_str).

```
HRESULT AppendBSTR(BSTR p) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
[in] BSTR, angefügt werden soll.

### <a name="return-value"></a>Rückgabewert

S_OK bei Erfolg oder einen standard HRESULT-Fehlerwert.

### <a name="remarks"></a>Hinweise

Übergeben Sie an diese Methode keine gewöhnliche Zeichenfolge mit Breitzeichen. Der Compiler kann nicht den Fehler abfangen und zur Laufzeit, die der Fehler auftreten.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#33](../../atl/codesnippet/cpp/ccombstr-class_2.cpp)]

##  <a name="appendbytes"></a>  CComBSTR::AppendBytes

Fügt die angegebene Anzahl von Bytes, die [M_str](#m_str) ohne Konvertierung.

```
HRESULT AppendBytes(const char* lpsz, int nLen) throw();
```

### <a name="parameters"></a>Parameter

*lpsz*<br/>
[in] Ein Zeiger auf ein Array von Bytes, angefügt werden soll.

*p*<br/>
[in] Die Anzahl der Bytes, angefügt werden soll.

### <a name="return-value"></a>Rückgabewert

S_OK bei Erfolg oder einen standard HRESULT-Fehlerwert.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#34](../../atl/codesnippet/cpp/ccombstr-class_3.cpp)]

##  <a name="arraytobstr"></a>  CComBSTR::ArrayToBSTR

Frei vorhandene Zeichenfolgen frei, die der `CComBSTR` Objekt, klicken Sie dann einen BSTR vom ersten Zeichen der einzelnen Elemente im Safearray erstellt und fügt es der `CComBSTR` Objekt.

```
HRESULT ArrayToBSTR(const SAFEARRAY* pSrc) throw();
```

### <a name="parameters"></a>Parameter

*pSrc*<br/>
[in] Das Safearray, das mit den Elementen verwendet, um die Zeichenfolge zu erstellen.

### <a name="return-value"></a>Rückgabewert

S_OK bei Erfolg oder einen standard HRESULT-Fehlerwert.

##  <a name="assignbstr"></a>  CComBSTR::AssignBSTR

Weist eine BSTR an [M_str](#m_str).

```
HRESULT AssignBSTR(const BSTR bstrSrc) throw();
```

### <a name="parameters"></a>Parameter

*bstrSrc*<br/>
[in] BSTR mit dem aktuellen zuweisen `CComBSTR` Objekt.

### <a name="return-value"></a>Rückgabewert

S_OK bei Erfolg oder einen standard HRESULT-Fehlerwert.

##  <a name="attach"></a>  CComBSTR::Attach

Fügt eine BSTR an den `CComBSTR` Objekt durch Festlegen der [M_str](#m_str) Member *Src*.

```
void Attach(BSTR src) throw();
```

### <a name="parameters"></a>Parameter

*src*<br/>
[in] BSTR an das Objekt anzufügen.

### <a name="remarks"></a>Hinweise

Übergeben Sie an diese Methode keine gewöhnliche Zeichenfolge mit Breitzeichen. Der Compiler kann nicht den Fehler abfangen und zur Laufzeit, die der Fehler auftreten.

> [!NOTE]
>  Wenn diese Methode bestätigt `m_str` ungleich NULL ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]

##  <a name="bstrtoarray"></a>  CComBSTR::BSTRToArray

Erstellt ein nullbasierte eindimensionale Safearray, wobei jedes Element des Arrays ist ein Zeichen aus dem `CComBSTR` Objekt.

```
HRESULT BSTRToArray(LPSAFEARRAY* ppArray) throw();
```

### <a name="parameters"></a>Parameter

*ppArray*<br/>
[out] Der Zeiger auf die Safearray verwendet, um die Ergebnisse der Funktion zu speichern.

### <a name="return-value"></a>Rückgabewert

S_OK bei Erfolg oder einen standard HRESULT-Fehlerwert.

##  <a name="bytelength"></a>  CComBSTR::ByteLength

Gibt die Anzahl der Bytes im `m_str`, ausgenommen das abschließende Nullzeichen.

```
unsigned int ByteLength() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die Länge der [M_str](#m_str) Elements in Bytes.

### <a name="remarks"></a>Hinweise

Gibt 0 zurück, wenn `m_str` ist NULL.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#36](../../atl/codesnippet/cpp/ccombstr-class_5.cpp)]

##  <a name="ccombstr"></a>  CComBSTR::CComBSTR

Der Konstruktor. Die Standard-Konstruktor legt die [M_str](#m_str) Datenmember auf NULL.

```
CComBSTR() throw();
CComBSTR(const CComBSTR& src);
CComBSTR(REFGUID  guid);
CComBSTR(int nSize);
CComBSTR(int nSize, LPCOLESTR sz);
CComBSTR(int nSize, LPCSTR sz);
CComBSTR(LPCOLESTR pSrc);
CComBSTR(LPCSTR pSrc);
CComBSTR(CComBSTR&& src) throw(); // (Visual Studio 2017)
```

### <a name="parameters"></a>Parameter

*nSize*<br/>
[in] Die Anzahl der zu kopierenden Zeichen aus *Sz* oder die ursprüngliche Größe in Zeichen für die `CComBSTR`.

*sz*<br/>
[in] Eine zu kopierende Zeichenfolge. Die Unicodeversion gibt an, eine LPCOLESTR; die ANSI-Version gibt ein LPCSTR an.

*pSrc*<br/>
[in] Eine zu kopierende Zeichenfolge. Die Unicodeversion gibt an, eine LPCOLESTR; die ANSI-Version gibt ein LPCSTR an.

*src*<br/>
[in] Ein `CComBSTR`-Objekt.

*GUID*<br/>
[in] Ein Verweis auf eine `GUID` Struktur.

### <a name="remarks"></a>Hinweise

Der Kopierkonstruktor legt `m_str` auf eine Kopie des BSTR-Elements *Src*. Die `REFGUID` Konstruktor konvertiert die GUID in eine Zeichenfolge mit `StringFromGUID2` und speichert das Ergebnis.

Die anderen Konstruktoren legen `m_str` auf eine Kopie der angegebenen Zeichenfolge fest. Wenn Sie einen Wert, für die übergeben *nSize*, und klicken Sie dann nur *nSize* Zeichen kopiert werden, gefolgt von einer Null-Abschlusszeichen.

`CComBSTR` unterstützt die move-Semantik. Mit dem Bewegungskonstruktor (dem Konstruktor, der einen rvalue-Verweis verwendet (`&&`) können Sie ein neues Objekt erstellen, das die Daten des alten als Argument übergebenen Objekts verwendet, ohne das Objekt kopieren zu müssen.

Der Destruktor gibt die Zeichenfolge frei, auf die von `m_str` gezeigt wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#37](../../atl/codesnippet/cpp/ccombstr-class_6.cpp)]

##  <a name="dtor"></a>  CComBSTR:: ~ CComBSTR

Der Destruktor.

```
~CComBSTR();
```

### <a name="remarks"></a>Hinweise

Der Destruktor gibt die Zeichenfolge frei, auf die von `m_str` gezeigt wird.

##  <a name="copy"></a>  CComBSTR::Copy

Belegt und gibt eine Kopie des `m_str`.

```
BSTR Copy() const throw();
```

### <a name="return-value"></a>Rückgabewert

Eine Kopie der [M_str](#m_str) Member. Wenn `m_str` NULL ist, wird NULL zurückgegeben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#38](../../atl/codesnippet/cpp/ccombstr-class_7.cpp)]

##  <a name="copyto"></a>  CComBSTR::CopyTo

Belegt und gibt eine Kopie des [M_str](#m_str) über den Parameter.

```
HRESULT CopyTo(BSTR* pbstr) throw();

HRESULT CopyTo(VARIANT* pvarDest) throw();
```

### <a name="parameters"></a>Parameter

*pbstr*<br/>
[out] Die Adresse der BSTR in das die Zeichenfolge, die von dieser Methode belegten zurückgegeben.

*pvarDest*<br/>
[out] Die Adresse einer Variante in das die Zeichenfolge, die von dieser Methode belegten zurückgegeben werden soll.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert, der angibt, den Erfolg oder Misserfolg der Kopie.

### <a name="remarks"></a>Hinweise

Nach dem Aufrufen dieser Methode die Variante verweist *PvarDest* vom Typ VT_BSTR.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#39](../../atl/codesnippet/cpp/ccombstr-class_8.cpp)]

##  <a name="detach"></a>  CComBSTR::Detach

Trennt [M_str](#m_str) aus der `CComBSTR` -Objekt und legt `m_str` auf NULL.

```
BSTR Detach() throw();
```

### <a name="return-value"></a>Rückgabewert

BSTR mit verknüpften der `CComBSTR` Objekt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#40](../../atl/codesnippet/cpp/ccombstr-class_9.cpp)]

##  <a name="empty"></a>  CComBSTR::Empty

Gibt frei, die [M_str](#m_str) Member.

```
void Empty() throw();
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#41](../../atl/codesnippet/cpp/ccombstr-class_10.cpp)]

##  <a name="length"></a>  CComBSTR::Length

Gibt die Anzahl der Zeichen in `m_str`, ausgenommen das abschließende Nullzeichen.

```
unsigned int Length() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die Länge der [M_str](#m_str) Member.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#42](../../atl/codesnippet/cpp/ccombstr-class_11.cpp)]

##  <a name="loadstring"></a>  CComBSTR::LoadString

Lädt eine Zeichenfolgenressource, die anhand des *nID* und speichert sie in dieses Objekt.

```
bool LoadString(HINSTANCE hInst, UINT nID) throw();
bool LoadString(UINT nID) throw();
```

### <a name="parameters"></a>Parameter

Finden Sie unter [LoadString](/windows/desktop/api/winuser/nf-winuser-loadstringa) in das Windows SDK.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn die Zeichenfolge erfolgreich geladen wird. Andernfalls wird FALSE zurückgegeben.

### <a name="remarks"></a>Hinweise

Die erste Funktion lädt die Ressource aus dem Modul identifiziert, die von Ihnen über die *hInst* Parameter. Die zweite Funktion lädt die Ressource aus dem zugeordneten Ressourcenmodul die [CComModule](../../atl/reference/ccommodule-class.md)-abgeleitete Objekt, das in diesem Projekt verwendet.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#43](../../atl/codesnippet/cpp/ccombstr-class_12.cpp)]

##  <a name="m_str"></a>  CComBSTR::m_str

Enthält die zugeordneten BSTR-Wert der `CComBSTR` Objekt.

```
BSTR m_str;
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#49](../../atl/codesnippet/cpp/ccombstr-class_13.cpp)]

##  <a name="operator_bstr"></a>  CComBSTR::operator BSTR

Wandelt eine `CComBSTR` Objekt auf ein BSTR.

```
operator BSTR() const throw();
```

### <a name="remarks"></a>Hinweise

Ermöglicht die Übergabe `CComBSTR` Objekte an Funktionen mit **[in] BSTR** Parameter.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CComBSTR::m_str](#m_str).

##  <a name="operator_not"></a>  CComBSTR::operator!

Überprüft, ob die BSTR-Zeichenfolge NULL ist.

```
bool operator!() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn die [M_str](#m_str) Member NULL ist; andernfalls "false".

### <a name="remarks"></a>Hinweise

Dieser Operator überprüft nur einen NULL-Wert, nicht für eine leere Zeichenfolge.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]

##  <a name="operator_neq"></a>  CComBSTR::operator! =

Gibt das logische Gegenteil dieses [Operator ==](#operator_eq_eq).

```
bool operator!= (const CComBSTR& bstrSrc) const throw();
bool operator!= (LPCOLESTR pszSrc) const;
bool operator!= (LPCSTR pszSrc) const;
bool operator!= (int nNull) const throw();
```

### <a name="parameters"></a>Parameter

*bstrSrc*<br/>
[in] Ein `CComBSTR`-Objekt.

*pszSrc*<br/>
[in] Eine 0 (null) endende Zeichenfolge.

*nNull*<br/>
[in] NULL muss sein.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn das Element mit dem verglichen wird, nicht gleich ist die `CComBSTR` -Objekt zurückgegeben; andernfalls "false".

### <a name="remarks"></a>Hinweise

`CComBSTR`s werden textlich im Kontext des Standard-Gebietsschema des Benutzers verglichen. Der endgültige Vergleichsoperator vergleicht lediglich die eingeschlossene Zeichenfolge mit NULL.

##  <a name="operator_amp"></a>  CComBSTR::operator &amp;

Gibt die Adresse des freizugebenden BSTR in gespeicherte zurück die [M_str](#m_str) Member.

```
BSTR* operator&() throw();
```

### <a name="remarks"></a>Hinweise

`CComBstr operator &` verfügt über eine spezielle-Assertion zu helfen, Speicherverluste zu identifizieren, zugeordnet. Das Programm wird bestätigt, wenn die `m_str` Member wird initialisiert. Diese Assertion wurde entwickelt, um die Identifizierung von Situationen, in dem ein Programmierer verwendet, die `& operator` einen neuen Wert zuweisen `m_str` Member ohne Freigabe der ersten Zuordnung des `m_str`. Wenn `m_str` gleich NULL ist, ist das Programm setzt voraus, M_str wurde nicht noch zugeordnet. In diesem Fall wird das Programm nicht bestätigt.

Diese Assertion ist nicht standardmäßig aktiviert. Definieren Sie ATL_CCOMBSTR_ADDRESS_OF_ASSERT, um diese Assertion zu aktivieren.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#46](../../atl/codesnippet/cpp/ccombstr-class_14.cpp)]

[!code-cpp[NVC_ATL_Utilities#47](../../atl/codesnippet/cpp/ccombstr-class_15.cpp)]

##  <a name="operator_add_eq"></a>  CComBSTR::operator +=

Fügt eine Zeichenfolge, die die `CComBSTR` Objekt.

```
CComBSTR& operator+= (const CComBSTR& bstrSrc);
CComBSTR& operator+= (const LPCOLESTR pszSrc);
```

### <a name="parameters"></a>Parameter

*bstrSrc*<br/>
[in] Ein `CComBSTR` anzufügende Objekt.

*pszSrc*<br/>
[in] Eine NULL-terminierte Zeichenfolge angefügt.

### <a name="remarks"></a>Hinweise

`CComBSTR`s werden textlich im Kontext des Standard-Gebietsschema des Benutzers verglichen. Der Vergleich LPCOLESTR erfolgt mit `memcmp` auf die unformatierten Daten in jeder Zeichenfolge. Der LPCSTR Vergleich erfolgt auf dieselbe Weise sobald Unicode temporäre Kopie *PszSrc* erstellt wurde. Der endgültige Vergleichsoperator vergleicht lediglich die eingeschlossene Zeichenfolge mit NULL.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#48](../../atl/codesnippet/cpp/ccombstr-class_16.cpp)]

##  <a name="operator_lt"></a>  CComBSTR::operator &lt;

Vergleicht einen `CComBSTR` mit einer Zeichenfolge.

```
bool operator<(const CComBSTR& bstrSrc) const throw();
bool operator<(LPCOLESTR pszSrc) const throw();
bool operator<(LPCSTR pszSrc) const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn das Element wird im Vergleich kleiner als der `CComBSTR` -Objekt zurückgegeben; andernfalls "false".

### <a name="remarks"></a>Hinweise

Der Vergleich erfolgt mithilfe von Standard-Gebietsschema des Benutzers.

##  <a name="operator_eq"></a>  CComBSTR::operator =

Legt die [M_str](#m_str) Member auf eine Kopie der *pSrc* oder auf eine Kopie des BSTR-Elements *Src*. Verschiebt den bewegungszuweisungsoperator `src` ohne es zu kopieren.

```
CComBSTR& operator= (const CComBSTR& src);
CComBSTR& operator= (LPCOLESTR pSrc);
CComBSTR& operator= (LPCSTR pSrc);
CComBSTR& operator= (CComBSTR&& src) throw(); // (Visual Studio 2017)
```

### <a name="remarks"></a>Hinweise

Die *pSrc* Parameter gibt an, entweder eine LPCOLESTR für Unicode-Versionen oder LPCSTR für ANSI-Versionen.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [CComBSTR::Copy](#copy).

##  <a name="operator_eq_eq"></a>  CComBSTR::operator ==

Vergleicht einen `CComBSTR` mit einer Zeichenfolge. `CComBSTR`s werden textlich im Kontext des Standard-Gebietsschema des Benutzers verglichen.

```
bool operator== (const CComBSTR& bstrSrc) const throw();
bool operator== (LPCOLESTR pszSrc) const;
bool operator== (LPCSTR pszSrc) const;
bool operator== (int nNull) const throw();
```

### <a name="parameters"></a>Parameter

*bstrSrc*<br/>
[in] Ein `CComBSTR`-Objekt.

*pszSrc*<br/>
[in] Eine 0 (null) endende Zeichenfolge.

*nNull*<br/>
[in] NULL muss sein.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn das Element mit dem verglichen wird, entspricht die `CComBSTR` -Objekt zurückgegeben; andernfalls "false".

### <a name="remarks"></a>Hinweise

Der endgültige Vergleichsoperator vergleicht lediglich die eingeschlossene Zeichenfolge mit NULL.

##  <a name="operator_gt"></a>  CComBSTR::operator &gt;

Vergleicht einen `CComBSTR` mit einer Zeichenfolge.

```
bool operator>(const CComBSTR& bstrSrc) const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn das Element mit dem verglichen wird größer als die `CComBSTR` -Objekt zurückgegeben; andernfalls "false".

### <a name="remarks"></a>Hinweise

Der Vergleich erfolgt mithilfe von Standard-Gebietsschema des Benutzers.

##  <a name="readfromstream"></a>  CComBSTR::ReadFromStream

Legt die [M_str](#m_str) Member das BSTR, das im angegebenen Stream enthalten sind.

```
HRESULT ReadFromStream(IStream* pStream) throw();
```

### <a name="parameters"></a>Parameter

*pStream*<br/>
[in] Ein Zeiger auf die [IStream](/windows/desktop/api/objidl/nn-objidl-istream) Schnittstelle für den Stream, der die Daten enthält.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

`ReadToStream` erfordert den Inhalt des Streams an der aktuellen Position als kompatibel mit das Format der Daten durch einen Aufruf von geschrieben [WriteToStream](#writetostream).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#44](../../atl/codesnippet/cpp/ccombstr-class_17.cpp)]

##  <a name="tolower"></a>  CComBSTR::ToLower

Konvertiert die eingeschlossene Zeichenfolge in Kleinbuchstaben.

```
HRESULT ToLower() throw();
```

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Finden Sie unter `CharLowerBuff` für Weitere Informationen dazu, wie die Konvertierung ausgeführt wird.

##  <a name="toupper"></a>  CComBSTR::ToUpper

Konvertiert die eingeschlossene Zeichenfolge in Großbuchstaben.

```
HRESULT ToUpper() throw();
```

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Finden Sie unter `CharUpperBuff` für Weitere Informationen dazu, wie die Konvertierung ausgeführt wird.

##  <a name="writetostream"></a>  CComBSTR::WriteToStream

Speichert die [M_str](#m_str) Element in einen Stream.

```
HRESULT WriteToStream(IStream* pStream) throw();
```

### <a name="parameters"></a>Parameter

*pStream*<br/>
[in] Ein Zeiger auf die [IStream](/windows/desktop/api/objidl/nn-objidl-istream) Schnittstelle für einen Datenstrom.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Sie können einen BSTR-Wert aus dem Inhalt der Stream mit neu erstellen, die [ReadFromStream](#readfromstream) Funktion.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#45](../../atl/codesnippet/cpp/ccombstr-class_18.cpp)]

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)<br/>
[ATL und MFC-Zeichenfolgen-Konvertierungsmakros](string-conversion-macros.md)
