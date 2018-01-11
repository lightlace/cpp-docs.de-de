---
title: COleCurrency-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
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
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a8d20b0f61fc7773899e671bec5b252ef2af1abf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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
|[COleCurrency::Format](#format)|Generiert eine formatierte Zeichenfolgendarstellung ein `COleCurrency` Objekt.|  
|[COleCurrency::GetStatus](#getstatus)|Ruft ab, der den Status (Gültigkeit) `COleCurrency` Objekt.|  
|[COleCurrency::ParseCurrency](#parsecurrency)|Liest eine **Währung** Wert aus einer Zeichenfolge und legt den Wert des `COleCurrency`.|  
|[COleCurrency::SetCurrency](#setcurrency)|Legt den Wert dieses `COleCurrency` Objekt.|  
|[COleCurrency::SetStatus](#setstatus)|Legt den Status (Gültigkeitsdauer) für diesen `COleCurrency` Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Operator =](#operator_eq)|Kopiert ein `COleCurrency` Wert.|  
|[Operator +, -](#operator_plus_minus)|Fügt subtrahiert und Änderungen Vorzeichen `COleCurrency` Werte.|  
|[Operator +=, =](#operator_plus_minus_eq)|Fügt und subtrahiert einen `COleCurrency` Wert aus diesem `COleCurrency` Objekt.|  
|[Operator * /](#operator_star)|Skaliert ein `COleCurrency` Wert von einem ganzzahligen Wert.|  
|[Operator * =, / =](#operator_star_div_eq)|Skaliert das `COleCurrency` Wert von einem ganzzahligen Wert.|  
|[Operator <<](#operator_stream)|Ausgaben einen `COleCurrency` Wert `CArchive` oder `CDumpContext`.|  
|[Operator >>](#operator_stream)|Eingaben ein `COleCurrency` -Sitzungsobjekts `CArchive`.|  
|[Operator Währung](#operator_currency)|Konvertiert eine `COleCurrency` -Wert in einen **Währung**.|  
|[Operator ==, <, < = usw..](#colecurrency_relational_operators)|Vergleicht zwei `COleCurrency` Werte.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleCurrency::m_cur](#m_cur)|Enthält die zugrunde liegende **Währung** dafür `COleCurrency` Objekt.|  
|[COleCurrency::m_status](#m_status)|Enthält den Status dieses `COleCurrency` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 **COleCurrency** verfügt nicht über eine Basisklasse.  
  
 **Währung** wird als eine 8-Byte, skaliert mit 10.000 zweier-Komplement Integer-Wert implementiert. Dies ermöglicht eine Festkommazahl mit 15 Stellen links vom Dezimaltrennzeichen und 4 Ziffern rechts. Die **Währung** Datentyp ist äußerst nützlich für finanzberechnungen oder für alle Berechnungsmethode, in denen Genauigkeit wichtig ist. Dies ist eine der möglichen Typen für die `VARIANT` -Datentyp der OLE-Automatisierung.  
  
 **COleCurrency** implementiert auch einige grundlegende arithmetischen Operationen für diesen festkommatyp. Die unterstützten Vorgänge wurden ausgewählt, um die Rundungsfehler zu steuern, die während der festkommaberechnungen auftreten.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `COleCurrency`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdisp.h  
  
##  <a name="colecurrency"></a>COleCurrency::COleCurrency  
 Erstellt eine **COleCurrency** Objekt.  
  
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
 `cySrc`  
 Ein **Währung** Wert an, in das neue kopiert werden **COleCurrency** Objekt.  
  
 `curSrc`  
 Eine vorhandene **COleCurrency** -Objekt, in das neue kopiert werden **COleCurrency** Objekt.  
  
 *varSrc*  
 Eine vorhandene **VARIANT** Datenstruktur (möglicherweise einer `COleVariant` Objekt), um eine Currency-Wert konvertiert werden soll ( `VT_CY`) und kopiert Sie in das neue **COleCurrency** Objekt.  
  
 `nUnits`, `nFractionalUnits`  
 Geben Sie an der Einheiten und der Bruchteil (in 1/10 Tausende) den Wert in das neue kopiert werden **COleCurrency** Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Alle diese Konstruktoren erstellen Sie eine neue **COleCurrency** Objekte, die auf den angegebenen Wert initialisiert. Eine kurze Beschreibung jeder dieser Konstruktoren folgt. Sofern nicht anders angegeben, den Status der neuen **COleCurrency** Element zu gültigen festgelegt ist.  
  
- COleCurrency() Konstrukte eine **COleCurrency** Objekt mit 0 (null) initialisiert.  
  
- COleCurrency (`cySrc`) erstellt eine **COleCurrency** -Objekt aus einem [Währung](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e) Wert.  
  
- COleCurrency (`curSrc`) erstellt eine **COleCurrency** Objekt aus einer vorhandenen **COleCurrency** Objekt. Das neue Objekt hat den gleichen Status wie das Quellobjekt.  
  
- COleCurrency (`varSrc`) erstellt eine **COleCurrency** Objekt. Versucht, Konvertieren einer [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) Struktur oder `COleVariant` Objekt, das eine Währung ( `VT_CY`) Wert. Wenn die Konvertierung erfolgreich ist, wird der konvertierte Wert kopiert, in das neue **COleCurrency** Objekt. Ist dies nicht der Fall, den Wert der **COleCurrency** -Objekts auf 0 (null) und ihren Status auf ungültig festgelegt wird.  
  
- `COleCurrency(`nUnits`, `nFractionalUnits') erstellt eine **COleCurrency** Objekt aus den angegebenen numerischen Komponenten. Wenn der Absolute Wert des Bruchteils größer als 10.000 ist, wird die entsprechende Anpassung an den Einheiten hergestellt. Beachten Sie, dass die Einheiten und Teil mit Bruchzahlen enthält durch lange Werte mit Vorzeichen angegeben werden.  
  
 Weitere Informationen finden Sie unter der [Währung](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e) und [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) Einträge in das Windows SDK.  
  
### <a name="example"></a>Beispiel  
 Die folgenden Beispiele zeigen die Auswirkungen der Konstruktoren NULL-Parameter und zwei Parameter:  
  
 [!code-cpp[NVC_MFCOleContainer#10](../../mfc/codesnippet/cpp/colecurrency-class_1.cpp)]  
  
##  <a name="format"></a>COleCurrency::Format  
 Rufen Sie diese Memberfunktion, um eine formatierte Darstellung des den Currency-Wert.  
  
```  
CString Format(DWORD  dwFlags = 0, LCID  lcid = LANG_USER_DEFAULT) const; 
```  
  
### <a name="parameters"></a>Parameter  
 `dwFlags`  
 Gibt Flags für gebietsschemaeinstellungen an. Nur die folgenden Flag ist in Währung relevant:  
  
- **LOCALE_NOUSEROVERRIDE** die Systemeinstellungen für Standard-Gebietsschema, anstelle von benutzerdefinierten Einstellungen verwenden.  
  
 `lcid`  
 Gibt die Gebietsschema-ID für die Konvertierung an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` , das die formatierte Währung-Wert enthält.  
  
### <a name="remarks"></a>Hinweise  
 Formatiert den Wert unter Verwendung der lokalen Sprache-Spezifikationen (Gebietsschema-IDs). Ein Währungssymbol ist nicht im zurückgegebenen Wert enthalten. Wenn der Status dieser **COleCurrency** Objekt null ist, wird eine leere Zeichenfolge zurückgegeben. Wenn der Status ungültig ist, ist die Rückgabezeichenfolge eine Zeichenfolgenressource angegeben **IDS_INVALID_CURRENCY**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer#11](../../mfc/codesnippet/cpp/colecurrency-class_2.cpp)]  
  
##  <a name="getstatus"></a>COleCurrency::GetStatus  
 Rufen Sie diese Memberfunktion zum Abrufen des Status (Gültigkeit) einen bestimmten **COleCurrency** Objekt.  
  
```  
CurrencyStatus GetStatus() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Status dieses **COleCurrency** Wert.  
  
### <a name="remarks"></a>Hinweise  
 Der Rückgabewert wird definiert, indem die `CurrencyStatus` Enumerationstyps, der im definiert ist die **COleCurrency** Klasse.  
  
```  
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };  
```  
  
 Eine kurze Beschreibung von diesen Statuswerten verwenden finden Sie in der folgenden Liste:  
  
- **COleCurrency::valid** gibt an, dass diese **COleCurrency** -Objekt gültig ist.  
  
- **COleCurrency::invalid** gibt an, dass diese **COleCurrency** Objekt ist ungültig; d. h. der Wert ist möglicherweise falsch.  
  
- **COleCurrency::null** gibt an, dass diese **COleCurrency** Objekt null ist, d. h., dass für dieses Objekt kein Wert angegeben wurde. (Dies ist "null", in dem Sinne Datenbank mit"kein Wert" im Gegensatz zu C++ **NULL**.)  
  
 Der Status einer **COleCurrency** Objekt ist ungültig in den folgenden Fällen:  
  
-   Wenn der Wert, von gesetzt wird einem **VARIANT** oder `COleVariant` Wert, der nicht auf einen Währungswert konvertiert werden konnten.  
  
-   Wenn dieses Objekt einen Überlauf oder Unterlauf während eines arithmetischen Zuweisungsvorgangs, z. B. aufgetreten `+=` oder  **\* =** .  
  
-   Wenn dieses Objekt ein ungültiger Wert zugewiesen wurde.  
  
-   Wenn der Status dieses Objekts explizit festgelegt wurde, um ungültige mit [SetStatus](#setstatus).  
  
 Weitere Informationen zu Vorgängen, die den Status ungültig, finden Sie unter den folgenden Memberfunktionen festgelegt werden können:  
  
- [COleCurrency](#colecurrency)  
  
- [Operator =](#operator_eq)  
  
- [Operator + -](#operator_plus_minus)  
  
- [Operator += und -=](#operator_plus_minus_eq)  
  
- [Operator * /](#operator_star)  
  
- [Operator * = und / =](#operator_star_div_eq)  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer#12](../../mfc/codesnippet/cpp/colecurrency-class_3.cpp)]  
  
##  <a name="m_cur"></a>COleCurrency::m_cur  
 Die zugrunde liegende [Währung](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e) Struktur für dieses **COleCurrency** Objekt.  
  
### <a name="remarks"></a>Hinweise  
  
> [!CAUTION]
>  Ändern des Werts in der **Währung** zugegriffen wird, die von dieser Funktion zurückgegebenen Zeiger Struktur ändert sich den Wert dieses **COleCurrency** Objekt. Ändert nicht den Status dieses **COleCurrency** Objekt.  
  
 Weitere Informationen finden Sie unter der [Währung](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e) Eintrag im Windows SDK.  
  
##  <a name="m_status"></a>COleCurrency::m_status  
 Der Typ dieses Datenelements ist den enumerierten Typ `CurrencyStatus`, die definiert ist, in der **COleCurrency** Klasse.  
  
```  
enum CurrencyStatus{  
    valid = 0,  
    invalid = 1,  
    null = 2,  
};  
```  
  
### <a name="remarks"></a>Hinweise  
 Eine kurze Beschreibung von diesen Statuswerten verwenden finden Sie in der folgenden Liste:  
  
- **COleCurrency::valid** gibt an, dass diese **COleCurrency** -Objekt gültig ist.  
  
- **COleCurrency::invalid** gibt an, dass diese **COleCurrency** Objekt ist ungültig; d. h. der Wert ist möglicherweise falsch.  
  
- **COleCurrency::null** gibt an, dass diese **COleCurrency** Objekt null ist, d. h., dass für dieses Objekt kein Wert angegeben wurde. (Dies ist "null", in dem Sinne Datenbank mit"kein Wert" im Gegensatz zu C++ **NULL**.)  
  
 Der Status einer **COleCurrency** Objekt ist ungültig in den folgenden Fällen:  
  
-   Wenn der Wert, von gesetzt wird einem **VARIANT** oder `COleVariant` Wert, der nicht auf einen Währungswert konvertiert werden konnten.  
  
-   Wenn dieses Objekt einen Überlauf oder Unterlauf während eines arithmetischen Zuweisungsvorgangs, z. B. aufgetreten `+=` oder  **\* =** .  
  
-   Wenn dieses Objekt ein ungültiger Wert zugewiesen wurde.  
  
-   Wenn der Status dieses Objekts explizit festgelegt wurde, um ungültige mit [SetStatus](#setstatus).  
  
 Weitere Informationen zu Vorgängen, die den Status ungültig, finden Sie unter den folgenden Memberfunktionen festgelegt werden können:  
  
- [COleCurrency](#colecurrency)  
  
- [Operator =](#operator_eq)  
  
- [Operator +, -](#operator_plus_minus)  
  
- [Operator +=, =](#operator_plus_minus_eq)  
  
- [Operator * /](#operator_star)  
  
- [Operator * =, / =](#operator_star_div_eq)  
  
    > [!CAUTION]
    >  Dieses Datenelement ist für Situationen, Erweiterte Programmierung. Sie sollten die Inline-Memberfunktionen verwenden [GetStatus](#getstatus) und [SetStatus](#setstatus). Finden Sie unter `SetStatus` weiteren Warnhinweise bezüglich dieses Datenelement explizit festlegen.  
  
##  <a name="operator_eq"></a>COleCurrency::operator =  
 Diese überladenen Zuweisungsoperatoren Currency-Wert für die Quelle in diese kopieren **COleCurrency** Objekt.  
  
```  
const COleCurrency& operator=(CURRENCY cySrc);  
const COleCurrency& operator=(const COleCurrency& curSrc);  
  const COleCurrency& operator=(const VARIANT& varSrc);
```  
  
### <a name="remarks"></a>Hinweise  
 Eine kurze Beschreibung der einzelnen Operatoren lautet folgendermaßen:  
  
- **Operator = (** `cySrc` **)** der `CURRENCY` Wert wird kopiert, in der **COleCurrency** Objekt und dessen Status auf ungültig festgelegt ist.  
  
- **Operator = (** `curSrc` **)** den Wert und den Status des Operanden, eine vorhandene **COleCurrency** Objekt werden in diese kopiert **COleCurrency** -Objekt.  
  
- **Operator = (** *VarSrc* **)** Wenn die Konvertierung von der `VARIANT` Wert (oder [COleVariant](../../mfc/reference/colevariant-class.md) Objekt) in einer Währung ( `VT_CY`) ist erfolgreich ist, wird der konvertierte Wert in diese kopiert **COleCurrency** Objekt und dessen Status auf ungültig festgelegt ist. Wenn die Konvertierung nicht erfolgreich ist, ist der Wert von der **COleCurrency** -Objekts auf 0 und ihren Status auf ungültig festgelegt wird.  
  
 Weitere Informationen finden Sie unter der [Währung](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e) und [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) Einträge in das Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer#15](../../mfc/codesnippet/cpp/colecurrency-class_4.cpp)]  
  
##  <a name="operator_plus_minus"></a>COleCurrency::operator +, -  
 Diese Operatoren ermöglichen es Ihnen, Addition und Subtraktion zwei **COleCurrency** Werte zu und voneinander und so ändern Sie die Vorzeichen einer **COleCurrency** Wert.  
  
```  
COleCurrency operator+(const COleCurrency& cur) const;  
COleCurrency operator-(const COleCurrency& cur) const;  
COleCurrency operator-() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn einer der Operanden null ist, ist den Status des resultierenden **COleCurrency** Wert ist null.  
  
 Wenn die arithmetische Operation führt zu einem Überlauf, das resultierende **COleCurrency** Wert ist ungültig.  
  
 Wenn der Operand "Invalid" und das andere ist nicht null ist, ist den Status des resultierenden **COleCurrency** Wert ist ungültig.  
  
 Weitere Informationen auf den Status gültig, ungültig und null-Werten finden Sie unter der [M_status](#m_status) Membervariablen gespeichert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer#16](../../mfc/codesnippet/cpp/colecurrency-class_5.cpp)]  
  
##  <a name="operator_plus_minus_eq"></a>COleCurrency::operator +=, =  
 Ermöglichen es Ihnen, Addition und Subtraktion ein **COleCurrency** Wert verschiedene andere und aus dieser **COleCurrency** Objekt.  
  
```  
const COleCurrency& operator+=(const COleCurrency& cur);  
const COleCurrency& operator-=(const COleCurrency& cur);
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn einer der Operanden null ist, ist den Status dieser **COleCurrency** Objektsatz ist NULL.  
  
 Wenn die arithmetische Operation führt zu einem Überlauf, den Status dieses **COleCurrency** -Objekts festgelegt wird, ungültig.  
  
 Wenn einer der Operanden ist ungültig, und das andere ungleich null ist, der Status dieser **COleCurrency** -Objekts festgelegt wird, ungültig.  
  
 Weitere Informationen auf den Status gültig, ungültig und null-Werten finden Sie unter der [M_status](#m_status) Membervariablen gespeichert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer#17](../../mfc/codesnippet/cpp/colecurrency-class_6.cpp)]  
  
##  <a name="operator_star"></a>COleCurrency::operator * und /  
 Ermöglichen Sie skalieren eine **COleCurrency** Wert durch einen ganzzahligen Wert.  
  
```  
COleCurrency operator*(long nOperand) const;  
COleCurrency operator/(long nOperand) const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn die **COleCurrency** Operanden null ist, wird der Status des resultierenden **COleCurrency** Wert ist null.  
  
 Wenn die arithmetische Operation führt zu einem Überlauf oder ein Unterlauf stattfindet, den Status des resultierenden **COleCurrency** Wert ist ungültig.  
  
 Wenn die **COleCurrency** Operand ist ungültig, den Status des resultierenden **COleCurrency** Wert ist ungültig.  
  
 Weitere Informationen auf den Status gültig, ungültig und null-Werten finden Sie unter der [M_status](#m_status) Membervariablen gespeichert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer#18](../../mfc/codesnippet/cpp/colecurrency-class_7.cpp)]  
  
##  <a name="operator_star_div_eq"></a>COleCurrency::operator * =, / =  
 Ermöglichen es Ihnen, die Skalierung dieser **COleCurrency** Wert durch einen ganzzahligen Wert.  
  
```  
const COleCurrency& operator*=(long nOperand);  
const COleCurrency& operator/=(long nOperand);
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn die **COleCurrency** Operanden null ist, wird der Status dieser **COleCurrency** Objektsatz ist auf Null.  
  
 Wenn die arithmetische Operation führt zu einem Überlauf, den Status dieses **COleCurrency** -Objekts festgelegt wird, ungültig.  
  
 Wenn die **COleCurrency** Operand ist ungültig, der Status dieser **COleCurrency** -Objekts festgelegt wird, ungültig.  
  
 Weitere Informationen auf den Status gültig, ungültig und null-Werten finden Sie unter der [M_status](#m_status) Membervariablen gespeichert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer#19](../../mfc/codesnippet/cpp/colecurrency-class_8.cpp)]  
  
##  <a name="operator_stream"></a>COleCurrency::operator &lt; &lt;,&gt;&gt;  
 Unterstützt die Diagnose Dump-Sicherungen und in ein Archiv zu speichern.  
  
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
 Die Extrahierung (  **>>** ) Operator unterstützt das Laden aus einem Archiv.  
  
##  <a name="operator_currency"></a>COleCurrency::operator Währung  
 Gibt eine `CURRENCY` -Struktur, deren Wert wird aus dieser kopiert **COleCurrency** Objekt.  
  
```  
operator CURRENCY() const; 
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="parsecurrency"></a>COleCurrency::ParseCurrency  
 Rufen Sie diese Memberfunktion zum Analysieren einer Zeichenfolge um eine Currency-Wert zu lesen.  
  
```  
BOOL ParseCurrency(
    LPCTSTR lpszCurrency,  
    DWORD dwFlags = 0,  
    LCID lcid = LANG_USER_DEFAULT);
 
throw(CMemoryException*); 
throw(COleException*);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszCurrency*  
 Ein Zeiger auf die Null-terminierte Zeichenfolge, die analysiert werden soll.  
  
 `dwFlags`  
 Gibt Flags für die gebietsschemaeinstellungen, möglicherweise die folgenden Flags an:  
  
- **LOCALE_NOUSEROVERRIDE** die Systemeinstellungen für Standard-Gebietsschema, anstelle von benutzerdefinierten Einstellungen verwenden.  
  
 `lcid`  
 Gibt die Gebietsschema-ID für die Konvertierung an.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Zeichenfolge erfolgreich, auf einen Währungswert, andernfalls 0 konvertiert wurde.  
  
### <a name="remarks"></a>Hinweise  
 Spezifikationen der lokalen Sprache (Gebietsschema-IDs) verwendet für die Bedeutung von numerischen Zeichen in der Quellzeichenfolge.  
  
 Eine Erläuterung der Gebietsschema-ID-Werte, finden Sie unter [unterstützen mehrere Sprachen](http://msdn.microsoft.com/en-us/47dc5add-232c-4268-b977-43e12da81ede).  
  
 Wenn die Zeichenfolge erfolgreich konvertiert wurde, um eine Währung-Wert, den Wert dieses **COleCurrency** -Objekts auf diesen Wert und ihren Status auf ungültig festgelegt wird.  
  
 Wenn die Zeichenfolge nicht in einen Currency-Wert konvertiert werden konnte oder gab es einem numerischen Überlauf, den Status dieses **COleCurrency** Objekt ist ungültig.  
  
 Wenn die zeichenfolgenkonvertierung aufgrund aufgrund von Zuordnungsfehlern der Speicher fehlgeschlagen ist, wird diese Funktion löst einen [CMemoryException](../../mfc/reference/cmemoryexception-class.md). In anderen Fehlerzustand, diese Funktion löst einen [COleException](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer#13](../../mfc/codesnippet/cpp/colecurrency-class_9.cpp)]  
  
##  <a name="colecurrency_relational_operators"></a>COleCurrency-Operatoren (Relational)  
 Vergleichen von zwei Währungswerten und ungleich NULL, wenn die Bedingung "true" zurück; andernfalls 0.  
  
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
>  Der Rückgabewert der aufwendigere Sortiervorgänge (  **<** ,  **\< =** ,  **>** ,  **>=** ) ist nicht definiert, wenn der Status einer der Operanden null oder ungültig ist. Die Gleichheitsoperatoren ( `==`, `!=`) sollten Sie den Status der Operanden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer#20](../../mfc/codesnippet/cpp/colecurrency-class_10.cpp)]  
  
##  <a name="setcurrency"></a>COleCurrency::SetCurrency  
 Rufen Sie diese Memberfunktion zum Festlegen von Einheiten und Teil mit Bruchzahlen enthält dieses **COleCurrency** Objekt.  
  
```  
void SetCurrency(
    long nUnits,  
    long nFractionalUnits);
```  
  
### <a name="parameters"></a>Parameter  
 `nUnits`, `nFractionalUnits`  
 Geben Sie an den Einheiten und der Bruchteil (in 1/10 Tausende) den Wert in diese kopiert werden **COleCurrency** Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Absolute Wert des Bruchteils größer als 10.000 ist, erfolgt die entsprechende Anpassung an den Einheiten, wie in der dritten der in den folgenden Beispielen gezeigt.  
  
 Beachten Sie, dass die Einheiten und Teil mit Bruchzahlen enthält durch lange Werte mit Vorzeichen angegeben werden. Die vierte von den folgenden Beispielen wird gezeigt, was geschieht, wenn die Parameter unterschiedliche Vorzeichen haben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer#14](../../mfc/codesnippet/cpp/colecurrency-class_11.cpp)]  
  
##  <a name="setstatus"></a>COleCurrency::SetStatus  
 Rufen Sie diese Memberfunktion um den Status (Gültigkeit) dieses festzulegen **COleCurrency** Objekt.  
  
```  
void SetStatus(CurrencyStatus  status  );
```  
  
### <a name="parameters"></a>Parameter  
 *status*  
 Der neue Status für diesen **COleCurrency** Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die *Status* Parameterwert wird definiert, indem Sie die `CurrencyStatus` Aufzählungstyp innerhalb definiert ist die **COleCurrency** Klasse.  
  
```  
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };  
```  
  
 Eine kurze Beschreibung von diesen Statuswerten verwenden finden Sie in der folgenden Liste:  
  
- **COleCurrency::valid** gibt an, dass diese **COleCurrency** -Objekt gültig ist.  
  
- **COleCurrency::invalid** gibt an, dass diese **COleCurrency** Objekt ist ungültig; d. h. der Wert ist möglicherweise falsch.  
  
- **COleCurrency::null** gibt an, dass diese **COleCurrency** Objekt null ist, d. h., dass für dieses Objekt kein Wert angegeben wurde. (Dies ist "null", in dem Sinne Datenbank mit"kein Wert" im Gegensatz zu C++ **NULL**.)  
  
    > [!CAUTION]
    >  Diese Funktion ist für Situationen, Erweiterte Programmierung. Diese Funktion wird die Daten in dieses Objekt nicht verändert. Am häufigsten wird verwendet werden, zum Festlegen des Status null oder ungültig. Beachten Sie, dass der Zuweisungsoperator ( [Operator =](#operator_eq)) und [SetCurrency](#setcurrency) sollte den Status des Objekts basierend auf der Quelle Wert(e) festgelegt.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleVariant-Klasse](../../mfc/reference/colevariant-class.md)
