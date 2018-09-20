---
title: COleCurrency-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleCurrency
- AFXDISP/COleCurrency
- AFXDISP/COleCurrency::COleCurrency
- AFXDISP/COleCurrency::Format
- AFXDISP/COleCurrency::GetStatus
- AFXDISP/COleCurrency::ParseCurrency
- AFXDISP/COleCurrency::SetCurrency
- AFXDISP/COleCurrency::SetStatus
- AFXDISP/COleCurrency::m_cur
- AFXDISP/COleCurrency::m_status
dev_langs:
- C++
helpviewer_keywords:
- COleCurrency [MFC], COleCurrency
- COleCurrency [MFC], Format
- COleCurrency [MFC], GetStatus
- COleCurrency [MFC], ParseCurrency
- COleCurrency [MFC], SetCurrency
- COleCurrency [MFC], SetStatus
- COleCurrency [MFC], m_cur
- COleCurrency [MFC], m_status
ms.assetid: 3a36e345-303f-46fb-a57c-858274378a8d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec20b4b212ee435c9538716afaca645edfe5adcc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404204"
---
# <a name="colecurrency-class"></a>COleCurrency-Klasse

Kapselt den `CURRENCY` -Datentyp der OLE-Automatisierung.

## <a name="syntax"></a>Syntax

```
class COleCurrency
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[COleCurrency::COleCurrency](#colecurrency)|Erstellt ein `COleCurrency`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[COleCurrency::Format](#format)|Generiert eine formatierte Zeichenfolgendarstellung einer `COleCurrency` Objekt.|
|[COleCurrency::GetStatus](#getstatus)|Ruft ab, der den Status (Gültigkeit) `COleCurrency` Objekt.|
|[COleCurrency::ParseCurrency](#parsecurrency)|Liest einen Währungswert aus einer Zeichenfolge und legt den Wert der `COleCurrency`.|
|[COleCurrency::SetCurrency](#setcurrency)|Legt den Wert dieses `COleCurrency` Objekt.|
|[COleCurrency::SetStatus](#setstatus)|Legt den Status der (Gültigkeit) für diese `COleCurrency` Objekt.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[operator =](#operator_eq)|Kopiert ein `COleCurrency` Wert.|
|[Operator +, -](#operator_plus_minus)|Fügt, subtrahiert wird und Anzeichen `COleCurrency` Werte.|
|[Operator +=, =](#operator_plus_minus_eq)|Fügt und subtrahiert einen `COleCurrency` Wert aus diesem `COleCurrency` Objekt.|
|[Operator * /](#operator_star)|Skaliert ein `COleCurrency` Wert durch einen ganzzahligen Wert.|
|[Operator * =, / =](#operator_star_div_eq)|Skaliert `COleCurrency` Wert durch einen ganzzahligen Wert.|
|[Operator <<](#operator_stream)|Ausgaben eine `COleCurrency` Wert `CArchive` oder `CDumpContext`.|
|[Operator >>](#operator_stream)|Eingaben ein `COleCurrency` -Sitzungsobjekts `CArchive`.|
|[Operator Währung](#operator_currency)|Konvertiert eine `COleCurrency` Wert in eine Währung.|
|[Operator ==, <, < =, usw..](#colecurrency_relational_operators)|Vergleicht zwei `COleCurrency` Werte.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[COleCurrency::m_cur](#m_cur)|Enthält die zugrunde liegenden Währung für diese `COleCurrency` Objekt.|
|[COleCurrency::m_status](#m_status)|Enthält den Status dieser `COleCurrency` Objekt.|

## <a name="remarks"></a>Hinweise

`COleCurrency` eine Basisklasse keinen.

Währung ist als eine 8-Byte-Komplement der beiden ganzzahligen Wert skaliert mit 10.000, implementiert. Dies ermöglicht eine Festkommazahl mit 15 Stellen links vom Dezimaltrennzeichen und 4 Ziffern rechts. Der CURRENCY-Datentyp ist äußerst nützlich für finanzberechnungen oder für alle Berechnungsmethode, in denen Genauigkeit wichtig. Es ist eine der möglichen Typen für die `VARIANT` -Datentyp der OLE-Automatisierung.

`COleCurrency` implementiert außerdem einige grundlegenden arithmetischen Operationen für diesen festkommatyp. Die unterstützten Vorgänge wurden ausgewählt, um die Rundungsfehler zu steuern, die während der festkommaberechnungen auftreten.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`COleCurrency`

## <a name="requirements"></a>Anforderungen

**Header:** afxdisp.h

##  <a name="colecurrency"></a>  COleCurrency::COleCurrency

Erstellt ein `COleCurrency`-Objekt.

```
COleCurrency();
COleCurrency(CURRENCY cySrc);
  COleCurrency(const COleCurrency& curSrc);
