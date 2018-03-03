---
title: CComCurrency Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CComCurrency class
ms.assetid: a1c3d10a-bba6-40cc-8bcf-aed9023c8a9e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c3ef0cdc45d4f3b84c738e5eec24d76a1f9b7fe2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
|[CComCurrency:: Getfraction](#getfraction)|Rufen Sie diese Methode auf, um den Nachkommawert eines `CComCurrency`-Objekts zurückzugeben.|  
|[CComCurrency::GetInteger](#getinteger)|Rufen Sie diese Methode auf, um die ganzzahlige Komponente eines `CComCurrency`-Objekts zurückzugeben.|  
|[CComCurrency::Round](#round)|Rufen Sie diese Methode auf, um ein `CComCurrency`-Objekt auf den nächsten ganzzahligen Wert zu runden.|  
|[CComCurrency::SetFraction](#setfraction)|Rufen Sie diese Methode auf, um den Nachkommawert eines `CComCurrency`-Objekts festzulegen.|  
|[CComCurrency::SetInteger](#setinteger)|Rufen Sie diese Methode auf, um den ganzzahligen Wert eines `CComCurrency`-Objekts festzulegen.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComCurrency::operator-](#operator_-)|Dieser Operator wird verwendet, um Subtraktion für ein `CComCurrency`-Objekt auszuführen.|  
|[CComCurrency::operator! =](#operator_neq)|Überprüft zwei `CComCurrency`-Objekte auf Ungleichheit.|  
|[CComCurrency::operator *](#operator_star)|Dieser Operator wird verwendet, um Multiplikation für ein `CComCurrency`-Objekt auszuführen.|  
|[CComCurrency::operator * =](#operator_star_eq)|Dieser Operator wird verwendet, um Multiplikation für ein `CComCurrency`-Objekt auszuführen und ihm das Ergebnis zuzuweisen.|  
|[CComCurrency::operator /](#operator_div)|Dieser Operator wird verwendet, um Division für ein `CComCurrency`-Objekt auszuführen.|  
|[CComCurrency::operator / =](#operator_div_eq)|Dieser Operator wird verwendet, um Division für ein `CComCurrency`-Objekt auszuführen und ihm das Ergebnis zuzuweisen.|  
|[CComCurrency::operator +](#operator_add)|Dieser Operator wird verwendet, um Addition für ein `CComCurrency`-Objekt auszuführen.|  
|[CComCurrency::operator +=](#operator_add_eq)|Dieser Operator wird verwendet, um Addition für ein `CComCurrency`-Objekt auszuführen und das Ergebnis dem aktuellen Objekt zuzuweisen.|  
|[CComCurrency::operator <](#operator_lt)|Dieser Operator vergleicht zwei `CComCurrency`-Objekte, um das kleinere zu bestimmen.|  
|[CComCurrency::operator < =](#operator_lt_eq)|Dieser Operator vergleicht zwei `CComCurrency`-Objekte, um zu bestimmen, ob sie gleich sind oder welches kleiner ist.|  
|[CComCurrency::operator =](#operator_eq)|Dieser Operator weist dem `CComCurrency`-Objekt einen neuen Wert zu.|  
|[CComCurrency::operator =](#operator_-_eq)|Dieser Operator wird verwendet, um Subtraktion für ein `CComCurrency`-Objekt auszuführen und ihm das Ergebnis zuzuweisen.|  
|[CComCurrency::operator ==](#operator_eq_eq)|Dieser Operator überprüft zwei `CComCurrency`-Objekte auf Gleichheit.|  
|[CComCurrency::operator >](#operator_gt)|Dieser Operator vergleicht zwei `CComCurrency`-Objekte, um das größere zu bestimmen.|  
|[CComCurrency::operator > =](#operator_gt_eq)|Dieser Operator vergleicht zwei `CComCurrency`-Objekte, um zu bestimmen, ob sie gleich sind oder welches größer ist.|  
|[CComCurrency::operator Währung](#operator_currency)|Wandelt ein `CURRENCY`-Objekt um.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComCurrency::m_currency](#m_currency)|Die `CURRENCY`-Variable, die von der Klasseninstanz erstellt wurde.|  
  
## <a name="remarks"></a>Hinweise  
 `CComCurrency`ist ein Wrapper für die **Währung** -Datentyp. **Währung** als ein skaliert mit 10.000 zweier-Komplement-8-Byte-Integer-Wert implementiert wird. Dies ermöglicht eine Festkommazahl mit 15 Stellen links vom Dezimaltrennzeichen und 4 Ziffern rechts. Die **Währung** Datentyp ist äußerst nützlich für finanzberechnungen oder für festkommaberechnungen, in denen Genauigkeit wichtig ist.  
  
 Die **CComCurrency** Wrapper implementiert arithmetische, zuweisungs- und Vergleichsausdrücke Vorgänge für diesen festkommatyp. Die unterstützten Anwendungen wurden ausgewählt, um die Rundungsfehler zu steuern, die während der Festkommaberechnungen auftreten können.  
  
 Das `CComCurrency`-Objekt bietet Zugriff auf die Zahlen auf beiden Seiten des Dezimaltrennzeichens in der Form von zwei Komponenten: eine Ganzzahlkomponente, die den Wert links vom Dezimalzeichen speichert, und eine Nachkommakomponente, die den Wert rechts vom Dezimalzeichen speichert. Der Nachkommawert wird intern als eine ganze Zahl zwischen-9999 gespeichert ( **CY_MIN_FRACTION**) und + 9999 ( **CY_MAX_FRACTION**). Die Methode [CComCurrency:: Getfraction](#getfraction) gibt einen Wert mit einem Faktor von 10.000 skaliert ( **CY_SCALE**).  
  
 Beim Angeben von für ganze Zahlen und nachkommakomponenten von einem **CComCurrency** Objekt, denken Sie daran, dass der Nachkommawert eine Zahl im Bereich von 0 bis 9999 ist. Dies ist bei einer Währung wie z. B. dem US-Dollar wichtig, bei der die Summen nur mit zwei signifikante Ziffern nach dem Dezimaltrennzeichen ausgedrückt werden. Obwohl die letzten zwei Ziffern nicht angezeigt werden, müssen sie berücksichtigt werden.  
  
|Wert|Mögliche CComCurrency-Zuweisungen|  
|-----------|---------------------------------------|  
|$10.50|CComCurrency(10,5000) *oder* CComCurrency(10.50)|  
|$10.05|CComCurrency(10,500) *oder* CComCurrency(10.05)|  
  
 Die Werte **CY_MIN_FRACTION**, **CY_MAX_FRACTION**, und **CY_SCALE** in "atlcur.h" definiert sind.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** "atlcur.h"  
  
##  <a name="ccomcurrency"></a>CComCurrency::CComCurrency  
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
 `curSrc`  
 Ein vorhandenes `CComCurrency`-Objekt.  
  
 `cySrc`  
 Eine Variable vom Typ **Währung**.  
  
 `bSrc`, `dSrc`, `fSrc`, `lSrc`, *sSrc*, *UlSrc UsSrc*  
 Der Anfangswert der Membervariable `m_currency`.  
  
 `cSrc`  
 Ein Zeichen, die mit dem ersten Wert übergeben, um die Membervariable `m_currency`.  
  
 `nInteger`, *nFraction*  
 Ganze Zahlen und nachkommakomponenten von der ersten Währungswert. Finden Sie unter der [CComCurrency](../../atl/reference/ccomcurrency-class.md) Übersicht für Weitere Informationen.  
  
 `pDispSrc`  
 Ein `IDispatch` Zeiger.  
  
 *varSrc*  
 Eine Variable vom Typ **VARIANT**. Zum Durchführen der Konvertierung, wird das Gebietsschema des aktuellen Threads verwendet.  
  
 `szSrc`  
 Eine Unicode- oder ANSI-Zeichenfolge, die den anfänglichen Wert enthält. Zum Durchführen der Konvertierung, wird das Gebietsschema des aktuellen Threads verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Der Konstruktor legt den anfänglichen Wert des [CComCurrency::m_currency](#m_currency), und akzeptiert eine Vielzahl von Datentypen, z. B. ganze Zahlen, Zeichenfolgen, Gleitkommazahlen, **Währung** Variablen und andere `CComCurrency` Objekte. Wenn kein Wert angegeben ist, `m_currency` auf 0 festgelegt ist.  
  
 Im Falle eines Fehlers, wie ein Überlauf, die Konstruktoren, die eine leere Ausnahmespezifikation fehlen ( **throw()**) aufrufen `AtlThrow` mit HRESULT, der den Fehler beschreibt.  
  
 Wenn Gleitkomma "oder" double-Werte verwenden, um einen Wert zuzuweisen, beachten Sie, dass **CComCurrency(10.50)** entspricht **CComCurrency(10,5000)** und nicht **CComCurrency(10,50)**.  
  
##  <a name="getcurrencyptr"></a>CComCurrency::GetCurrencyPtr  
 Gibt die Adresse eines `m_currency`-Datenmembers zurück.  
  
```
CURRENCY* GetCurrencyPtr() throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Adresse des ein `m_currency` -Datenmember  
  
##  <a name="getfraction"></a>CComCurrency:: Getfraction  
 Rufen Sie diese Methode zum Zurückgeben des Nachkommawert von der `CComCurrency` Objekt.  
  
```
SHORT GetFraction() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt zurück, den Nachkommawert von der `m_currency` -Datenmember.  
  
### <a name="remarks"></a>Hinweise  
 Der Nachkommawert wird ein 4 Ziffern Integerwert zwischen-9999 ( **CY_MIN_FRACTION**) und + 9999 ( **CY_MAX_FRACTION**). `GetFraction`Gibt diesen Wert, der um 10000 skalierten zurück ( **CY_SCALE**). Die Werte der **CY_MIN_FRACTION**, **CY_MAX_FRACTION**, und **CY_SCALE** in "atlcur.h" definiert sind.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#50](../../atl/codesnippet/cpp/ccomcurrency-class_1.cpp)]  
  
##  <a name="getinteger"></a>CComCurrency::GetInteger  
 Rufen Sie diese Methode zum Abrufen der ganzzahligen Komponente von einem `CComCurrency` Objekt.  
  
```
LONGLONG GetInteger() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den ganzzahligen der `m_currency` -Datenmember.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#51](../../atl/codesnippet/cpp/ccomcurrency-class_2.cpp)]  
  
##  <a name="m_currency"></a>CComCurrency::m_currency  
 Die **Währung** -Datenmember.  
  
```
CURRENCY m_currency;
```  
  
### <a name="remarks"></a>Hinweise  
 Bei diesem Member enthält, die Währung zugegriffen und von den Methoden dieser Klasse bearbeitet wird.  
  
##  <a name="operator_-"></a>CComCurrency::operator-  
 Dieser Operator wird verwendet, um Subtraktion für ein `CComCurrency`-Objekt auszuführen.  
  
```
CComCurrency operator-() const;
CComCurrency operator-(const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Parameter  
 `cur`  
 Ein `CComCurrency`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine `CComCurrency` Objekt, das das Ergebnis der Subtraktion darstellt. Im Falle eines Fehlers, wie ein Überlauf dieser Operator ruft `AtlThrow` mit dem HRESULT, der den Fehler beschreibt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#55](../../atl/codesnippet/cpp/ccomcurrency-class_3.cpp)]  
  
##  <a name="operator_neq"></a>CComCurrency::operator! =  
 Dieser Operator vergleicht zwei Objekte auf Ungleichheit.  
  
```
bool operator!= (const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Parameter  
 `cur`  
 Das zu vergleichende `CComCurrency`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** ist das Element verglichenen nicht gleich der `CComCurrency` Objekt; andernfalls **"false"**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#56](../../atl/codesnippet/cpp/ccomcurrency-class_4.cpp)]  
  
##  <a name="operator_star"></a>CComCurrency::operator *  
 Dieser Operator wird verwendet, um Multiplikation für ein `CComCurrency`-Objekt auszuführen.  
  
```
CComCurrency operator*(long nOperand) const;
CComCurrency operator*(const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Parameter  
 `nOperand`  
 Der Multiplikator.  
  
 `cur`  
 Die `CComCurrency` als Multiplikator für die verwendete Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine `CComCurrency` Objekt, das das Ergebnis der Multiplikation darstellt. Im Falle eines Fehlers, wie ein Überlauf dieser Operator ruft `AtlThrow` mit dem HRESULT, der den Fehler beschreibt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#57](../../atl/codesnippet/cpp/ccomcurrency-class_5.cpp)]  
  
##  <a name="operator_star_eq"></a>CComCurrency::operator * =  
 Dieser Operator wird verwendet, um Multiplikation für ein `CComCurrency`-Objekt auszuführen und ihm das Ergebnis zuzuweisen.  
  
```
const CComCurrency& operator*= (long nOperand);
const CComCurrency& operator*= (const CComCurrency& cur);
```  
  
### <a name="parameters"></a>Parameter  
 `nOperand`  
 Der Multiplikator.  
  
 `cur`  
 Die `CComCurrency` als Multiplikator für die verwendete Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die aktualisierte `CComCurrency` Objekt. Im Falle eines Fehlers, wie ein Überlauf dieser Operator ruft `AtlThrow` mit dem HRESULT, der den Fehler beschreibt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#58](../../atl/codesnippet/cpp/ccomcurrency-class_6.cpp)]  
  
##  <a name="operator_div"></a>CComCurrency::operator /  
 Dieser Operator wird verwendet, um Division für ein `CComCurrency`-Objekt auszuführen.  
  
```
CComCurrency operator/(long nOperand) const;
```  
  
### <a name="parameters"></a>Parameter  
 `nOperand`  
 Der Divisor.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine `CComCurrency` Objekt, das das Ergebnis der Division darstellt. Wenn der Divisor 0 ist, wird ein Assertionsfehler ausgelöst.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#59](../../atl/codesnippet/cpp/ccomcurrency-class_7.cpp)]  
  
##  <a name="operator_div_eq"></a>CComCurrency::operator / =  
 Dieser Operator wird verwendet, um Division für ein `CComCurrency`-Objekt auszuführen und ihm das Ergebnis zuzuweisen.  
  
```
const CComCurrency& operator/= (long nOperand);
```  
  
### <a name="parameters"></a>Parameter  
 `nOperand`  
 Der Divisor.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die aktualisierte `CComCurrency` Objekt. Wenn der Divisor 0 ist, wird ein Assertionsfehler ausgelöst.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#60](../../atl/codesnippet/cpp/ccomcurrency-class_8.cpp)]  
  
##  <a name="operator_add"></a>CComCurrency::operator +  
 Dieser Operator wird verwendet, um Addition für ein `CComCurrency`-Objekt auszuführen.  
  
```
CComCurrency operator+(const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Parameter  
 `cur`  
 Die `CComCurrency` -Objekt, auf das ursprüngliche Objekt hinzugefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine `CComCurrency` Objekt, das das Ergebnis der Addition darstellt. Im Falle eines Fehlers, wie ein Überlauf dieser Operator ruft `AtlThrow` mit dem HRESULT, der den Fehler beschreibt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#61](../../atl/codesnippet/cpp/ccomcurrency-class_9.cpp)]  
  
##  <a name="operator_add_eq"></a>CComCurrency::operator +=  
 Dieser Operator wird verwendet, um Addition für ein `CComCurrency`-Objekt auszuführen und das Ergebnis dem aktuellen Objekt zuzuweisen.  
  
```
const CComCurrency& operator+= (const CComCurrency& cur);
```  
  
### <a name="parameters"></a>Parameter  
 `cur`  
 Das `CComCurrency`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die aktualisierte `CComCurrency` Objekt. Im Falle eines Fehlers, wie ein Überlauf dieser Operator ruft `AtlThrow` mit dem HRESULT, der den Fehler beschreibt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#62](../../atl/codesnippet/cpp/ccomcurrency-class_10.cpp)]  
  
##  <a name="operator_lt"></a>CComCurrency::operator&lt;  
 Dieser Operator vergleicht zwei `CComCurrency`-Objekte, um das kleinere zu bestimmen.  
  
```
bool operator<(const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Parameter  
 `cur`  
 Ein `CComCurrency`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** , wenn das erste Objekt kleiner ist als das zweite **"false"** andernfalls.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#63](../../atl/codesnippet/cpp/ccomcurrency-class_11.cpp)]  
  
##  <a name="operator_lt_eq"></a>CComCurrency::operator&lt;=  
 Dieser Operator vergleicht zwei `CComCurrency`-Objekte, um zu bestimmen, ob sie gleich sind oder welches kleiner ist.  
  
```
bool operator<= (const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Parameter  
 `cur`  
 Ein `CComCurrency`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** Wenn das erste Objekt kleiner als oder gleich dem zweiten **"false"** andernfalls.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#64](../../atl/codesnippet/cpp/ccomcurrency-class_12.cpp)]  
  
##  <a name="operator_eq"></a>CComCurrency::operator =  
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
 `curSrc`  
 Ein **CComCurrency** Objekt.  
  
 `cySrc`  
 Eine Variable vom Typ **Währung**.  
  
 *sSrc*, `fSrc`, `lSrc`, *bSrc*, *UsSrc*, `dSrc`, *cSrc*, *UlSrc*,`dSrc`  
 Der numerische Wert, der zum Zuweisen der `CComCurrency` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die aktualisierte `CComCurrency` Objekt. Im Falle eines Fehlers, wie ein Überlauf dieser Operator ruft `AtlThrow` mit dem HRESULT, der den Fehler beschreibt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#65](../../atl/codesnippet/cpp/ccomcurrency-class_13.cpp)]  
  
##  <a name="operator_-_eq"></a>CComCurrency::operator =  
 Dieser Operator wird verwendet, um Subtraktion für ein `CComCurrency`-Objekt auszuführen und ihm das Ergebnis zuzuweisen.  
  
```
const CComCurrency& operator-= (const CComCurrency& cur);
```  
  
### <a name="parameters"></a>Parameter  
 `cur`  
 Ein `CComCurrency`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die aktualisierte `CComCurrency` Objekt. Im Falle eines Fehlers, wie ein Überlauf dieser Operator ruft `AtlThrow` mit dem HRESULT, der den Fehler beschreibt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#66](../../atl/codesnippet/cpp/ccomcurrency-class_14.cpp)]  
  
##  <a name="operator_eq_eq"></a>CComCurrency::operator ==  
 Dieser Operator überprüft zwei `CComCurrency`-Objekte auf Gleichheit.  
  
```
bool operator== (const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Parameter  
 `cur`  
 Die `CComCurrency` zu vergleichende Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** , wenn die Objekte gleich sind (d. h. die `m_currency` Datenmember, beide ganze Zahl und Bruchteilen, in beiden Objekte den gleichen Wert aufweisen), **"false"** andernfalls.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#67](../../atl/codesnippet/cpp/ccomcurrency-class_15.cpp)]  
  
##  <a name="operator_gt"></a>CComCurrency::operator&gt;  
 Dieser Operator vergleicht zwei `CComCurrency`-Objekte, um das größere zu bestimmen.  
  
```
bool operator>(const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Parameter  
 `cur`  
 Ein `CComCurrency`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** ist das erste Objekt größer als das zweite **"false"** andernfalls.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#68](../../atl/codesnippet/cpp/ccomcurrency-class_16.cpp)]  
  
##  <a name="operator_gt_eq"></a>CComCurrency::operator&gt;=  
 Dieser Operator vergleicht zwei `CComCurrency`-Objekte, um zu bestimmen, ob sie gleich sind oder welches größer ist.  
  
```
bool operator>= (const CComCurrency& cur) const;
```  
  
### <a name="parameters"></a>Parameter  
 `cur`  
 Ein `CComCurrency`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** ist das erste Objekt größer als oder gleich dem zweiten **"false"** andernfalls.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#69](../../atl/codesnippet/cpp/ccomcurrency-class_17.cpp)]  
  
##  <a name="operator_currency"></a>CComCurrency::operator Währung  
 Diese Operatoren werden verwendet, um die Umwandlung einer `CComCurrency` -Objekt an eine **Währung** -Datentyp.  
  
```  
operator CURRENCY&() throw();
operator const CURRENCY&() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf eine **Währung** Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#70](../../atl/codesnippet/cpp/ccomcurrency-class_18.cpp)]  
  
##  <a name="round"></a>CComCurrency::Round  
 Rufen Sie diese Methode, um die Währung auf eine angegebene Anzahl von Dezimalstellen gerundet.  
  
```
HRESULT Roundint nDecimals);
```  
  
### <a name="parameters"></a>Parameter  
 *nDecimals*  
 Die Anzahl der Ziffern, `m_currency` abgerundet wird, im Bereich von 0 bis 4.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#52](../../atl/codesnippet/cpp/ccomcurrency-class_19.cpp)]  
  
##  <a name="setfraction"></a>CComCurrency::SetFraction  
 Rufen Sie diese Methode auf, um den Nachkommawert eines `CComCurrency`-Objekts festzulegen.  
  
```
HRESULT SetFraction(SHORT nFraction);
```  
  
### <a name="parameters"></a>Parameter  
 *nFraction*  
 Der Wert der Nachkommawert von zuzuweisenden das `m_currency` -Datenmember. Das Vorzeichen der Nachkommawert muss identisch mit der ganzzahligen Komponente, und des Werts muss im Bereich von-9999 ( **CY_MIN_FRACTION**), + 9999 ( **CY_MAX_FRACTION**).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#53](../../atl/codesnippet/cpp/ccomcurrency-class_20.cpp)]  
  
##  <a name="setinteger"></a>CComCurrency::SetInteger  
 Rufen Sie diese Methode auf, um den ganzzahligen Wert eines `CComCurrency`-Objekts festzulegen.  
  
```
HRESULT SetInteger(LONGLONG nInteger);
```  
  
### <a name="parameters"></a>Parameter  
 `nInteger`  
 Der Wert, den ganzzahligen zuzuweisenden das `m_currency` -Datenmember. Die Vorzeichen der ganzzahligen Komponente müssen die Vorzeichen des vorhandenen Nachkommawert übereinstimmen.  
  
 `nInteger`muss im Bereich **CY_MIN_INTEGER** auf **CY_MAX_INTEGER** inklusive. Diese Werte werden in "atlcur.h" definiert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `S_OK` auf Erfolg oder Fehler `HRESULT` bei einem Fehler.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_Utilities#54](../../atl/codesnippet/cpp/ccomcurrency-class_21.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [COleCurrency-Klasse](../../mfc/reference/colecurrency-class.md)   
 [WÄHRUNG](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
