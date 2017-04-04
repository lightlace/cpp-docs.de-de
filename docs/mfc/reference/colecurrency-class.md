---
title: COleCurrency Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- fixed-point numbers
- numbers, fixed-point
- CURRENCY
- COleCurrency class
ms.assetid: 3a36e345-303f-46fb-a57c-858274378a8d
caps.latest.revision: 24
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 38dbd45818f53430db37bb5807c255494c4a9896
ms.lasthandoff: 02/24/2017

---
# <a name="colecurrency-class"></a>COleCurrency-Klasse
Kapselt den `CURRENCY` -Datentyp der OLE-Automatisierung.  
  
## <a name="syntax"></a>Syntax  
  
```  
class COleCurrency  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleCurrency::COleCurrency](#colecurrency)|Erstellt ein `COleCurrency`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleCurrency::Format](#format)|Generiert eine formatierte Zeichenfolge-Darstellung des ein `COleCurrency` Objekt.|  
|[COleCurrency::GetStatus](#getstatus)|Ruft ab, der den Status (Gültigkeit) `COleCurrency` Objekt.|  
|[COleCurrency::ParseCurrency](#parsecurrency)|Liest eine **Währung** Wert aus einer Zeichenfolge und legt den Wert des `COleCurrency`.|  
|[COleCurrency::SetCurrency](#setcurrency)|Legt den Wert dieses `COleCurrency` Objekt.|  
|[COleCurrency::SetStatus](#setstatus)|Legt den Status (Gültigkeit) für diesen `COleCurrency` Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Operator =](#operator_eq)|Kopiert einen `COleCurrency` Wert.|  
|[Operator +, -](#operator_plus_minus)|Fügt subtrahiert und ändert sich der `COleCurrency` Werte.|  
|[Operator +=, =](#operator_plus_minus_eq)|Fügt und subtrahiert einen `COleCurrency` Wert aus diesem `COleCurrency` Objekt.|  
|[Operator * /](#operator_star)|Ändert die Größe einer `COleCurrency` Wert durch einen ganzzahligen Wert.|  
|[Operator * =, / =](#operator_star_div_eq)|Skaliert das `COleCurrency` Wert durch einen ganzzahligen Wert.|  
|[Operator](#operator_stream)|Ausgaben einer `COleCurrency` Wert `CArchive` oder `CDumpContext`.|  
|[Operator >>](#operator_stream)|Eingaben ein `COleCurrency` -Objekt aus `CArchive`.|  
|[Operator Währung](#operator_currency)|Konvertiert eine `COleCurrency` Wert in einem **Währung**.|  
|[Operator ==,<,></,><=,></=,>](#colecurrency_relational_operators)|Vergleicht zwei `COleCurrency` Werte.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleCurrency::m_cur](#m_cur)|Enthält die zugrunde liegende **Währung** für dieses `COleCurrency` Objekt.|  
|[COleCurrency::m_status](#m_status)|Enthält den Status dieser `COleCurrency` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 **COleCurrency** verfügt nicht über eine Basisklasse.  
  
 **Währung** wird als eine 8-Byte, zweier-Komplement ganzzahligen Wert multipliziert mit 10.000 implementiert. Dies ermöglicht eine Festkommazahl mit 15 Stellen links vom Dezimaltrennzeichen und 4 Ziffern rechts. Die **Währung** Datentyp ist äußerst nützlich für Berechnungen mit Geld oder für alle Berechnungsmethode, wenn Genauigkeit wichtig. Es gibt die möglichen Typen für die `VARIANT` -Datentyp der OLE-Automatisierung.  
  
 **COleCurrency** implementiert außerdem einige grundlegenden arithmetischen Operationen für diesen Festkomma. Die unterstützten Vorgänge wurden ausgewählt, um die Rundungsfehler steuern, welche die Festkommanotation Berechnungen auftreten.  
  
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
 Ein **Währung** Wert in die neue kopiert werden **COleCurrency** Objekt.  
  
 `curSrc`  
 Eine vorhandene **COleCurrency** -Objekt, in das neue kopiert werden **COleCurrency** Objekt.  
  
 *varSrc*  
 Eine vorhandene **VARIANT** Datenstruktur (möglicherweise eine `COleVariant` Objekt) in einen Währungswert konvertiert werden ( `VT_CY`) und kopiert Sie in die neue **COleCurrency** Objekt.  
  
 `nUnits`, `nFractionalUnits`  
 Geben Sie den Einheiten und Bruchteil (in 1/10 Tausende) den Wert in die neue kopiert werden **COleCurrency** Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Alle diese Konstruktoren Erstellen neuer **COleCurrency** Objekte, die mit dem angegebenen Wert initialisiert. Eine kurze Beschreibung jeder dieser Konstruktoren folgt. Sofern nicht anders angegeben, den Status der neuen **COleCurrency** Element zu gültigen festgelegt ist.  
  
- COleCurrency() erstellt einen **COleCurrency** Objekt mit 0 (null) initialisiert.  
  
- COleCurrency (`cySrc`) erstellt eine **COleCurrency** -Objekt aus einer [Währung](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e) Wert.  
  
- COleCurrency (`curSrc`) erstellt eine **COleCurrency** -Objekt aus einem vorhandenen **COleCurrency** Objekt. Das neue Objekt hat den gleichen Status wie das Quellobjekt.  
  
- COleCurrency (`varSrc`) erstellt eine **COleCurrency** Objekt. Versucht, Konvertieren einer [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) Struktur oder `COleVariant` Objekt, das eine Währung ( `VT_CY`) Wert. Wenn die Konvertierung erfolgreich ist, wird der konvertierte Wert in die neue kopiert **COleCurrency** Objekt. Ist dies nicht der Fall, den Wert der **COleCurrency** -Objekts auf&0; (null) und ihren Status auf ungültige festgelegt wird.  
  
- `COleCurrency(`nUnits`, `nFractionalUnits') erstellt eine **COleCurrency** Objekt aus den angegebenen numerischen Komponenten. Wenn der Absolute Wert des Bruchteils größer als 10.000 ist, wird die entsprechende Anpassung an den Einheiten vorgenommen. Beachten Sie, dass die Einheiten und Bruchteil von signierten long-Werte angegeben werden.  
  
 Weitere Informationen finden Sie unter der [Währung](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e) und [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) Einträge in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Die folgenden Beispiele zeigen die Auswirkungen der Konstruktoren NULL-Parameter und zwei Parameter:  
  
 [!code-cpp[NVC_MFCOleContainer&#10;](../../mfc/codesnippet/cpp/colecurrency-class_1.cpp)]  
  
##  <a name="format"></a>COleCurrency::Format  
 Rufen Sie diese Memberfunktion, um eine formatierte Darstellung des Werts Währung zu erstellen.  
  
```  
CString Format(DWORD  dwFlags = 0, LCID  lcid = LANG_USER_DEFAULT) const; 
```  
  
### <a name="parameters"></a>Parameter  
 `dwFlags`  
 Gibt Flags für das Gebietsschema an. Das folgende Flag ist auf Currency relevant:  
  
- **LOCALE_NOUSEROVERRIDE** Gebietsschema Standardeinstellungen des Systems statt mit dem benutzerdefinierten Einstellungen verwenden.  
  
 `lcid`  
 Gibt die Gebietsschema-ID für die Konvertierung an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` , das die formatierte Währung-Wert enthält.  
  
### <a name="remarks"></a>Hinweise  
 Es formatiert den Wert mit den Spezifikationen der Landessprache (Gebietsschema-IDs). Ein Währungssymbol ist nicht in dem zurückgegebenen Wert enthalten. Wenn der Status dieser **COleCurrency** Objekt ist null, der Rückgabewert ist eine leere Zeichenfolge. Wenn der Status ungültig ist, wird die zurückgegebene Zeichenfolge durch die Zeichenfolgenressource angegeben **IDS_INVALID_CURRENCY**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer&#11;](../../mfc/codesnippet/cpp/colecurrency-class_2.cpp)]  
  
##  <a name="getstatus"></a>COleCurrency::GetStatus  
 Rufen Sie diese Memberfunktion zum Abrufen des Status (Gültigkeit) einer bestimmten **COleCurrency** Objekt.  
  
```  
CurrencyStatus GetStatus() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Status dieses **COleCurrency** Wert.  
  
### <a name="remarks"></a>Hinweise  
 Der Rückgabewert wird definiert, indem die `CurrencyStatus` Enumerationstyps, der definiert ist die **COleCurrency** Klasse.  
  
```  
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };  
```  
  
 Eine kurze Beschreibung dieser Status-Werte finden Sie in der folgenden Liste:  
  
- **COleCurrency::valid** gibt an, dass diese **COleCurrency** -Objekt gültig ist.  
  
- **COleCurrency::invalid** gibt an, dass diese **COleCurrency** Objekt ist ungültig; d. h. möglicherweise der Wert falsch.  
  
- **COleCurrency::null** gibt an, dass diese **COleCurrency** Objekt null ist, d. h., dass für dieses Objekt kein Wert angegeben wurde. (Dies ist "null", in dem Sinne Datenbank mit"kein Wert" im Gegensatz zu C++ **NULL**.)  
  
 Der Status einer **COleCurrency** Objekt ist ungültig, in den folgenden Fällen:  
  
-   Wenn der Wert, von gesetzt wird einem **VARIANT** oder `COleVariant` -Wert, der nicht in einen Währungswert konvertiert werden konnte.  
  
-   Wenn dieses Objekt einen Überlauf oder Unterlauf während eines Zuweisungsvorgangs arithmetische z. B. aufgetreten `+=` oder ** \* = **.  
  
-   Wenn ein ungültiger Wert für dieses Objekt zugewiesen wurde.  
  
-   Wenn der Status des Objekts explizit festgelegt wurde, um ungültige mit [SetStatus](#setstatus).  
  
 Weitere Informationen zu Vorgängen, die den Status ungültig, finden Sie unter den folgenden Memberfunktionen festgelegt werden können:  
  
- [COleCurrency](#colecurrency)  
  
- [Operator =](#operator_eq)  
  
- [Operator + -](#operator_plus_minus)  
  
- [Operator += und -=](#operator_plus_minus_eq)  
  
- [Operator * /](#operator_star)  
  
- [Operator * = und / =](#operator_star_div_eq)  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer&#12;](../../mfc/codesnippet/cpp/colecurrency-class_3.cpp)]  
  
##  <a name="m_cur"></a>COleCurrency::m_cur  
 Die zugrunde liegende [Währung](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e) Struktur für dieses **COleCurrency** Objekt.  
  
### <a name="remarks"></a>Hinweise  
  
> [!CAUTION]
>  Ändern den Wert in der **Währung** Zugriff auf der Zeiger verweist, die von dieser Funktion zurückgegebenen Struktur ändert sich den Wert dieses **COleCurrency** Objekt. Er ändert nicht den Status dieses **COleCurrency** Objekt.  
  
 Weitere Informationen finden Sie unter der [Währung](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e) Eintrag in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="m_status"></a>COleCurrency::m_status  
 Der Typ der Datenmember ist der Enumerationstyp `CurrencyStatus`, definiert in der **COleCurrency** Klasse.  
  
```  
enum CurrencyStatus{  
    valid = 0,  
    invalid = 1,  
    null = 2,  
};  
```  
  
### <a name="remarks"></a>Hinweise  
 Eine kurze Beschreibung dieser Status-Werte finden Sie in der folgenden Liste:  
  
- **COleCurrency::valid** gibt an, dass diese **COleCurrency** -Objekt gültig ist.  
  
- **COleCurrency::invalid** gibt an, dass diese **COleCurrency** Objekt ist ungültig; d. h. möglicherweise der Wert falsch.  
  
- **COleCurrency::null** gibt an, dass diese **COleCurrency** Objekt null ist, d. h., dass für dieses Objekt kein Wert angegeben wurde. (Dies ist "null", in dem Sinne Datenbank mit"kein Wert" im Gegensatz zu C++ **NULL**.)  
  
 Der Status einer **COleCurrency** Objekt ist ungültig, in den folgenden Fällen:  
  
-   Wenn der Wert, von gesetzt wird einem **VARIANT** oder `COleVariant` -Wert, der nicht in einen Währungswert konvertiert werden konnte.  
  
-   Wenn dieses Objekt einen Überlauf oder Unterlauf während eines Zuweisungsvorgangs arithmetische z. B. aufgetreten `+=` oder ** \* = **.  
  
-   Wenn ein ungültiger Wert für dieses Objekt zugewiesen wurde.  
  
-   Wenn der Status des Objekts explizit festgelegt wurde, um ungültige mit [SetStatus](#setstatus).  
  
 Weitere Informationen zu Vorgängen, die den Status ungültig, finden Sie unter den folgenden Memberfunktionen festgelegt werden können:  
  
- [COleCurrency](#colecurrency)  
  
- [Operator =](#operator_eq)  
  
- [Operator +, -](#operator_plus_minus)  
  
- [Operator +=, =](#operator_plus_minus_eq)  
  
- [Operator * /](#operator_star)  
  
- [Operator * =, / =](#operator_star_div_eq)  
  
    > [!CAUTION]
    >  Dieses Datenelement ist für die Erweiterte Programmierung Situationen. Verwenden Sie die Inline-Memberfunktionen [GetStatus](#getstatus) und [SetStatus](#setstatus). Finden Sie unter `SetStatus` Weitere Warnhinweise in Bezug auf dieses Datenelement explizit festlegen.  
  
##  <a name="operator_eq"></a>COleCurrency::operator =  
 Diese überladenen Zuweisungsoperatoren kopieren Currency-Wert für die Quelle in dieser **COleCurrency** Objekt.  
  
```  
const COleCurrency& operator=(CURRENCY cySrc);  
const COleCurrency& operator=(const COleCurrency& curSrc);  
  const COleCurrency& operator=(const VARIANT& varSrc);