COleCurrency(const VARIANT& varSrc);


COleCurrency(
    long nUnits,
    long nFractionalUnits);
```

### <a name="parameters"></a>Parameter

*cySrc*<br/>
Ein Währungswert in die neue kopiert werden `COleCurrency` Objekt.

*curSrc*<br/>
Eine vorhandene `COleCurrency` Objekt, das in die neue kopiert werden `COleCurrency` Objekt.

*varSrc*<br/>
Eine vorhandene `VARIANT` Datenstruktur (möglicherweise eine `COleVariant` Objekt) als Währungswert (VT_CY) konvertiert und kopiert in das neue `COleCurrency` Objekt.

*nUnits*, *nFractionalUnits* geben die Einheiten und der Bruchteil (in 1/10.000) den Wert in die neue kopiert werden `COleCurrency` Objekt.

### <a name="remarks"></a>Hinweise

Alle diese Konstruktoren erstellen neue `COleCurrency` Objekte, die auf den angegebenen Wert initialisiert. Eine kurze Beschreibung jeder dieser Konstruktoren folgt. Sofern nicht anders angegeben, den Status der neuen `COleCurrency` Element zu ungültig festgelegt ist.

- COleCurrency() Konstrukte ein `COleCurrency` Objekt mit 0 (null) initialisiert.

- COleCurrency (`cySrc`) erstellt eine `COleCurrency` -Objekt aus einem [Währung](/windows/desktop/api/wtypes/ns-wtypes-tagcy) Wert.

- COleCurrency (`curSrc`) erstellt eine `COleCurrency` -Objekt aus einem vorhandenen `COleCurrency` Objekt. Das neue Objekt hat den gleichen Status wie das Quellobjekt.

- COleCurrency (`varSrc`) erstellt eine `COleCurrency` Objekt. Versucht, Konvertieren einer [VARIANT](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) Struktur oder `COleVariant` Objekt, das ein Währungswert (VT_CY). Wenn die Konvertierung erfolgreich ist, wird der konvertierte Wert in die neue kopiert `COleCurrency` Objekt. Ist dies nicht der Fall, den Wert des der `COleCurrency` Objekt auf 0 (null) und dessen Status als ungültig festgelegt ist.

- `COleCurrency(`nUnits`, `nFractionalUnits`) Constructs a `COleCurrency' Objekt aus den angegebenen numerischen Komponenten. Wenn der Bruchteil den absoluten Wert größer als 10.000 ist, wird die entsprechende Anpassung an die Einheiten vorgenommen. Beachten Sie, dass die Einheiten und der Teil mit Bruchzahlen von long-Werte mit Vorzeichen angegeben werden.

Weitere Informationen finden Sie unter den [Währung](/windows/desktop/api/wtypes/ns-wtypes-tagcy) und [VARIANT](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) Einträge in das Windows SDK.

### <a name="example"></a>Beispiel

Die folgenden Beispiele zeigen die Auswirkungen der Konstruktoren Parameter 0 (null) oder zwei Parameter:

[!code-cpp[NVC_MFCOleContainer#10](../../mfc/codesnippet/cpp/colecurrency-class_1.cpp)]

##  <a name="format"></a>  COleCurrency::Format

Rufen Sie diese Memberfunktion, um eine formatierte Darstellung des den Currency-Wert zu erstellen.

```
CString Format(DWORD  dwFlags = 0, LCID  lcid = LANG_USER_DEFAULT) const;
```

### <a name="parameters"></a>Parameter

*dwFlags*<br/>
Gibt Flags für das Gebietsschema an. Nur das Flag ist in die Währung relevant:

- LOCALE_NOUSEROVERRIDE verwenden Sie den Standard-gebietsschemaeinstellungen für System, anstelle von benutzerdefinierten Einstellungen.

*lcid*<br/>
Gibt die Gebietsschema-ID, für die Konvertierung verwendet.

### <a name="return-value"></a>Rückgabewert

Ein `CString` , das die formatierte Währung-Wert enthält.

### <a name="remarks"></a>Hinweise

Es formatiert den Wert, der mit den Spezifikationen der lokalen Sprache (Gebietsschema-IDs). Ein Währungssymbol ist nicht in den zurückgegebenen Wert enthalten. Wenn der Status dieser `COleCurrency` Objekt null ist. der zurückgegebene Wert ist eine leere Zeichenfolge. Wenn der Status ungültig ist, wird die zurückgegebene Zeichenfolge durch die Zeichenfolgenressource IDS_INVALID_CURRENCY angegeben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#11](../../mfc/codesnippet/cpp/colecurrency-class_2.cpp)]

##  <a name="getstatus"></a>  COleCurrency::GetStatus

Rufen Sie diese Memberfunktion zum Abrufen des Status (Gültigkeit) einen bestimmten `COleCurrency` Objekt.

```
CurrencyStatus GetStatus() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt den Status dieses `COleCurrency` Wert.

