---
title: CComCurrency-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComCurrency
- ATLCUR/ATL::CComCurrency
- ATLCUR/ATL::CComCurrency::CComCurrency
- ATLCUR/ATL::CComCurrency::GetCurrencyPtr
- ATLCUR/ATL::CComCurrency::GetFraction
- ATLCUR/ATL::CComCurrency::GetInteger
- ATLCUR/ATL::CComCurrency::Round
- ATLCUR/ATL::CComCurrency::SetFraction
- ATLCUR/ATL::CComCurrency::SetInteger
- ATLCUR/ATL::CComCurrency::m_currency
helpviewer_keywords:
- CComCurrency class
ms.assetid: a1c3d10a-bba6-40cc-8bcf-aed9023c8a9e
ms.openlocfilehash: 11463b7113876abdf0743b9f8c7df373fadd99ef
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497293"
---
# <a name="ccomcurrency-class"></a>CComCurrency-Klasse

`CComCurrency` verfügt über Methoden und Operatoren zum Erstellen und Verwalten eines CURRENCY-Objekts.

## <a name="syntax"></a>Syntax

```
class CComCurrency
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComCurrency::CComCurrency](#ccomcurrency)|Der Konstruktor für ein `CComCurrency`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComCurrency::GetCurrencyPtr](#getcurrencyptr)|Gibt die Adresse eines `m_currency`-Datenmembers zurück.|
|[CComCurrency::GetFraction](#getfraction)|Rufen Sie diese Methode auf, um den Nachkommawert eines `CComCurrency`-Objekts zurückzugeben.|
|[CComCurrency::GetInteger](#getinteger)|Rufen Sie diese Methode auf, um die ganzzahlige Komponente eines `CComCurrency`-Objekts zurückzugeben.|
|[CComCurrency::Round](#round)|Rufen Sie diese Methode auf, um ein `CComCurrency`-Objekt auf den nächsten ganzzahligen Wert zu runden.|
|[CComCurrency::SetFraction](#setfraction)|Rufen Sie diese Methode auf, um den Nachkommawert eines `CComCurrency`-Objekts festzulegen.|
|[CComCurrency::SetInteger](#setinteger)|Rufen Sie diese Methode auf, um den ganzzahligen Wert eines `CComCurrency`-Objekts festzulegen.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CComCurrency::operator -](#operator_-)|Dieser Operator wird verwendet, um Subtraktion für ein `CComCurrency`-Objekt auszuführen.|
|[CComCurrency::operator !=](#operator_neq)|Überprüft zwei `CComCurrency`-Objekte auf Ungleichheit.|
|[CComCurrency:: Operator *](#operator_star)|Dieser Operator wird verwendet, um Multiplikation für ein `CComCurrency`-Objekt auszuführen.|
|[CComCurrency::operator *=](#operator_star_eq)|Dieser Operator wird verwendet, um Multiplikation für ein `CComCurrency`-Objekt auszuführen und ihm das Ergebnis zuzuweisen.|
|[CComCurrency::operator /](#operator_div)|Dieser Operator wird verwendet, um Division für ein `CComCurrency`-Objekt auszuführen.|
|[CComCurrency::operator /=](#operator_div_eq)|Dieser Operator wird verwendet, um Division für ein `CComCurrency`-Objekt auszuführen und ihm das Ergebnis zuzuweisen.|
|[CComCurrency:: Operator +](#operator_add)|Dieser Operator wird verwendet, um Addition für ein `CComCurrency`-Objekt auszuführen.|
|[CComCurrency::operator +=](#operator_add_eq)|Dieser Operator wird verwendet, um Addition für ein `CComCurrency`-Objekt auszuführen und das Ergebnis dem aktuellen Objekt zuzuweisen.|
|[CComCurrency:: Operator-<](#operator_lt)|Dieser Operator vergleicht zwei `CComCurrency`-Objekte, um das kleinere zu bestimmen.|
|[CComCurrency::operator <=](#operator_lt_eq)|Dieser Operator vergleicht zwei `CComCurrency`-Objekte, um zu bestimmen, ob sie gleich sind oder welches kleiner ist.|
|[CComCurrency::operator =](#operator_eq)|Dieser Operator weist dem `CComCurrency`-Objekt einen neuen Wert zu.|
|[CComCurrency::operator -=](#operator_-_eq)|Dieser Operator wird verwendet, um Subtraktion für ein `CComCurrency`-Objekt auszuführen und ihm das Ergebnis zuzuweisen.|
|[CComCurrency::operator ==](#operator_eq_eq)|Dieser Operator überprüft zwei `CComCurrency`-Objekte auf Gleichheit.|
|[CComCurrency::operator >](#operator_gt)|Dieser Operator vergleicht zwei `CComCurrency`-Objekte, um das größere zu bestimmen.|
|[CComCurrency::operator >=](#operator_gt_eq)|Dieser Operator vergleicht zwei `CComCurrency`-Objekte, um zu bestimmen, ob sie gleich sind oder welches größer ist.|
|[CComCurrency:: Operator Währung](#operator_currency)|Wandelt ein Währungs Objekt um.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CComCurrency::m_currency](#m_currency)|Die von der Klasseninstanz erstellte Währungs Variable.|

## <a name="remarks"></a>Hinweise

`CComCurrency`ist ein Wrapper für den Currency-Datentyp. Die Währung wird als ganzzahliger 8-Byte-zweit Wert Wert implementiert, der von 10.000 skaliert wird. Dies ermöglicht eine Festkommazahl mit 15 Stellen links vom Dezimaltrennzeichen und 4 Ziffern rechts. Der Currency-Datentyp ist für Berechnungen, die Geld betreffen, oder für alle fest Komma Berechnungen, bei denen die Genauigkeit wichtig ist, äußerst nützlich.

Der `CComCurrency` Wrapper implementiert arithmetische, Zuweisungs-und Vergleichs Vorgänge für diesen fest kommatyp. Die unterstützten Anwendungen wurden ausgewählt, um die Rundungsfehler zu steuern, die während der Festkommaberechnungen auftreten können.

Das `CComCurrency`-Objekt bietet Zugriff auf die Zahlen auf beiden Seiten des Dezimaltrennzeichens in der Form von zwei Komponenten: eine Ganzzahlkomponente, die den Wert links vom Dezimalzeichen speichert, und eine Nachkommakomponente, die den Wert rechts vom Dezimalzeichen speichert. Die Bruchteile werden intern als ganzzahliger Wert zwischen-9999 (CY_MIN_FRACTION) und + 9999 (CY_MAX_FRACTION) gespeichert. Die [CComCurrency:: getbruchmethode](#getfraction) gibt einen Wert zurück, der mit dem Faktor 10000 (CY_SCALE) skaliert wird.

Beachten Sie beim Angeben der ganzzahligen und der `CComCurrency` Bruchteile eines-Objekts, dass es sich bei der Bruchteil-Komponente um eine Zahl im Bereich von 0 bis 9999 handelt. Dies ist bei einer Währung wie z. B. dem US-Dollar wichtig, bei der die Summen nur mit zwei signifikante Ziffern nach dem Dezimaltrennzeichen ausgedrückt werden. Obwohl die letzten zwei Ziffern nicht angezeigt werden, müssen sie berücksichtigt werden.

|Wert|Mögliche CComCurrency-Zuweisungen|
|-----------|---------------------------------------|
|$10.50|CComCurrency (10, 5000) *oder* CComCurrency (10.50)|
|$10.05|CComCurrency (10500) *oder* CComCurrency (10.05)|

Die Werte CY_MIN_FRACTION, CY_MAX_FRACTION und CY_SCALE werden in "atlcur. h" definiert.

## <a name="requirements"></a>Anforderungen

**Header:** atlcur. h

##  <a name="ccomcurrency"></a>CComCurrency:: CComCurrency

Der Konstruktor.

```
CComCurrency() throw();
CComCurrency(const CComCurrency& curSrc) throw();
CComCurrency(CURRENCY cySrc) throw();
CComCurrency(DECIMAL dSrc);
CComCurrency(ULONG ulSrc);
CComCurrency(USHORT usSrc);
CComCurrency(CHAR cSrc);
CComCurrency(DOUBLE dSrc);
CComCurrency(FLOAT fSrc);
CComCurrency(LONG lSrc);
CComCurrency(SHORT sSrc);
CComCurrency(BYTE bSrc);
CComCurrency(LONGLONG nInteger, SHORT nFraction);
explicit CComCurrency(LPDISPATCH pDispSrc);
explicit CComCurrency(const VARIANT& varSrc);
explicit CComCurrency(LPCWSTR szSrc);
explicit CComCurrency(LPCSTR szSrc);
```

### <a name="parameters"></a>Parameter

*curSrc*<br/>
Ein vorhandenes `CComCurrency`-Objekt.

*cySrc*<br/>
Eine Variable vom Typ Currency.

*bSrc*, *dSrc*, *fSrc*, *lSrc*, *sSrc*, *ulSrc, usSrc*<br/>
Der Anfangswert, der der Element Variablen `m_currency`zugewiesen ist.

*cSrc*<br/>
Ein Zeichen, das den Anfangswert der Element Variablen `m_currency`enthält.

*nInteger*, *nFraction*<br/>
Die ganzzahligen und Bruch enden Komponenten des anfänglichen monetären Werts. Weitere Informationen finden Sie in der Übersicht über [CComCurrency](../../atl/reference/ccomcurrency-class.md) .

*pDispSrc*<br/>
Ein `IDispatch` -Zeiger.

*varSrc*<br/>
Eine Variable vom Typ Variant. Das Gebiets Schema des aktuellen Threads wird zum Durchführen der Konvertierung verwendet.

*szSrc*<br/>
Eine Unicode-oder ANSI-Zeichenfolge, die den Anfangswert enthält. Das Gebiets Schema des aktuellen Threads wird zum Durchführen der Konvertierung verwendet.

### <a name="remarks"></a>Hinweise

Der-Konstruktor legt den Anfangswert von [CComCurrency:: m_currency](#m_currency)fest und akzeptiert einen großen Bereich von Datentypen, einschließlich Ganzzahlen, Zeichen folgen, Gleit Komma Zahlen, Währungs Variablen und anderen `CComCurrency` Objekten. Wenn kein Wert angegeben wird, `m_currency` wird auf 0 festgelegt.

Im Fall eines Fehlers, z. b. eines Überlaufs, fehlt für die Konstruktoren, die einen leeren Ausnahme Spezifikations Befehl `AtlThrow` (**throw ()** ) haben, mit einem HRESULT, das den Fehler beschreibt.

Beachten Sie beim Verwenden von Gleit Komma-oder Double-Werten zum Zuweisen eines `CComCurrency(10.50)` Werts, dass `CComCurrency(10,5000)` gleich und `CComCurrency(10,50)`nicht ist.

##  <a name="getcurrencyptr"></a>CComCurrency:: GetCurrency. tr

Gibt die Adresse eines `m_currency`-Datenmembers zurück.

```
CURRENCY* GetCurrencyPtr() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Adresse eines `m_currency` Datenmembers zurück.