```  
  
### <a name="remarks"></a>Hinweise  
 Eine kurze Beschreibung der einzelnen Operatoren folgt:  
  
- **Operator = (** `cySrc` **)** der `CURRENCY` Wert wird kopiert, in der **COleCurrency** Objekt und seinen Status zu gültigen festgelegt ist.  
  
- **Operator = (** `curSrc` **)** den Wert und den Status des Operanden ein vorhandenes **COleCurrency** in dieses Objekt kopiert **COleCurrency** Objekt.  
  
- **Operator = (** *VarSrc* **)** Wenn die Konvertierung von der `VARIANT` Wert (oder [COleVariant](../../mfc/reference/colevariant-class.md) Objekt) zu einer Währung ( `VT_CY`) ist erfolgreich, wird der konvertierte Wert in diese kopiert **COleCurrency** Objekt und seinen Status zu gültigen festgelegt ist. Wenn die Konvertierung nicht erfolgreich ist, ist der Wert des der **COleCurrency** Objekt ist auf 0 festgelegt und dessen Status ungültig.  
  
 Weitere Informationen finden Sie unter der [Währung](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e) und [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) Einträge in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer&#15;](../../mfc/codesnippet/cpp/colecurrency-class_4.cpp)]  
  
##  <a name="operator_plus_minus"></a>COleCurrency::operator +, -  
 Diese Operatoren können Sie addieren und subtrahieren zwei **COleCurrency** Werte an und ändern Sie die Vorzeichen des ein **COleCurrency** Wert.  
  
```  
COleCurrency operator+(const COleCurrency& cur) const;  
COleCurrency operator-(const COleCurrency& cur) const;  
COleCurrency operator-() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn einer der Operanden null ist, ist den Status der resultierenden **COleCurrency** Wert ist null.  
  
 Wenn die arithmetische Operation läuft, das resultierende **COleCurrency** Wert ist ungültig.  
  
 Wenn der Operand ungültig und der andere ist nicht null ist, ist den Status der resultierenden **COleCurrency** Wert ist ungültig.  
  
 Weitere Informationen zu den gültig, ungültig und null-Status-Werte, finden Sie unter der [M_status](#m_status) Membervariablen gespeichert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer Nr.&16;](../../mfc/codesnippet/cpp/colecurrency-class_5.cpp)]  
  
##  <a name="operator_plus_minus_eq"></a>COleCurrency::operator +=, =  
 Ermöglichen es Ihnen, Addition und Subtraktion ein **COleCurrency** Wert aus diesem **COleCurrency** Objekt.  
  
```  
const COleCurrency& operator+=(const COleCurrency& cur);  
const COleCurrency& operator-=(const COleCurrency& cur);
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn einer der Operanden null ist, ist den Status dieser **COleCurrency** wird auf Null.  
  
 Wenn die arithmetische Operation läuft, den Status dieses **COleCurrency** -Objekts festgelegt wird, ungültig.  
  
 Wenn die Operanden ist ungültig, und der andere nicht null ist Operand, den Status dieses **COleCurrency** -Objekts festgelegt wird, ungültig.  
  
 Weitere Informationen zu den gültig, ungültig und null-Status-Werte, finden Sie unter der [M_status](#m_status) Membervariablen gespeichert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer&17;](../../mfc/codesnippet/cpp/colecurrency-class_6.cpp)]  
  
##  <a name="operator_star"></a>COleCurrency::operator * und /  
 Ermöglichen Sie skalieren eine **COleCurrency** Wert durch einen ganzzahligen Wert.  
  
```  
COleCurrency operator*(long nOperand) const;  
COleCurrency operator/(long nOperand) const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn die **COleCurrency** der Operanden null ist, ist der Status der resultierenden **COleCurrency** Wert ist null.  
  
 Wenn die arithmetische Operation führt zu einem Überlauf oder ein Unterlauf stattfindet, den Status der resultierenden **COleCurrency** Wert ist ungültig.  
  
 Wenn die **COleCurrency** Operand ungültig ist, wird der Status der resultierenden **COleCurrency** Wert ist ungültig.  
  
 Weitere Informationen zu den gültig, ungültig und null-Status-Werte, finden Sie unter der [M_status](#m_status) Membervariablen gespeichert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer&18;](../../mfc/codesnippet/cpp/colecurrency-class_7.cpp)]  
  
##  <a name="operator_star_div_eq"></a>COleCurrency::operator * =, / =  
 Ermöglichen es Ihnen, die Skalierung dieser **COleCurrency** Wert durch einen ganzzahligen Wert.  
  
```  
const COleCurrency& operator*=(long nOperand);  
const COleCurrency& operator/=(long nOperand);
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der **COleCurrency** der Operanden null ist, ist der Status dieser **COleCurrency** wird auf Null.  
  
 Wenn die arithmetische Operation läuft, den Status dieses **COleCurrency** -Objekts festgelegt wird, ungültig.  
  
 Wenn die **COleCurrency** Operand ist ungültig, der den Status **COleCurrency** -Objekts festgelegt wird, ungültig.  
  
 Weitere Informationen zu den gültig, ungültig und null-Status-Werte, finden Sie unter der [M_status](#m_status) Membervariablen gespeichert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer Nr.&19;](../../mfc/codesnippet/cpp/colecurrency-class_8.cpp)]  
  
##  <a name="operator_stream"></a>COleCurrency::operator &lt; &lt;,&gt;&gt;  
 Sichern von Diagnose und in ein Archiv speichern unterstützt.  
  
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
 Die Extraktion ( ** >> **) Operator unterstützt das Laden aus einem Archiv.  
  
##  <a name="operator_currency"></a>COleCurrency::operator Währung  
 Gibt eine `CURRENCY` , deren Wert aus dieser kopiert Struktur **COleCurrency** Objekt.  
  
```  
operator CURRENCY() const; 
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="parsecurrency"></a>COleCurrency::ParseCurrency  
 Rufen Sie diese Memberfunktion zum Analysieren einer Zeichenfolge um einen Währungswert zu lesen.  
  
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
 Gibt Flags für das Gebietsschema, möglicherweise das folgende Flag an:  
  
- **LOCALE_NOUSEROVERRIDE** Gebietsschema Standardeinstellungen des Systems statt mit dem benutzerdefinierten Einstellungen verwenden.  
  
 `lcid`  
 Gibt die Gebietsschema-ID für die Konvertierung an.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Zeichenfolge in einen Währungswert, andernfalls 0 erfolgreich konvertiert wurde.  
  
### <a name="remarks"></a>Hinweise  
 Spezifikationen der Landessprache (Gebietsschema-IDs) verwendet für die Bedeutung von nicht-numerische Zeichen in der Quellzeichenfolge.  
  
 Eine Erläuterung der Gebietsschema-ID-Werten, finden Sie unter [mehrere Sprachen unterstützen](http://msdn.microsoft.com/en-us/47dc5add-232c-4268-b977-43e12da81ede).  
  
 Wenn die Zeichenfolge erfolgreich in einer Währung konvertiert wurde Wert ist, wird den Wert dieses **COleCurrency** -Objekts auf dieses Werts und ihren Status auf gültig festgelegt wird.  
  
 Wenn die Zeichenfolge nicht in einen Währungswert konvertiert werden kann oder ob es einem numerischen Überlauf, den Status dieses **COleCurrency** Objekt ist ungültig.  
  
 Wenn aufgrund von Arbeitsspeicher-Reservierungsfehler die Konvertierung fehlgeschlagen ist, löst diese Funktion eine [CMemoryException](../../mfc/reference/cmemoryexception-class.md). In jedem anderen Fehlerzustand, löst diese Funktion eine [COleException verfügt](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer&#13;](../../mfc/codesnippet/cpp/colecurrency-class_9.cpp)]  
  
##  <a name="colecurrency_relational_operators"></a>COleCurrency relationale Operatoren  
 Vergleichen von zwei Währungswerten, und geben einen Wert ungleich NULL, wenn die Bedingung true ist; andernfalls 0.  
  
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
>  Der Rückgabewert der Sortierung Vorgänge ( ** < **, ** \< = **, ** > **, ** >= **) ist nicht definiert, wenn der Status einer der Operanden null oder ungültig ist. Die Gleichheitsoperatoren ( `==`, `!=`) sollten Sie den Status der Operanden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer&20;](../../mfc/codesnippet/cpp/colecurrency-class_10.cpp)]  
  
##  <a name="setcurrency"></a>COleCurrency::SetCurrency  
 Rufen Sie diese Memberfunktion zum Festlegen von Einheiten und Bruchteil dieser **COleCurrency** Objekt.  
  
```  
void SetCurrency(
    long nUnits,  
    long nFractionalUnits);
```  
  
### <a name="parameters"></a>Parameter  
 `nUnits`, `nFractionalUnits`  
 Geben Sie den Einheiten und Bruchteil (in 1/10 Tausende) den Wert in diese kopiert werden **COleCurrency** Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Absolute Wert des Bruchteils größer als 10.000 ist, erfolgt die entsprechende Anpassung an den Einheiten, wie im dritten der folgenden Beispiele gezeigt.  
  
 Beachten Sie, dass die Einheiten und Bruchteil von signierten long-Werte angegeben werden. Die vierte von den folgenden Beispielen wird gezeigt, was geschieht, wenn die Parameter unterschiedliche Vorzeichen haben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCOleContainer&14;](../../mfc/codesnippet/cpp/colecurrency-class_11.cpp)]  
  
