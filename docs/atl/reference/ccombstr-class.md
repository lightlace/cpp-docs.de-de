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
ms.openlocfilehash: dd45c2ff9b43148e0fe27ebd410a2390a4d12ce2
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497556"
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
|[CComBSTR::~CComBSTR](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComBSTR:: Anfügen](#append)|Fügt eine Zeichenfolge an `m_str`.|
|[CComBSTR::AppendBSTR](#appendbstr)|Fügt ein BSTR an `m_str`.|
|[CComBSTR:: AppendBytes](#appendbytes)|Fügt eine angegebene Anzahl von Bytes an `m_str`.|
|[CComBSTR::ArrayToBSTR](#arraytobstr)|Erstellt ein BSTR aus dem ersten Zeichen jedes Elements im SafeArray und fügt es an das `CComBSTR` -Objekt an.|
|[CComBSTR:: zutragbstr](#assignbstr)|Weist einen BSTR zu `m_str`.|
|[CComBSTR:: Attach](#attach)|Fügt ein BSTR an das `CComBSTR` -Objekt an.|
|[CComBSTR::BSTRToArray](#bstrtoarray)|Erstellt ein NULL basiertes eindimensionales SafeArray, wobei jedes Element des Arrays ein Zeichen aus dem `CComBSTR` -Objekt ist.|
|[CComBSTR::ByteLength](#bytelength)|Gibt die Länge von `m_str` in Byte zurück.|
|[CComBSTR::Copy](#copy)|Gibt eine Kopie von `m_str`zurück.|
|[CComBSTR::CopyTo](#copyto)|Gibt eine Kopie von `m_str` über einen **[out]** -Parameter zurück.|
|[CComBSTR::Detach](#detach)|`m_str` Trennt das`CComBSTR` -Objekt.|
|[CComBSTR::Empty](#empty)|Gibt `m_str`frei.|
|[CComBSTR::Length](#length)|Gibt die Länge von `m_str`zurück.|
|[CComBSTR::LoadString](#loadstring)|Lädt eine Zeichen folgen Ressource.|
|[CComBSTR::ReadFromStream](#readfromstream)|Lädt ein BSTR-Objekt aus einem Stream.|
|[CComBSTR::ToLower](#tolower)|Konvertiert die Zeichenfolge in Kleinbuchstaben.|
|[CComBSTR::ToUpper](#toupper)|Konvertiert die Zeichenfolge in Großbuchstaben.|
|[CComBSTR::WriteToStream](#writetostream)|Speichert `m_str` in einem Datenstrom.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CComBSTR:: Operator BSTR](#operator_bstr)|Wandelt ein `CComBSTR` -Objekt in ein BSTR um.|
|[CComBSTR::-Operator!](#operator_not)|Gibt true oder false zurück, je nachdem `m_str`, ob NULL ist.|
|[CComBSTR:: Operator! =](#operator_neq)|Vergleicht einen `CComBSTR` mit einer Zeichenfolge.|
|[CComBSTR:: Operator &](#operator_amp)|Gibt die Adresse von `m_str`zurück.|
|[CComBSTR:: Operator + =](#operator_add_eq)|Fügt ein `CComBSTR` an das-Objekt an.|
|[CComBSTR:: Operator <](#operator_lt)|Vergleicht einen `CComBSTR` mit einer Zeichenfolge.|
|[CComBSTR::operator =](#operator_eq)|Weist einen Wert zu `m_str`.|
|[CComBSTR::operator ==](#operator_eq_eq)|Vergleicht einen `CComBSTR` mit einer Zeichenfolge.|
|[CComBSTR:: Operator >](#operator_gt)|Vergleicht einen `CComBSTR` mit einer Zeichenfolge.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CComBSTR::m_str](#m_str)|Enthält den BSTR, der dem `CComBSTR` -Objekt zugeordnet ist.|

## <a name="remarks"></a>Hinweise

Die `CComBSTR` -Klasse ist ein Wrapper für BSTRs, bei dem es sich um Zeichen folgen mit Längen Präfix handelt. Die Länge wird als ganze Zahl an dem Speicherort gespeichert, der den Daten in der Zeichenfolge vorangestellt ist.

Ein [BSTR](/previous-versions/windows/desktop/automat/bstr) wird nach dem letzten gezählten Zeichen NULL-terminiert, kann aber auch NULL Zeichen enthalten, die in die Zeichenfolge eingebettet sind. Die Zeichen folgen Länge wird durch die Zeichen Anzahl bestimmt, nicht das erste Null Zeichen.

> [!NOTE]
>  Die `CComBSTR` -Klasse stellt eine Reihe von Membern (Konstruktoren, Zuweisungs Operatoren und Vergleichs Operatoren) bereit, die entweder ANSI-oder Unicode-Zeichen folgen als Argumente annehmen. Die ANSI-Versionen dieser Funktionen sind weniger effizient als ihre Unicode-Entsprechungen, da temporäre Unicode-Zeichen folgen häufig intern erstellt werden. Verwenden Sie aus Gründen der Effizienz die Unicode-Versionen, sofern möglich.

> [!NOTE]
>  Aufgrund des verbesserten Such Verhaltens, das in Visual Studio .NET implementiert wurde, sollte Code `bstr = L"String2" + bstr;`wie z. b., der in früheren Versionen kompiliert werden kann, `bstr = CStringW(L"String2") + bstr`stattdessen als implementiert werden.

Eine Liste der Vorsichts ungen bei der Verwendung `CComBSTR`von finden Sie unter [Programmieren mit CComBSTR](../../atl/programming-with-ccombstr-atl.md).

## <a name="requirements"></a>Anforderungen

**Header:** atlbase. h

##  <a name="append"></a>CComBSTR:: Anfügen

Fügt entweder *lpsz* oder den BSTR-Member von *bstrausrc* an [m_str](#m_str)an.

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
in Ein `CComBSTR` -Objekt, das angefügt werden soll.

*ch*<br/>
in Ein anzufügende Zeichen.

*lpsz*<br/>
in Eine mit NULL endend beendete Zeichenfolge, die angefügt werden soll. Sie können über die lpcolestr-Überladung oder eine ANSI-Zeichenfolge über die LPCSTR-Version eine Unicode-Zeichenfolge übergeben.

*nLen*<br/>
in Die Anzahl der Zeichen aus *lpsz* , die angefügt werden sollen.

### <a name="return-value"></a>Rückgabewert

S_OK bei Erfolg oder beliebiger Standard-HRESULT-Fehlerwert.

### <a name="remarks"></a>Hinweise

Eine ANSI-Zeichenfolge wird in Unicode konvertiert, bevor Sie angefügt wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#32](../../atl/codesnippet/cpp/ccombstr-class_1.cpp)]

##  <a name="appendbstr"></a>CComBSTR:: appendbstr

Fügt den angegebenen BSTR an [m_str](#m_str)an.

```
HRESULT AppendBSTR(BSTR p) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
in Ein BSTR, das angefügt werden soll.

### <a name="return-value"></a>Rückgabewert

S_OK bei Erfolg oder beliebiger Standard-HRESULT-Fehlerwert.

### <a name="remarks"></a>Hinweise

Übergeben Sie keine gewöhnliche Zeichenfolge mit breit Zeichen an diese Methode. Der Compiler kann die Fehler nicht abfangen, und Laufzeitfehler werden auftreten.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#33](../../atl/codesnippet/cpp/ccombstr-class_2.cpp)]

##  <a name="appendbytes"></a>CComBSTR:: AppendBytes

Fügt die angegebene Anzahl von Bytes an [m_str](#m_str) ohne Konvertierung an.

```
HRESULT AppendBytes(const char* lpsz, int nLen) throw();
```

### <a name="parameters"></a>Parameter

*lpsz*<br/>
in Ein Zeiger auf ein Array von Bytes, die angefügt werden sollen.

*p*<br/>
in Die Anzahl der anzufügende bytes.

### <a name="return-value"></a>Rückgabewert

S_OK bei Erfolg oder beliebiger Standard-HRESULT-Fehlerwert.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#34](../../atl/codesnippet/cpp/ccombstr-class_3.cpp)]

##  <a name="arraytobstr"></a>CComBSTR:: arrayto BSTR

Gibt eine vorhandene, im `CComBSTR` -Objekt enthaltene Zeichenfolge frei und erstellt dann ein BSTR-Objekt aus dem ersten Zeichen jedes Elements im SafeArray und fügt es an das `CComBSTR` -Objekt an.

```
HRESULT ArrayToBSTR(const SAFEARRAY* pSrc) throw();
```

### <a name="parameters"></a>Parameter

*pSrc*<br/>
in Das SafeArray, das die Elemente enthält, die zum Erstellen der Zeichenfolge verwendet werden.

### <a name="return-value"></a>Rückgabewert

S_OK bei Erfolg oder beliebiger Standard-HRESULT-Fehlerwert.

##  <a name="assignbstr"></a>CComBSTR:: zutragbstr

Weist [m_str](#m_str)einen BSTR zu.

```
HRESULT AssignBSTR(const BSTR bstrSrc) throw();
```

### <a name="parameters"></a>Parameter

*bstrSrc*<br/>
in Ein BSTR, das dem aktuellen `CComBSTR` -Objekt zugewiesen werden soll.

### <a name="return-value"></a>Rückgabewert

S_OK bei Erfolg oder beliebiger Standard-HRESULT-Fehlerwert.

##  <a name="attach"></a>CComBSTR:: Attach

Fügt ein BSTR an das `CComBSTR` -Objekt an, indem das [m_str](#m_str) -Member auf *src*festgelegt wird.

```
void Attach(BSTR src) throw();
```

### <a name="parameters"></a>Parameter

*src*<br/>
in Der BSTR, der an das-Objekt angehängt werden soll.

### <a name="remarks"></a>Hinweise

Übergeben Sie keine gewöhnliche Zeichenfolge mit breit Zeichen an diese Methode. Der Compiler kann die Fehler nicht abfangen, und Laufzeitfehler werden auftreten.

> [!NOTE]
>  Diese Methode wird bestätigt, `m_str` wenn nicht NULL ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]

##  <a name="bstrtoarray"></a>CComBSTR:: bstraudearray

Erstellt ein NULL basiertes eindimensionales SafeArray, wobei jedes Element des Arrays ein Zeichen aus dem `CComBSTR` -Objekt ist.

```
HRESULT BSTRToArray(LPSAFEARRAY* ppArray) throw();
```

### <a name="parameters"></a>Parameter

*ppArray*<br/>
vorgenommen Der Zeiger auf das SafeArray, das die Ergebnisse der Funktion enthält.

### <a name="return-value"></a>Rückgabewert

S_OK bei Erfolg oder beliebiger Standard-HRESULT-Fehlerwert.

##  <a name="bytelength"></a>CComBSTR:: ByteLength

Gibt die Anzahl der Bytes in `m_str`zurück, ohne das abschließende Null Zeichen.

```
unsigned int ByteLength() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die Länge des [m_str](#m_str) -Elements in Bytes.

### <a name="remarks"></a>Hinweise

Gibt 0 zurück `m_str` , wenn NULL ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#36](../../atl/codesnippet/cpp/ccombstr-class_5.cpp)]

##  <a name="ccombstr"></a>CComBSTR:: CComBSTR

Der Konstruktor. Der Standardkonstruktor legt den [m_str](#m_str) -Member auf NULL fest.

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
in Die Anzahl der Zeichen, die aus der *SZ* kopiert werden sollen, oder die Anfangs `CComBSTR`Größe in Zeichen für den.

*sz*<br/>
[in] Eine zu kopierende Zeichenfolge. Die Unicode-Version gibt einen lpcolestr an. die ANSI-Version gibt ein LPCSTR an.

*pSrc*<br/>
[in] Eine zu kopierende Zeichenfolge. Die Unicode-Version gibt einen lpcolestr an. die ANSI-Version gibt ein LPCSTR an.

*src*<br/>
[in] Ein `CComBSTR`-Objekt.

*guid*<br/>
in Ein Verweis auf eine `GUID` -Struktur.

### <a name="remarks"></a>Hinweise

Der Kopierkonstruktor `m_str` legt auf eine Kopie des BSTR-Members von *src*fest. Der Konstruktor konvertiert die GUID mit `StringFromGUID2` in eine Zeichenfolge und speichert das Ergebnis. `REFGUID`

Die anderen Konstruktoren legen `m_str` auf eine Kopie der angegebenen Zeichenfolge fest. Wenn Sie einen Wert für *nSize*übergeben, werden nur die *nSize* -Zeichen kopiert, gefolgt von einem abschließenden NULL Zeichen.

`CComBSTR` unterstützt die move-Semantik. Mit dem Bewegungskonstruktor (dem Konstruktor, der einen rvalue-Verweis verwendet (`&&`) können Sie ein neues Objekt erstellen, das die Daten des alten als Argument übergebenen Objekts verwendet, ohne das Objekt kopieren zu müssen.

Der Destruktor gibt die Zeichenfolge frei, auf die von `m_str` gezeigt wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#37](../../atl/codesnippet/cpp/ccombstr-class_6.cpp)]

##  <a name="dtor"></a>CComBSTR:: ~ CComBSTR

Der Destruktor.

```
~CComBSTR();
```

### <a name="remarks"></a>Hinweise

Der Destruktor gibt die Zeichenfolge frei, auf die von `m_str` gezeigt wird.

##  <a name="copy"></a>CComBSTR:: Copy

Ordnet eine Kopie von `m_str`zu und gibt Sie zurück.

```
BSTR Copy() const throw();
```

### <a name="return-value"></a>Rückgabewert

Eine Kopie des [m_str](#m_str) -Members. Wenn `m_str` NULL ist, wird NULL zurückgegeben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#38](../../atl/codesnippet/cpp/ccombstr-class_7.cpp)]

##  <a name="copyto"></a>CComBSTR:: CopyTo

Ordnet eine Kopie von [m_str](#m_str) über den-Parameter zu und gibt Sie zurück.

```
HRESULT CopyTo(BSTR* pbstr) throw();

HRESULT CopyTo(VARIANT* pvarDest) throw();
```

### <a name="parameters"></a>Parameter

*pbstr*<br/>
vorgenommen Die Adresse eines BSTR, in dem die von dieser Methode zugeordnete Zeichenfolge zurückgegeben werden soll.

*pvarDest*<br/>
vorgenommen Die Adresse einer Variante, in der die von dieser Methode zugeordnete Zeichenfolge zurückgegeben werden soll.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert, der den Erfolg oder das Fehlschlagen der Kopie angibt.

### <a name="remarks"></a>Hinweise

Nach dem Aufrufen dieser Methode ist die Variante, auf die *pvardest* verweist, vom Typ VT_BSTR.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#39](../../atl/codesnippet/cpp/ccombstr-class_8.cpp)]

##  <a name="detach"></a>CComBSTR::D Etach

Trennt [m_str](#m_str) vom `CComBSTR` -Objekt und legt `m_str` auf NULL fest.

```
BSTR Detach() throw();
```

### <a name="return-value"></a>Rückgabewert

Der BSTR, der dem `CComBSTR` Objekt zugeordnet ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#40](../../atl/codesnippet/cpp/ccombstr-class_9.cpp)]

##  <a name="empty"></a>CComBSTR:: Empty

Gibt den [m_str](#m_str) -Member frei.

```
void Empty() throw();
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#41](../../atl/codesnippet/cpp/ccombstr-class_10.cpp)]

##  <a name="length"></a>CComBSTR:: length

Gibt die Anzahl von Zeichen in `m_str`zurück, ohne das abschließende Null Zeichen.

```
unsigned int Length() const throw();
```

### <a name="return-value"></a>Rückgabewert

Die Länge des [m_str](#m_str) -Members.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#42](../../atl/codesnippet/cpp/ccombstr-class_11.cpp)]

##  <a name="loadstring"></a>CComBSTR:: loadstring

Lädt eine von *NID* angegebene Zeichen folgen Ressource und speichert Sie in diesem-Objekt.

```
bool LoadString(HINSTANCE hInst, UINT nID) throw();
bool LoadString(UINT nID) throw();
```

### <a name="parameters"></a>Parameter

Weitere Informationen finden Sie unter [LoadString](/windows/win32/api/winuser/nf-winuser-loadstringw) in der Windows SDK.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Zeichenfolge erfolgreich geladen wurde. Andernfalls wird false zurückgegeben.

### <a name="remarks"></a>Hinweise

Die erste Funktion lädt die Ressource aus dem von Ihnen identifizierten Modul über den *hInst* -Parameter. Die zweite Funktion lädt die Ressource aus dem Ressourcen Modul, das mit dem in diesem Projekt verwendeten [CComModule](../../atl/reference/ccommodule-class.md)-abgeleiteten Objekt verknüpft ist.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#43](../../atl/codesnippet/cpp/ccombstr-class_12.cpp)]

##  <a name="m_str"></a>CComBSTR:: m_str

Enthält den BSTR, der dem `CComBSTR` -Objekt zugeordnet ist.

```
BSTR m_str;
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#49](../../atl/codesnippet/cpp/ccombstr-class_13.cpp)]

##  <a name="operator_bstr"></a>CComBSTR:: Operator BSTR

Wandelt ein `CComBSTR` -Objekt in ein BSTR um.

```
operator BSTR() const throw();
```

### <a name="remarks"></a>Hinweise

Ermöglicht das übergeben `CComBSTR` von Objekten an Funktionen mit **[in] BSTR** -Parametern.

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [CComBSTR:: m_str](#m_str).

##  <a name="operator_not"></a>CComBSTR::-Operator!

Überprüft, ob BSTR-Zeichenfolge NULL ist.

```
bool operator!() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn der [m_str](#m_str) -Member NULL ist. andernfalls false.

### <a name="remarks"></a>Hinweise

Dieser Operator prüft nur auf einen NULL-Wert, nicht auf eine leere Zeichenfolge.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#35](../../atl/codesnippet/cpp/ccombstr-class_4.cpp)]

##  <a name="operator_neq"></a>CComBSTR:: Operator! =

Gibt das logische Gegenteil von [Operator = =](#operator_eq_eq)zurück.

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
in Eine NULL terminierte Zeichenfolge.

*nNull*<br/>
in Muss NULL sein.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn das verglichene Element nicht gleich `CComBSTR` dem-Objekt ist; andernfalls wird false zurückgegeben.

### <a name="remarks"></a>Hinweise

`CComBSTR`e werden im Kontext des Standard Gebiets Schemas des Benutzers textuell verglichen. Der abschließende Vergleichs Operator vergleicht die enthaltene Zeichenfolge nur mit NULL.

##  <a name="operator_amp"></a>CComBSTR::-Operator&amp;

Gibt die Adresse des BSTR zurück, der im [m_str](#m_str) -Element gespeichert ist.

```
BSTR* operator&() throw();
```

### <a name="remarks"></a>Hinweise

`CComBstr operator &`Es ist eine besondere Assertion zugeordnet, um Speicher Verluste zu identifizieren. Das Programm bestätigt, wenn der `m_str` Member initialisiert wird. Diese Assertion wurde erstellt, um Situationen zu identifizieren, in `& operator` denen ein Programmierer mithilfe von einen `m_str` neuen Wert einem Member zuweist, `m_str`ohne die erste Zuordnung von aufzuheben. Wenn `m_str` gleich NULL ist, geht das Programm davon aus, dass m_str noch nicht zugeordnet wurde. In diesem Fall wird das Programm nicht bestätigen.

Diese Übersetzung ist standardmäßig nicht aktiviert. Definieren Sie ATL_CCOMBSTR_ADDRESS_OF_ASSERT, um diese Assertion zu aktivieren.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#46](../../atl/codesnippet/cpp/ccombstr-class_14.cpp)]

[!code-cpp[NVC_ATL_Utilities#47](../../atl/codesnippet/cpp/ccombstr-class_15.cpp)]

##  <a name="operator_add_eq"></a>CComBSTR:: Operator + =

Fügt eine Zeichenfolge an das `CComBSTR` -Objekt an.

```
CComBSTR& operator+= (const CComBSTR& bstrSrc);
CComBSTR& operator+= (const LPCOLESTR pszSrc);
```

### <a name="parameters"></a>Parameter

*bstrSrc*<br/>
in Ein `CComBSTR` -Objekt, das angefügt werden soll.

*pszSrc*<br/>
in Eine mit NULL endenden Zeichenfolge, die angefügt werden soll.

### <a name="remarks"></a>Hinweise

`CComBSTR`e werden im Kontext des Standard Gebiets Schemas des Benutzers textuell verglichen. Der lpcolestr-Vergleich erfolgt mithilfe `memcmp` von für die Rohdaten in den einzelnen Zeichen folgen. Der LPCSTR-Vergleich wird auf die gleiche Weise durchgeführt, nachdem eine temporäre Unicode-Kopie von *pszSrc* erstellt wurde. Der abschließende Vergleichs Operator vergleicht die enthaltene Zeichenfolge nur mit NULL.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#48](../../atl/codesnippet/cpp/ccombstr-class_16.cpp)]

##  <a name="operator_lt"></a>CComBSTR::-Operator&lt;

Vergleicht einen `CComBSTR` mit einer Zeichenfolge.

```
bool operator<(const CComBSTR& bstrSrc) const throw();
bool operator<(LPCOLESTR pszSrc) const throw();
bool operator<(LPCSTR pszSrc) const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn das verglichene Element kleiner `CComBSTR` als das-Objekt ist; andernfalls wird false zurückgegeben.

### <a name="remarks"></a>Hinweise

Der Vergleich erfolgt über das Standard Gebiets Schema des Benutzers.

##  <a name="operator_eq"></a>CComBSTR:: Operator =

Legt den [m_str](#m_str) -Member auf eine Kopie von *psrc* oder auf eine Kopie des BSTR-Members von *src*fest. Der Bewegungs Zuweisungs Operator `src` wird verschoben, ohne ihn zu kopieren.

```
CComBSTR& operator= (const CComBSTR& src);
CComBSTR& operator= (LPCOLESTR pSrc);
CComBSTR& operator= (LPCSTR pSrc);
CComBSTR& operator= (CComBSTR&& src) throw(); // (Visual Studio 2017)
```

### <a name="remarks"></a>Hinweise

Der *psrc* -Parameter gibt entweder einen lpcolestr für Unicode-Versionen oder LPCSTR für ANSI-Versionen an.

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Beispiel für [CComBSTR:: Copy](#copy).

##  <a name="operator_eq_eq"></a>CComBSTR:: Operator = =

Vergleicht einen `CComBSTR` mit einer Zeichenfolge. `CComBSTR`e werden im Kontext des Standard Gebiets Schemas des Benutzers textuell verglichen.

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
in Eine NULL terminierte Zeichenfolge.

*nNull*<br/>
in Muss NULL sein.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn das verglichene Element gleich `CComBSTR` dem-Objekt ist; andernfalls wird false zurückgegeben.

### <a name="remarks"></a>Hinweise

Der abschließende Vergleichs Operator vergleicht die enthaltene Zeichenfolge nur mit NULL.

##  <a name="operator_gt"></a>CComBSTR::-Operator&gt;

Vergleicht einen `CComBSTR` mit einer Zeichenfolge.

```
bool operator>(const CComBSTR& bstrSrc) const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn das verglichene Element größer `CComBSTR` als das-Objekt ist; andernfalls wird false zurückgegeben.

### <a name="remarks"></a>Hinweise

Der Vergleich erfolgt über das Standard Gebiets Schema des Benutzers.

##  <a name="readfromstream"></a>CComBSTR:: Read FromStream

Legt das [m_str](#m_str) -Element auf den BSTR-Wert fest, der im angegebenen Stream enthalten ist.

```
HRESULT ReadFromStream(IStream* pStream) throw();
```

### <a name="parameters"></a>Parameter

*pStream*<br/>
in Ein Zeiger auf die [IStream](/windows/win32/api/objidl/nn-objidl-istream) -Schnittstelle im Stream, der die Daten enthält.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

### <a name="remarks"></a>Hinweise

`ReadToStream`erfordert, dass der Inhalt des Datenstroms an der aktuellen Position mit dem Datenformat kompatibel ist, das durch einen-aufschreibe [Schreib](#writetostream)Vorgang geschrieben wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#44](../../atl/codesnippet/cpp/ccombstr-class_17.cpp)]

##  <a name="tolower"></a>CComBSTR:: ToLower

Konvertiert die enthaltene Zeichenfolge in Kleinbuchstaben.

```
HRESULT ToLower() throw();
```

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

### <a name="remarks"></a>Hinweise

Weitere `CharLowerBuff` Informationen zur Durchführung der Konvertierung finden Sie unter.

##  <a name="toupper"></a>CComBSTR:: toupperdatei

Konvertiert die enthaltene Zeichenfolge in Großbuchstaben.

```
HRESULT ToUpper() throw();
```

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

### <a name="remarks"></a>Hinweise

Weitere `CharUpperBuff` Informationen zur Durchführung der Konvertierung finden Sie unter.

##  <a name="writetostream"></a>CComBSTR:: Write-to-Stream

Speichert das [m_str](#m_str) -Element in einem Stream.

```
HRESULT WriteToStream(IStream* pStream) throw();
```

### <a name="parameters"></a>Parameter

*pStream*<br/>
in Ein Zeiger auf die [IStream](/windows/win32/api/objidl/nn-objidl-istream) -Schnittstelle in einem Stream.

### <a name="return-value"></a>Rückgabewert

Ein HRESULT-Standardwert.

### <a name="remarks"></a>Hinweise

Sie können ein BSTR mithilfe der Funktion "read [FromStream](#readfromstream) " aus dem Inhalt des Streams neu erstellen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#45](../../atl/codesnippet/cpp/ccombstr-class_18.cpp)]

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)<br/>
[ATL-und MFC-Zeichen folgen Konvertierungs Makros](string-conversion-macros.md)