##  <a name="getfraction"></a>CComCurrency:: getbruchzahl

Ruft diese Methode auf, um die Bruchteile der Komponente `CComCurrency` des-Objekts zurückzugeben.

```
SHORT GetFraction() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt die Dezimalstellen Komponente des `m_currency` Datenmembers zurück.

### <a name="remarks"></a>Hinweise

Die Bruchteile Komponente ist ein vierstelliger ganzzahliger Wert zwischen-9999 (CY_MIN_FRACTION) und + 9999 (CY_MAX_FRACTION). `GetFraction`gibt diesen durch 10000 (CY_SCALE) skalierten Wert zurück. Die Werte von CY_MIN_FRACTION, CY_MAX_FRACTION und CY_SCALE werden in "atlcur. h" definiert.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#50](../../atl/codesnippet/cpp/ccomcurrency-class_1.cpp)]

##  <a name="getinteger"></a>CComCurrency:: GetInteger

Mit dieser Methode können Sie die ganzzahlige Komponente `CComCurrency` eines-Objekts abrufen.

```
LONGLONG GetInteger() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt die ganzzahlige Komponente `m_currency` des Datenmembers zurück.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#51](../../atl/codesnippet/cpp/ccomcurrency-class_2.cpp)]

##  <a name="m_currency"></a>CComCurrency:: m_currency