### <a name="remarks"></a>Hinweise

Der Rückgabewert wird definiert, durch die `CurrencyStatus` Enumerationstyps, der definiert ist die `COleCurrency` Klasse.

```
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };
```

Eine kurze Beschreibung dieser Status-Werte finden Sie in der folgenden Liste:

  - `COleCurrency::valid` Gibt an, das von diesem `COleCurrency` Objekt gültig ist.

  - `COleCurrency::invalid` Gibt an, das von diesem `COleCurrency` Objekt ist ungültig; d. h. der Wert möglicherweise nicht korrekt.

  - `COleCurrency::null` Gibt an, das von diesem `COleCurrency` Objekt null ist, d. h., dass für dieses Objekt kein Wert angegeben wurde. (Dies ist "null", in dem Sinne Database "kein Wert, wenn" im Gegensatz zu den C++-NULL).

Der Status einer `COleCurrency` Objekt ist ungültig. in den folgenden Fällen:

- Wenn der Wert, über eine Variante festgelegt ist oder `COleVariant` -Wert, der kein Währungswert konvertiert werden konnten.

- Wenn dieses Objekt, einem Überlauf oder Unterlauf während eines arithmetischen Zuweisung, z. B. aufgetreten sind `+=` oder **\* =**.

- Wenn ein ungültiger Wert für dieses Objekt zugewiesen wurde.