##  <a name="setstatus"></a>COleCurrency::SetStatus  
 Rufen Sie diese Memberfunktion zum Festlegen des Status (Gültigkeit) **COleCurrency** Objekt.  
  
```  
void SetStatus(CurrencyStatus  status  );
```  
  
### <a name="parameters"></a>Parameter  
 *status*  
 Der neue Status für diesen **COleCurrency** Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die *Status* Parameterwert wird definiert, indem die `CurrencyStatus` -Enumerationstyp definiert ist die **COleCurrency** Klasse.  
  
```  
enum CurrencyStatus {
    valid = 0,
    invalid = 1,
    null = 2
    };  
```  
  
 Eine kurze Beschreibung dieser Status-Werte finden Sie in der folgenden Liste:  
  
- **COleCurrency::valid** gibt an, dass diese **COleCurrency** -Objekt gültig ist.  
  
- **COleCurrency::invalid** gibt an, dass diese **COleCurrency** Objekt ist ungültig; d. h. möglicherweise der Wert falsch.  
  
- **COleCurrency::null** gibt an, dass diese **COleCurrency** Objekt null ist, d. h., dass für dieses Objekt kein Wert angegeben wurde. (Dies ist "null", in dem Sinne Datenbank mit"kein Wert" im Gegensatz zu C++ **NULL**.)  
  
    > [!CAUTION]
    >  Diese Funktion ist für die Erweiterte Programmierung Situationen. Diese Funktion werden die Daten in diesem Objekt nicht geändert. Am häufigsten wird verwendet werden, um den Status null oder ungültig. Beachten Sie, dass der Zuweisungsoperator ( [Operator =](#operator_eq)) und [SetCurrency](#setcurrency) den Status des Objekts basierend auf der Quelle Werte festgelegt.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleVariant-Klasse](../../mfc/reference/colevariant-class.md)