Der Currency-Datenmember.

```
CURRENCY m_currency;
```

### <a name="remarks"></a>Hinweise

Dieser Member enthält die Währung, auf die von den Methoden dieser Klasse zugegriffen wird.

##  <a name="operator_-"></a>CComCurrency:: Operator-

Dieser Operator wird verwendet, um Subtraktion für ein `CComCurrency`-Objekt auszuführen.

```
CComCurrency operator-() const;
CComCurrency operator-(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parameter

*cur*<br/>
Ein `CComCurrency`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt ein `CComCurrency` -Objekt zurück, das das Ergebnis der Subtraktion darstellt. Im Fall eines Fehlers, z. b. eines Überlaufs, ruft `AtlThrow` dieser Operator mit einem HRESULT auf, das den Fehler beschreibt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#55](../../atl/codesnippet/cpp/ccomcurrency-class_3.cpp)]

##  <a name="operator_neq"></a>CComCurrency:: Operator! =

Dieser Operator vergleicht zwei-Objekte auf Ungleichheit.

```
bool operator!= (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parameter

*cur*<br/>
Das zu vergleichende `CComCurrency`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn das verglichene Element nicht gleich `CComCurrency` dem-Objekt ist, andernfalls false.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#56](../../atl/codesnippet/cpp/ccomcurrency-class_4.cpp)]

##  <a name="operator_star"></a>CComCurrency:: Operator *

Dieser Operator wird verwendet, um Multiplikation für ein `CComCurrency`-Objekt auszuführen.

```
CComCurrency operator*(long nOperand) const;
CComCurrency operator*(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parameter

*nOperand*<br/>
Der Multiplikator.

*cur*<br/>
Das `CComCurrency` als Multiplikator verwendete-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt ein `CComCurrency` -Objekt zurück, das das Ergebnis der Multiplikation darstellt. Im Fall eines Fehlers, z. b. eines Überlaufs, ruft `AtlThrow` dieser Operator mit einem HRESULT auf, das den Fehler beschreibt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#57](../../atl/codesnippet/cpp/ccomcurrency-class_5.cpp)]

##  <a name="operator_star_eq"></a>CComCurrency::-Operator\*=

Dieser Operator wird verwendet, um Multiplikation für ein `CComCurrency`-Objekt auszuführen und ihm das Ergebnis zuzuweisen.

```
const CComCurrency& operator*= (long nOperand);
const CComCurrency& operator*= (const CComCurrency& cur);
```

### <a name="parameters"></a>Parameter

*nOperand*<br/>
Der Multiplikator.

*cur*<br/>
Das `CComCurrency` als Multiplikator verwendete-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt das aktualisierte `CComCurrency` Objekt zurück. Im Fall eines Fehlers, z. b. eines Überlaufs, ruft `AtlThrow` dieser Operator mit einem HRESULT auf, das den Fehler beschreibt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#58](../../atl/codesnippet/cpp/ccomcurrency-class_6.cpp)]

##  <a name="operator_div"></a>CComCurrency:: Operator/

Dieser Operator wird verwendet, um Division für ein `CComCurrency`-Objekt auszuführen.

```
CComCurrency operator/(long nOperand) const;
```

### <a name="parameters"></a>Parameter

*nOperand*<br/>
Der Divisor.

### <a name="return-value"></a>Rückgabewert

Gibt ein `CComCurrency` -Objekt zurück, das das Ergebnis der Division darstellt. Wenn der Divisor gleich 0 ist, tritt ein Assert-Fehler auf.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#59](../../atl/codesnippet/cpp/ccomcurrency-class_7.cpp)]

##  <a name="operator_div_eq"></a>CComCurrency:: Operator/=

Dieser Operator wird verwendet, um Division für ein `CComCurrency`-Objekt auszuführen und ihm das Ergebnis zuzuweisen.

```
const CComCurrency& operator/= (long nOperand);
```

### <a name="parameters"></a>Parameter

*nOperand*<br/>
Der Divisor.

### <a name="return-value"></a>Rückgabewert

Gibt das aktualisierte `CComCurrency` Objekt zurück. Wenn der Divisor gleich 0 ist, tritt ein Assert-Fehler auf.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#60](../../atl/codesnippet/cpp/ccomcurrency-class_8.cpp)]

##  <a name="operator_add"></a>CComCurrency:: Operator +

Dieser Operator wird verwendet, um Addition für ein `CComCurrency`-Objekt auszuführen.

```
CComCurrency operator+(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parameter

*cur*<br/>
Das `CComCurrency` -Objekt, das dem ursprünglichen-Objekt hinzugefügt werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt ein `CComCurrency` -Objekt zurück, das das Ergebnis der Addition darstellt. Im Fall eines Fehlers, z. b. eines Überlaufs, ruft `AtlThrow` dieser Operator mit einem HRESULT auf, das den Fehler beschreibt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#61](../../atl/codesnippet/cpp/ccomcurrency-class_9.cpp)]

##  <a name="operator_add_eq"></a>CComCurrency:: Operator + =

Dieser Operator wird verwendet, um Addition für ein `CComCurrency`-Objekt auszuführen und das Ergebnis dem aktuellen Objekt zuzuweisen.

```
const CComCurrency& operator+= (const CComCurrency& cur);
```

### <a name="parameters"></a>Parameter

*cur*<br/>
Das `CComCurrency`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt das aktualisierte `CComCurrency` Objekt zurück. Im Fall eines Fehlers, z. b. eines Überlaufs, ruft `AtlThrow` dieser Operator mit einem HRESULT auf, das den Fehler beschreibt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#62](../../atl/codesnippet/cpp/ccomcurrency-class_10.cpp)]

##  <a name="operator_lt"></a>CComCurrency::-Operator&lt;

Dieser Operator vergleicht zwei `CComCurrency`-Objekte, um das kleinere zu bestimmen.

```
bool operator<(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parameter

*cur*<br/>
Ein `CComCurrency`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn das erste Objekt kleiner als das zweite Objekt ist, andernfalls false.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#63](../../atl/codesnippet/cpp/ccomcurrency-class_11.cpp)]

##  <a name="operator_lt_eq"></a>CComCurrency::-Operator&lt;=

Dieser Operator vergleicht zwei `CComCurrency`-Objekte, um zu bestimmen, ob sie gleich sind oder welches kleiner ist.

```
bool operator<= (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parameter

*cur*<br/>
Ein `CComCurrency`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn das erste Objekt kleiner oder gleich dem zweiten ist, andernfalls "false".

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#64](../../atl/codesnippet/cpp/ccomcurrency-class_12.cpp)]

##  <a name="operator_eq"></a>CComCurrency:: Operator =

Dieser Operator weist dem `CComCurrency`-Objekt einen neuen Wert zu.

```
const CComCurrency& operator= (const CComCurrency& curSrc) throw();
const CComCurrency& operator= (CURRENCY cySrc) throw();
const CComCurrency& operator= (FLOAT fSrc);
const CComCurrency& operator= (SHORT sSrc);
const CComCurrency& operator= (LONG lSrc);
const CComCurrency& operator= (BYTE bSrc);
const CComCurrency& operator= (USHORT usSrc);
const CComCurrency& operator= (DOUBLE dSrc);
const CComCurrency& operator= (CHAR cSrc);
const CComCurrency& operator= (ULONG ulSrc);
const CComCurrency& operator= (DECIMAL dSrc);
```

### <a name="parameters"></a>Parameter

*curSrc*<br/>
Ein `CComCurrency`-Objekt.

*cySrc*<br/>
Eine Variable vom Typ Currency.

*sSrc*, *fSrc*, *lSrc*, *bSrc*, *usSrc*, *dSrc*, *cSrc*, *ulSrc*, *dSrc*<br/>
Der numerische Wert, der dem `CComCurrency` -Objekt zugewiesen werden soll.

### <a name="return-value"></a>Rückgabewert

Gibt das aktualisierte `CComCurrency` Objekt zurück. Im Fall eines Fehlers, z. b. eines Überlaufs, ruft `AtlThrow` dieser Operator mit einem HRESULT auf, das den Fehler beschreibt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#65](../../atl/codesnippet/cpp/ccomcurrency-class_13.cpp)]

##  <a name="operator_-_eq"></a>CComCurrency:: Operator-=

Dieser Operator wird verwendet, um Subtraktion für ein `CComCurrency`-Objekt auszuführen und ihm das Ergebnis zuzuweisen.

```
const CComCurrency& operator-= (const CComCurrency& cur);
```

### <a name="parameters"></a>Parameter

*cur*<br/>
Ein `CComCurrency`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt das aktualisierte `CComCurrency` Objekt zurück. Im Fall eines Fehlers, z. b. eines Überlaufs, ruft `AtlThrow` dieser Operator mit einem HRESULT auf, das den Fehler beschreibt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#66](../../atl/codesnippet/cpp/ccomcurrency-class_14.cpp)]

##  <a name="operator_eq_eq"></a>CComCurrency:: Operator = =

Dieser Operator überprüft zwei `CComCurrency`-Objekte auf Gleichheit.

```
bool operator== (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parameter

*cur*<br/>
Das `CComCurrency` zu vergleichende Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn die Objekte gleich sind (d. `m_currency` h., die Datenmember (Integer und Bruch), in beiden Objekten denselben Wert), andernfalls false.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#67](../../atl/codesnippet/cpp/ccomcurrency-class_15.cpp)]

##  <a name="operator_gt"></a>CComCurrency::-Operator&gt;

Dieser Operator vergleicht zwei `CComCurrency`-Objekte, um das größere zu bestimmen.

```
bool operator>(const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parameter

*cur*<br/>
Ein `CComCurrency`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn das erste Objekt größer als das zweite Objekt ist, andernfalls "false".

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#68](../../atl/codesnippet/cpp/ccomcurrency-class_16.cpp)]

##  <a name="operator_gt_eq"></a>CComCurrency::-Operator&gt;=

Dieser Operator vergleicht zwei `CComCurrency`-Objekte, um zu bestimmen, ob sie gleich sind oder welches größer ist.

```
bool operator>= (const CComCurrency& cur) const;
```

### <a name="parameters"></a>Parameter

*cur*<br/>
Ein `CComCurrency`-Objekt.

### <a name="return-value"></a>Rückgabewert

Gibt true zurück, wenn das erste Objekt größer als oder gleich dem zweiten Objekt ist, andernfalls false.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#69](../../atl/codesnippet/cpp/ccomcurrency-class_17.cpp)]

##  <a name="operator_currency"></a>CComCurrency:: Operator Währung

Diese Operatoren werden verwendet, um `CComCurrency` ein-Objekt in einen Currency-Datentyp umzuwandeln.

```
operator CURRENCY&() throw();
operator const CURRENCY&() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Verweis auf ein Währungs Objekt zurück.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#70](../../atl/codesnippet/cpp/ccomcurrency-class_18.cpp)]

##  <a name="round"></a>CComCurrency:: Round

Ruft diese Methode auf, um die Währung auf eine angegebene Anzahl von Dezimalstellen zu runden.

```
HRESULT Roundint nDecimals);
```

### <a name="parameters"></a>Parameter

*nDecimals*<br/>
Die Anzahl der Ziffern, auf `m_currency` die gerundet wird, im Bereich von 0 bis 4.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#52](../../atl/codesnippet/cpp/ccomcurrency-class_19.cpp)]

##  <a name="setfraction"></a>CComCurrency:: setbruchteil

Rufen Sie diese Methode auf, um den Nachkommawert eines `CComCurrency`-Objekts festzulegen.

```
HRESULT SetFraction(SHORT nFraction);
```

### <a name="parameters"></a>Parameter

*nFraction*<br/>
Der Wert, der der Bruchteil-Komponente des `m_currency` Datenmembers zugewiesen werden soll. Das Vorzeichen der Bruchteil-Komponente muss mit der ganzzahligen Komponente identisch sein, und der Wert muss im Bereich von-9999 (CY_MIN_FRACTION) bis + 9999 (CY_MAX_FRACTION) liegen.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#53](../../atl/codesnippet/cpp/ccomcurrency-class_20.cpp)]

##  <a name="setinteger"></a>CComCurrency:: SetInteger

Rufen Sie diese Methode auf, um den ganzzahligen Wert eines `CComCurrency`-Objekts festzulegen.

```
HRESULT SetInteger(LONGLONG nInteger);
```

### <a name="parameters"></a>Parameter

*nInteger*<br/>
Der Wert, der der ganzzahligen Komponente des `m_currency` Datenmembers zugewiesen werden soll. Das Vorzeichen der ganzzahligen Komponente muss mit dem Vorzeichen der vorhandenen Bruchteil-Komponente identisch sein.

*ninteger* muss im Bereich von CY_MIN_INTEGER bis CY_MAX_INTEGER einschließlich liegen. Diese Werte werden in "atlcur. h" definiert.

### <a name="return-value"></a>Rückgabewert

Gibt bei Erfolg S_OK oder einen fehlerhaften HRESULT bei einem Fehler zurück.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Utilities#54](../../atl/codesnippet/cpp/ccomcurrency-class_21.cpp)]

## <a name="see-also"></a>Siehe auch

[COleCurrency-Klasse](../../mfc/reference/colecurrency-class.md)<br/>
[WÄHRUNGS](/windows/win32/api/wtypes/ns-wtypes-cy)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