- Wenn der Status dieses Objekts explizit festgelegt wurde, um ungültige mit [SetStatus](#setstatus).

Weitere Informationen zu Vorgängen, die den Status ungültige, finden Sie unter den folgenden Member-Funktionen festgelegt werden können:

- [COleCurrency](#colecurrency)

- [operator =](#operator_eq)

- [Operator + -](#operator_plus_minus)

- [Operator += und -=](#operator_plus_minus_eq)

- [Operator * /](#operator_star)

- [Operator * = und / =](#operator_star_div_eq)

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#12](../../mfc/codesnippet/cpp/colecurrency-class_3.cpp)]

##  <a name="m_cur"></a>  COleCurrency::m_cur

Die zugrunde liegende [Währung](/windows/desktop/api/wtypes/ns-wtypes-tagcy) Struktur für diese `COleCurrency` Objekt.

### <a name="remarks"></a>Hinweise

> [!CAUTION]
>  Ändern des Werts in der `CURRENCY` Struktur, die Zugriff auf die von dieser Funktion zurückgegebenen Zeiger ändert sich den Wert dieser `COleCurrency` Objekt. Er ändert nicht den Status dieses `COleCurrency` Objekt.

Weitere Informationen finden Sie unter den [Währung](/windows/desktop/api/wtypes/ns-wtypes-tagcy) Eintrag in das Windows SDK.

##  <a name="m_status"></a>  COleCurrency::m_status

Der Typ dieses Datenelements ist den enumerierten Typ `CurrencyStatus`, definiert in der `COleCurrency` Klasse.

```
enum CurrencyStatus{
    valid = 0,
    invalid = 1,
    null = 2,
};
```

### <a name="remarks"></a>Hinweise

Eine kurze Beschreibung dieser Status-Werte finden Sie in der folgenden Liste:

- `COleCurrency::valid` Gibt an, das von diesem `COleCurrency` Objekt gültig ist.

- `COleCurrency::invalid` Gibt an, das von diesem `COleCurrency` Objekt ist ungültig; d. h. der Wert möglicherweise nicht korrekt.

- `COleCurrency::null` Gibt an, das von diesem `COleCurrency` Objekt null ist, d. h., dass für dieses Objekt kein Wert angegeben wurde. (Dies ist "null", in dem Sinne Database "kein Wert, wenn" im Gegensatz zu den C++-NULL).

Der Status einer `COleCurrency` Objekt ist ungültig. in den folgenden Fällen:

- Wenn der Wert, über eine Variante festgelegt ist oder `COleVariant` -Wert, der kein Währungswert konvertiert werden konnten.

- Wenn dieses Objekt, einem Überlauf oder Unterlauf während eines arithmetischen Zuweisung, z. B. aufgetreten sind `+=` oder **\* =**.

- Wenn ein ungültiger Wert für dieses Objekt zugewiesen wurde.

- Wenn der Status dieses Objekts explizit festgelegt wurde, um ungültige mit [SetStatus](#setstatus).

Weitere Informationen zu Vorgängen, die den Status ungültige, finden Sie unter den folgenden Member-Funktionen festgelegt werden können:

- [COleCurrency](#colecurrency)

- [operator =](#operator_eq)

- [Operator +, -](#operator_plus_minus)

- [Operator +=, =](#operator_plus_minus_eq)

- [Operator * /](#operator_star)

- [Operator * =, / =](#operator_star_div_eq)

> [!CAUTION]
>  Dieses Datenelement ist für erweiterte programmierungssituationen. Sie sollten die Inline-Memberfunktionen verwenden [GetStatus](#getstatus) und [SetStatus](#setstatus). Finden Sie unter `SetStatus` für weitere Punkte in Bezug auf die dieses Datenelement explizit festlegen.

##  <a name="operator_eq"></a>  COleCurrency::operator =

Diese überladenen Zuweisungsoperatoren kopieren Sie den Wert der Source-Währung in diese `COleCurrency` Objekt.

```
const COleCurrency& operator=(CURRENCY cySrc);
const COleCurrency& operator=(const COleCurrency& curSrc);
  const COleCurrency& operator=(const VARIANT& varSrc);
```

### <a name="remarks"></a>Hinweise

Es folgt eine kurze Beschreibung der einzelnen Operatoren:

- **Operator = (** `cySrc` **)** der `CURRENCY` Wert wird in kopiert die `COleCurrency` -Objekt und seinen Status zu ungültig festgelegt ist.

- **Operator = (** `curSrc` **)** den Wert und Status des Operanden, eine vorhandene `COleCurrency` Objekt werden in diese kopiert `COleCurrency` Objekt.

- **Operator = (** *VarSrc* **)** Wenn die Konvertierung der `VARIANT` Wert (oder [COleVariant](../../mfc/reference/colevariant-class.md) Objekt) zu einer Währung ( `VT_CY`) ist erfolgreich ist, wird der konvertierte Wert in diese kopiert `COleCurrency` -Objekt und seinen Status zu ungültig festgelegt ist. Wenn die Konvertierung nicht erfolgreich ist, ist der Wert des der `COleCurrency` Objekt auf 0 und dessen Status als ungültig festgelegt ist.

Weitere Informationen finden Sie unter den [Währung](/windows/desktop/api/wtypes/ns-wtypes-tagcy) und [VARIANT](/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagvariant) Einträge in das Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#15](../../mfc/codesnippet/cpp/colecurrency-class_4.cpp)]

##  <a name="operator_plus_minus"></a>  COleCurrency::operator +, -

Diese Operatoren können Sie von Addition und Subtraktion von zwei `COleCurrency` Werte zu und von anderen und so ändern Sie die Vorzeichen einer `COleCurrency` Wert.

```
COleCurrency operator+(const COleCurrency& cur) const;
COleCurrency operator-(const COleCurrency& cur) const;
COleCurrency operator-() const;
```

### <a name="remarks"></a>Hinweise

Wenn einer der Operanden null ist, ist den Status des resultierenden `COleCurrency` Wert ist null.

Wenn die arithmetische Operation überläuft, die resultierende `COleCurrency` Wert ist ungültig.

Wenn der Operand ungültig ist und die andere ist nicht null ist, ist den Status des resultierenden `COleCurrency` Wert ist ungültig.

Weitere Informationen zu den gültigen, Ungültiger und null-Status-Werte, finden Sie unter den [M_status](#m_status) Membervariablen gespeichert.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#16](../../mfc/codesnippet/cpp/colecurrency-class_5.cpp)]

##  <a name="operator_plus_minus_eq"></a>  COleCurrency::operator +=, =

Ermöglichen es Ihnen, Addition und Subtraktion ein `COleCurrency` Wert zu und aus diesem `COleCurrency` Objekt.

```
const COleCurrency& operator+=(const COleCurrency& cur);
const COleCurrency& operator-=(const COleCurrency& cur);
```

### <a name="remarks"></a>Hinweise

Wenn einer der Operanden null ist, ist den Status dieser `COleCurrency` Objekts wird festgelegt auf Null.

Wenn die arithmetische Operation überläuft, den den Status `COleCurrency` Objekt festgelegt ist, ungültig.

Wenn es sich bei den Operanden ist ungültig, und die andere ist nicht null ist, der den Status `COleCurrency` Objekt festgelegt ist als ungültig.

Weitere Informationen zu den gültigen, Ungültiger und null-Status-Werte, finden Sie unter den [M_status](#m_status) Membervariablen gespeichert.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#17](../../mfc/codesnippet/cpp/colecurrency-class_6.cpp)]

##  <a name="operator_star"></a>  COleCurrency::operator \* und /

Ermöglichen Ihnen die Skalierung einer `COleCurrency` Wert durch einen ganzzahligen Wert.

```
COleCurrency operator*(long nOperand) const;
COleCurrency operator/(long nOperand) const;
```

### <a name="remarks"></a>Hinweise

Wenn die `COleCurrency` Operand null ist, den Status des resultierenden `COleCurrency` Wert ist null.

Wenn die arithmetische Operation führt zu einem Überlauf oder Unterlauf stattfindet, wird der Status des resultierenden `COleCurrency` Wert ist ungültig.

Wenn die `COleCurrency` Operand ungültig ist, wird der Status des resultierenden `COleCurrency` Wert ist ungültig.

Weitere Informationen zu den gültigen, Ungültiger und null-Status-Werte, finden Sie unter den [M_status](#m_status) Membervariablen gespeichert.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#18](../../mfc/codesnippet/cpp/colecurrency-class_7.cpp)]

##  <a name="operator_star_div_eq"></a>  COleCurrency::operator \*=, / =

Ermöglichen es Ihnen, die Skalierung dieser `COleCurrency` Wert durch einen ganzzahligen Wert.

```
const COleCurrency& operator*=(long nOperand);
const COleCurrency& operator/=(long nOperand);
```

### <a name="remarks"></a>Hinweise

Wenn die `COleCurrency` Operand null ist, ist der Status dieser `COleCurrency` Objekts wird festgelegt auf Null.

Wenn die arithmetische Operation überläuft, den den Status `COleCurrency` Objekt festgelegt ist, ungültig.

Wenn die `COleCurrency` Operand ungültig ist, wird der Status dieser `COleCurrency` Objekt festgelegt ist als ungültig.

Weitere Informationen zu den gültigen, Ungültiger und null-Status-Werte, finden Sie unter den [M_status](#m_status) Membervariablen gespeichert.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#19](../../mfc/codesnippet/cpp/colecurrency-class_8.cpp)]

##  <a name="operator_stream"></a>  COleCurrency::operator &lt; &lt;, &gt;&gt;

Unterstützt die diagnostische Ausgabe und in ein Archiv zu speichern.

```
friend CDumpContext& operator<<(
    CDumpContext& dc,
    COleCurrency curSrc);

friend CArchive& operator<<(
    CArchive& ar,
    COleCurrency curSrc);

friend CArchive& operator>>(
    CArchive& ar,
    COleCurrency& curSrc);
```

### <a name="remarks"></a>Hinweise

Die Extraktion ( **>>**) Operator unterstützt das Laden aus einem Archiv.

##  <a name="operator_currency"></a>  COleCurrency::operator Währung

Gibt eine `CURRENCY` -Struktur, deren Wert wird aus dieser kopiert `COleCurrency` Objekt.

```
operator CURRENCY() const;
```

### <a name="remarks"></a>Hinweise

##  <a name="parsecurrency"></a>  COleCurrency::ParseCurrency

Rufen Sie diese Memberfunktion zum Analysieren einer Zeichenfolge zum Lesen eines Werts für die Währung.

```
BOOL ParseCurrency(
    LPCTSTR lpszCurrency,
    DWORD dwFlags = 0,
    LCID lcid = LANG_USER_DEFAULT);

throw(CMemoryException*);
throw(COleException*);
```

### <a name="parameters"></a>Parameter

*lpszCurrency*<br/>
Ein Zeiger auf die Null-terminierte Zeichenfolge, die analysiert werden soll.

*dwFlags*<br/>
Gibt Flags für die gebietsschemaeinstellungen, möglicherweise die folgenden Flags:

- LOCALE_NOUSEROVERRIDE verwenden Sie den Standard-gebietsschemaeinstellungen für System, anstelle von benutzerdefinierten Einstellungen.

*lcid*<br/>
Gibt die Gebietsschema-ID, für die Konvertierung verwendet.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Zeichenfolge erfolgreich, als Währungswert, andernfalls 0 konvertiert wurde.

### <a name="remarks"></a>Hinweise

Spezifikationen der lokalen Sprache (Gebietsschema-IDs) verwendet für die Bedeutung des nicht numerische Zeichen in der Quellzeichenfolge.

Eine Erläuterung der Gebietsschema-ID-Werten, finden Sie unter [unterstützen mehrere Sprachen](/previous-versions/windows/desktop/automat/supporting-multiple-national-languages).

Wenn die Zeichenfolge in eine Währung erfolgreich konvertiert wurde, den Wert dieses `COleCurrency` Objekt auf diesen Wert und ihren Status auf ungültig festgelegt ist.

Wenn die Zeichenfolge kein Währungswert konvertiert werden kann, oder es bei einem numerischen Überlauf, der den Status `COleCurrency` Objekt ist ungültig.

Wenn die zeichenfolgenkonvertierung aufgrund von Arbeitsspeicher aufgrund von Zuordnungsfehlern fehlgeschlagen ist, wird diese Funktion löst einen [CMemoryException](../../mfc/reference/cmemoryexception-class.md). In einem beliebigen anderen Fehlerzustand, die diese Funktion löst einen [COleException](../../mfc/reference/coleexception-class.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#13](../../mfc/codesnippet/cpp/colecurrency-class_9.cpp)]

##  <a name="colecurrency_relational_operators"></a>  COleCurrency-Operatoren (Relational)

Vergleicht zwei Currency-Werte und ungleich NULL, wenn die Bedingung "true" zurückgeben; andernfalls 0.

```
BOOL operator==(const COleCurrency& cur) const;
BOOL operator!=(const COleCurrency& cur) const;
BOOL operator<(const COleCurrency& cur) const;
BOOL operator>(const COleCurrency& cur) const;
BOOL operator<=(const COleCurrency& cur) const;
BOOL operator>=(const COleCurrency& cur) const;
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Der Rückgabewert der Bestellung Vorgänge ( **<**, **\< =**, **>**, **>=**) ist undefiniert, wenn der Status einer der Operanden null oder ungültig ist. Die Gleichheitsoperatoren ( `==`, `!=`) sollten Sie den Status der Operanden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#20](../../mfc/codesnippet/cpp/colecurrency-class_10.cpp)]

##  <a name="setcurrency"></a>  COleCurrency::SetCurrency

Rufen Sie diese Memberfunktion zum Festlegen der Einheiten und der Bruchteil dieser `COleCurrency` Objekt.

```
void SetCurrency(
    long nUnits,
    long nFractionalUnits);
```

### <a name="parameters"></a>Parameter

*nUnits*, *nFractionalUnits* geben die Einheiten und der Bruchteil (in 1/10.000) den Wert in diese kopiert werden `COleCurrency` Objekt.

### <a name="remarks"></a>Hinweise

Wenn der Bruchteil den absoluten Wert größer als 10.000 ist, erfolgt die entsprechende Anpassung an die Einheiten, wie die dritte von den folgenden Beispielen gezeigt.

Beachten Sie, dass die Einheiten und der Teil mit Bruchzahlen von long-Werte mit Vorzeichen angegeben werden. Die vierte von den folgenden Beispielen wird gezeigt, was geschieht, wenn die Parameter unterschiedliche Vorzeichen haben.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCOleContainer#14](../../mfc/codesnippet/cpp/colecurrency-class_11.cpp)]

##  <a name="setstatus"></a>  COleCurrency::SetStatus

Rufen Sie diese Memberfunktion zum Festlegen des in den Status (Gültigkeit) `COleCurrency` Objekt.

```
void SetStatus(CurrencyStatus  status  );
```

### <a name="parameters"></a>Parameter

*status*<br/>
Der neue Status für diesen `COleCurrency` Objekt.

### <a name="remarks"></a>Hinweise

Die *Status* Parameterwert wird definiert, indem die `CurrencyStatus` Enumerationstyp, der in definiert ist die `COleCurrency` Klasse.

```
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };
```

Eine kurze Beschreibung dieser Status-Werte finden Sie in der folgenden Liste:

- `COleCurrency::valid` Gibt an, das von diesem `COleCurrency` Objekt gültig ist.

- `COleCurrency::invalid` Gibt an, das von diesem `COleCurrency` Objekt ist ungültig; d. h. der Wert möglicherweise nicht korrekt.

- `COleCurrency::null` Gibt an, das von diesem `COleCurrency` Objekt null ist, d. h., dass für dieses Objekt kein Wert angegeben wurde. (Dies ist "null", in dem Sinne Database "kein Wert, wenn" im Gegensatz zu den C++-NULL).

> [!CAUTION]
>  Diese Funktion ist für die erweiterte programmierungssituationen. Diese Funktion wird die Daten in dieses Objekt nicht geändert. Es wird am häufigsten zum Festlegen des Status auf null oder ein ungültiges verwendet werden. Beachten Sie, dass der Zuweisungsoperator ( [Operator =](#operator_eq)) und [SetCurrency](#setcurrency) den Status des Objekts basierend auf den Werten der Datenquelle festgelegt.

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[COleVariant-Klasse](../../mfc/reference/colevariant-class.md)
