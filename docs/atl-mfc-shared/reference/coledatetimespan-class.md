---
title: COleDateTimeSpan Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.COleDateTimeSpan
- COleDateTimeSpan
- ATL::COleDateTimeSpan
dev_langs:
- C++
helpviewer_keywords:
- timespan
- time span
- shared classes, COleDateTimeSpan
- Date data type, MFC encapsulation of
- COleDateTimeSpan class
ms.assetid: 7441526d-a30a-4019-8fb3-3fee6f897cbe
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 4091ca2c766d56d8398119413778af0a0405b8ab
ms.lasthandoff: 02/24/2017

---
# <a name="coledatetimespan-class"></a>COleDateTimeSpan-Klasse
Einen relativen Zeitraum eine Zeitspanne darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```
class COleDateTimeSpan
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDateTimeSpan::COleDateTimeSpan](#coledatetimespan)|Erstellt ein `COleDateTimeSpan`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDateTimeSpan::Format](#format)|Generiert eine formatierte Zeichenfolge-Darstellung des ein `COleDateTimeSpan` Objekt.|  
|[COleDateTimeSpan::GetDays](#getdays)|Gibt den Tagesteil des Span-Tags dies `COleDateTimeSpan` -Objekt darstellt.|  
|[COleDateTimeSpan::GetHours](#gethours)|Gibt dem Stundenteil des Span-Tags dies `COleDateTimeSpan` -Objekt darstellt.|  
|[COleDateTimeSpan::GetMinutes](#getminutes)|Gibt den Minutenteil des Span-Tags dies `COleDateTimeSpan` -Objekt darstellt.|  
|[COleDateTimeSpan::GetSeconds](#getseconds)|Dem zweiten Teil des Span-Tags zurückgegeben `COleDateTimeSpan` -Objekt darstellt.|  
|[COleDateTimeSpan::GetStatus](#getstatus)|Ruft ab, der den Status (Gültigkeit) `COleDateTimeSpan` Objekt.|  
|[COleDateTimeSpan::GetTotalDays](#gettotaldays)|Gibt die Anzahl der Tage dies `COleDateTimeSpan` -Objekt darstellt.|  
|[COleDateTimeSpan::GetTotalHours](#gettotalhours)|Gibt die Anzahl der Stunden dies `COleDateTimeSpan` -Objekt darstellt.|  
|[COleDateTimeSpan::GetTotalMinutes](#gettotalminutes)|Gibt die Anzahl der Minuten dies `COleDateTimeSpan` -Objekt darstellt.|  
|[COleDateTimeSpan::GetTotalSeconds](#gettotalseconds)|Gibt die Anzahl der Sekunden dies `COleDateTimeSpan` -Objekt darstellt.|  
|[COleDateTimeSpan::SetDateTimeSpan](#setdatetimespan)|Legt den Wert dieses `COleDateTimeSpan` Objekt.|  
|[COleDateTimeSpan::SetStatus](#setstatus)|Setzt den Status (Gültigkeit) dieses `COleDateTimeSpan` Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|||  
|-|-|  
|[Operator +, -](#operator_add_-)|Hinzufügen, subtrahieren, und ändern Sie die Zeichen für `COleDateTimeSpan` Werte.|  
|[Operator +=, =](#operator_add_eq_-_eq)|Addition und Subtraktion ein `COleDateTimeSpan` Wert aus diesem `COleDateTimeSpan` Wert.|  
|[Operator =](#operator_eq)|Kopiert einen `COleDateTimeSpan` Wert.|  
|[Operator ==,<,></,><>](#coledatetimespan_relational_operators)|Vergleicht zwei `COleDateTimeSpan` Werte.|  
|[Operator double](#operator_double)|Konvertiert dieses `COleDateTimeSpan` -Wert in einem **doppelte**.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDateTimeSpan::m_span](#m_span)|Enthält die zugrunde liegende **doppelte** für dieses `COleDateTimeSpan` Objekt.|  
|[COleDateTimeSpan::m_status](#m_status)|Enthält den Status dieser `COleDateTimeSpan` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `COleDateTimeSpan`eine Basisklasse keinen.  
  
 Ein `COleDateTimeSpan` verfolgt Zeit in Tagen.  
  
 `COleDateTimeSpan`wird verwendet, mit dessen Begleitklasse [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md). `COleDateTime`Kapselt die **Datum** -Datentyp der OLE-Automatisierung. `COleDateTime`Stellt die absoluten Werte dar. Alle `COleDateTime` schließen Berechnungen `COleDateTimeSpan` Werte. Die Beziehung zwischen diesen Klassen entspricht, die zwischen [CTime](../../atl-mfc-shared/reference/ctime-class.md) und [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md).  
  
 Weitere Informationen zu den `COleDateTime` und `COleDateTimeSpan` -Klassen finden Sie im Artikel [Datum und Uhrzeit: Benutzeroberflächenautomatisierungs-Unterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ATLComTime.h  
  
##  <a name="a-namecoledatetimespanrelationaloperatorsa--coledatetimespan-relational-operators"></a><a name="coledatetimespan_relational_operators"></a>COleDateTimeSpan relationale Operatoren  
 Vergleichsoperatoren.  
  
```
bool operator==(const COleDateTimeSpan& dateSpan) const throw();
bool operator!=(const COleDateTimeSpan& dateSpan) const throw();
bool operator<(const COleDateTimeSpan& dateSpan) const throw();
bool operator>(const COleDateTimeSpan& dateSpan) const throw();
bool operator<=(const COleDateTimeSpan& dateSpan) const throw();
bool operator>=(const COleDateTimeSpan& dateSpan) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 *dateSpan*  
 Der zu vergleichende `COleDateTimeSpan`.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Operatoren vergleichen zwei Werte für Datum/Uhrzeit-Span und zurückgeben **true** Wenn die Bedingung true ist andernfalls **false**.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Ein ATLASSERT treten auf, wenn einer der Operanden ungültig ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#25;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_1.cpp)]  
  
 [!code-cpp[NVC_ATLMFC_Utilities&#26;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_2.cpp)]  
  
##  <a name="a-namecoledatetimespana--coledatetimespancoledatetimespan"></a><a name="coledatetimespan"></a>COleDateTimeSpan::COleDateTimeSpan  
 Erstellt ein `COleDateTimeSpan`-Objekt.  
  
```
COleDateTimeSpan() throw();
COleDateTimeSpan(double dblSpanSrc) throw();
COleDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `dblSpanSrc`  
 Die Anzahl der Tage, die in die neue kopiert werden `COleDateTimeSpan` Objekt.  
  
 `lDays`, `nHours`, `nMins`, `nSecs`  
 Geben Sie die Werte für Datum und Uhrzeit in die neue kopiert werden `COleDateTimeSpan` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Alle diese Konstruktoren Erstellen neuer `COleDateTimeSpan` Objekte, die mit dem angegebenen Wert initialisiert. Eine kurze Beschreibung jeder dieser Konstruktoren folgt:  
  
- **COleDateTimeSpan ()** erstellt ein `COleDateTimeSpan` Objekt mit 0 initialisiert.  
  
- **COleDateTimeSpan (** `dblSpanSrc` **)** erstellt ein `COleDateTimeSpan` Objekt aus einen Gleitkommawert.  
  
- **COleDateTimeSpan (** `lDays` **,** `nHours` **,** `nMins` **,** `nSecs` **)** erstellt ein `COleDateTimeSpan` Objekt mit den angegebenen numerischen Werten initialisiert.  
  
 Der Status der neuen `COleDateTimeSpan` Objekt zu gültigen festgelegt ist.  
  
 Weitere Informationen über die Grenzen für `COleDateTimeSpan` Werte finden Sie im Artikel [Datum und Uhrzeit: Benutzeroberflächenautomatisierungs-Unterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&14;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_3.cpp)]  
  
##  <a name="a-nameformata--coledatetimespanformat"></a><a name="format"></a>COleDateTimeSpan::Format  
 Generiert eine formatierte Zeichenfolge-Darstellung des ein `COleDateTimeSpan` Objekt.  
  
```
CString Format(LPCTSTR pFormat) const;
CString Format(UINT nID) const;
```  
  
### <a name="parameters"></a>Parameter  
 `pFormat`  
 Eine Formatierungszeichenfolge ähnelt der `printf` Formatierungszeichenfolge. Formatierungscodes Prozentsatz vorangestellt ( `%`) anmelden, werden mit den entsprechenden ersetzt `COleDateTimeSpan` Komponente. Andere Zeichen in der Formatierungszeichenfolge werden in der zurückgegebenen Zeichenfolge unverändert kopiert. Der Wert und die Bedeutung der Formatierungscodes für **Format** sind nachfolgend aufgeführt:  
  
- **"% H"** Stunden in den aktuellen Tag  
  
- **"% M"** in der aktuellen Stunde Minuten  
  
- **%S** Sekunden in der aktuellen Minute  
  
- **%%**Prozentzeichen  
  
 Die vier Formatcodes, die oben aufgeführten sind nur Codes, die Format akzeptiert.  
  
-  
  
 `nID`  
 Die Ressourcen-ID für die Format-Zeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` , der den formatierten Wert für Datum/Uhrzeit-Span enthält.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktionen, um eine formatierte Darstellung des Werts Zeitraum zu erstellen. Wenn der Status dieser `COleDateTimeSpan` Objekt ist null, der Rückgabewert ist eine leere Zeichenfolge. Wenn der Status ungültig ist, wird die zurückgegebene Zeichenfolge durch die Zeichenfolgenressource angegeben **IDS_INVALID_DATETIMESPAN**.  
  
 Eine kurze Beschreibung der Formulare für diese Funktion folgt:  
  
 **Format(** `pFormat` **)**  
 Dieses Formular formatiert den Wert, der mit der Formatzeichenfolge mit speziellen Formatcodes, die ein Prozentzeichen (%) vorangestellt werden, wie in `printf`. Die Formatierungszeichenfolge wird als Parameter an die Funktion übergeben.  
  
 **Format(** `nID` **)**  
 Dieses Formular formatiert den Wert, der mit der Formatzeichenfolge mit speziellen Formatcodes, die ein Prozentzeichen (%) vorangestellt werden, wie in `printf`. Die Formatierungszeichenfolge ist eine Ressource. Die ID dieser Zeichenfolgenressource wird als Parameter übergeben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#15;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_4.cpp)]  
  
##  <a name="a-namegetdaysa--coledatetimespangetdays"></a><a name="getdays"></a>COleDateTimeSpan::GetDays  
 Ruft den Tagteil dieses Datum/Uhrzeit-Span-Werts ab.  
  
```
LONG GetDays() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Tagteil dieser Zeitspanne/Zeit Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die Rückgabe Werte aus dieser Funktion Bereich zwischen ca. – 3,615,000 und 3,615,000.  
  
 Für andere Funktionen, die den Wert der Abfrage ein `COleDateTimeSpan` Objekt, das die folgenden Memberfunktionen:  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities Nr.&16;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_5.cpp)]  
  
##  <a name="a-namegethoursa--coledatetimespangethours"></a><a name="gethours"></a>COleDateTimeSpan::GetHours  
 Ruft den Stundenteil dieses Datum/Uhrzeit-Span-Werts ab.  
  
```
LONG GetHours() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Stunden Teil dieser Zeitspanne/Zeit Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die Rückgabewerte dieser Funktion zwischen – 23 und 23.  
  
 Für andere Funktionen, die den Wert der Abfrage ein `COleDateTimeSpan` Objekt, das die folgenden Memberfunktionen:  
  
- [GetDays](#getdays)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&17;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_6.cpp)]  
  
##  <a name="a-namegetminutesa--coledatetimespangetminutes"></a><a name="getminutes"></a>COleDateTimeSpan::GetMinutes  
 Ruft den Minutenteil dieses Datum/Uhrzeit-Span-Werts ab.  
  
```
LONG GetMinutes() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Minuten Teil dieser Zeitspanne/Zeit Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die Rückgabewerte dieser Funktion Bereich von – 59 bis 59.  
  
 Für andere Funktionen, die den Wert der Abfrage ein `COleDateTimeSpan` Objekt, das die folgenden Memberfunktionen:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&18;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_7.cpp)]  
  
##  <a name="a-namegetsecondsa--coledatetimespangetseconds"></a><a name="getseconds"></a>COleDateTimeSpan::GetSeconds  
 Ruft den zweiten Teil dieses Datum/Uhrzeit-Span-Werts ab.  
  
```
LONG GetSeconds() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Den Sekundenteil dieses Datum/Uhrzeit-Span-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die Rückgabewerte dieser Funktion Bereich von – 59 bis 59.  
  
 Für andere Funktionen, die den Wert der Abfrage ein `COleDateTimeSpan` Objekt, das die folgenden Memberfunktionen:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities Nr.&19;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_8.cpp)]  
  
##  <a name="a-namegetstatusa--coledatetimespangetstatus"></a><a name="getstatus"></a>COleDateTimeSpan::GetStatus  
 Ruft ab, der den Status (Gültigkeit) `COleDateTimeSpan` Objekt.  
  
```
DateTimeSpanStatus GetStatus() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Status dieser `COleDateTimeSpan` Wert.  
  
### <a name="remarks"></a>Hinweise  
 Der Rückgabewert wird definiert, indem die **DateTimeSpanStatus** -Enumerationstyp definiert ist die `COleDateTimeSpan` Klasse.  
  
 `enum DateTimeSpanStatus{`  
  
 `valid = 0,`  
  
 `invalid = 1,`  
  
 `null = 2,`  
  
 `};`  
  
 Eine kurze Beschreibung dieser Status-Werte finden Sie in der folgenden Liste:  
  
- **COleDateTimeSpan::valid** gibt an, dass diese `COleDateTimeSpan` -Objekt gültig ist.  
  
- **COleDateTimeSpan::invalid** gibt an, dass diese `COleDateTimeSpan` Objekt ist ungültig; d. h. möglicherweise der Wert falsch.  
  
- **COleDateTimeSpan::null** gibt an, dass diese `COleDateTimeSpan` Objekt null ist, d. h., dass für dieses Objekt kein Wert angegeben wurde. (Dies ist "null", in dem Sinne Datenbank mit"kein Wert" im Gegensatz zu C++ **NULL**.)  
  
 Der Status einer `COleDateTimeSpan` Objekt ist ungültig, in den folgenden Fällen:  
  
-   Wenn dieses Objekt einen Überlauf oder Unterlauf während eines Zuweisungsvorgangs arithmetische nämlich aufgetreten `+=` oder `-=`.  
  
-   Wenn ein ungültiger Wert für dieses Objekt zugewiesen wurde.  
  
-   Wenn der Status des Objekts explizit festgelegt wurde, um ungültige mit `SetStatus`.  
  
 Weitere Informationen zu den Vorgängen, die den Status auf ungültige festlegen können, finden Sie unter [COleDateTimeSpan::operator +, -](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) und [COleDateTimeSpan::operator +=, -=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq).  
  
 Weitere Informationen über die Grenzen für `COleDateTimeSpan` Werte finden Sie im Artikel [Datum und Uhrzeit: Benutzeroberflächenautomatisierungs-Unterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="a-namegettotaldaysa--coledatetimespangettotaldays"></a><a name="gettotaldays"></a>COleDateTimeSpan::GetTotalDays  
 Ruft dieses Datum/Uhrzeit-Span-Wert in Tagen angegeben.  
  
```
double GetTotalDays() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Dieses Datum/Uhrzeit-Span-Wert in Tagen angegeben. Obwohl diese Funktion Prototyp einen Double-Wert zurückgegeben wird, wird immer einen ganzzahligen Wert zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Die Rückgabewerte dieser Funktion zwischen ca. – 3.65e6 und 3.65e6.  
  
 Für andere Funktionen, die den Wert der Abfrage ein `COleDateTimeSpan` Objekt, das die folgenden Memberfunktionen:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&20;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_9.cpp)]  
  
##  <a name="a-namegettotalhoursa--coledatetimespangettotalhours"></a><a name="gettotalhours"></a>COleDateTimeSpan::GetTotalHours  
 Ruft dieses Datum/Uhrzeit-Span-Wert, ausgedrückt in Stunden ab.  
  
```
double GetTotalHours() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Dieses Datum/Uhrzeit-Span-Wert, ausgedrückt in Stunden. Obwohl diese Funktion Prototyp einen Double-Wert zurückgegeben wird, wird immer einen ganzzahligen Wert zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Die Rückgabewerte dieser Funktion zwischen ca. – 8.77e7 und 8.77e7.  
  
 Für andere Funktionen, die den Wert der Abfrage ein `COleDateTimeSpan` Objekt, das die folgenden Memberfunktionen:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetTotalDays](#gettotaldays).  
  
##  <a name="a-namegettotalminutesa--coledatetimespangettotalminutes"></a><a name="gettotalminutes"></a>COleDateTimeSpan::GetTotalMinutes  
 Ruft dieses Datum/Uhrzeit-Span-Wert in Minuten ausgedrückt.  
  
```
double GetTotalMinutes() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Dieses Datum/Uhrzeit-Span-Wert in Minuten ausgedrückt. Obwohl diese Funktion Prototyp einen Double-Wert zurückgegeben wird, wird immer einen ganzzahligen Wert zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Die Rückgabewerte dieser Funktion zwischen ca. – 5.26e9 und 5.26e9.  
  
 Für andere Funktionen, die den Wert der Abfrage ein `COleDateTimeSpan` Objekt, das die folgenden Memberfunktionen:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetTotalDays](#gettotaldays).  
  
##  <a name="a-namegettotalsecondsa--coledatetimespangettotalseconds"></a><a name="gettotalseconds"></a>COleDateTimeSpan::GetTotalSeconds  
 Ruft dieses Datum/Uhrzeit-Span-Wert in Sekunden angegeben.  
  
```
double GetTotalSeconds() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Dieses Datum/Uhrzeit-Span-Wert in Sekunden angegeben. Obwohl diese Funktion Prototyp einen Double-Wert zurückgegeben wird, wird immer einen ganzzahligen Wert zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Die Rückgabewerte von dieser Funktion im Bereich zwischen ca. – 3.16e11, 3.16e11.  
  
 Für andere Funktionen, die den Wert der Abfrage ein `COleDateTimeSpan` Objekt, das die folgenden Memberfunktionen:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetTotalDays](#gettotaldays).  
  
##  <a name="a-namemspana--coledatetimespanmspan"></a><a name="m_span"></a>COleDateTimeSpan::m_span  
 Die zugrunde liegende **doppelte** Wert für diesen `COleDateTime` Objekt.  
  
```
double m_span;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Wert drückt der Datums-/Zeitraum in Tagen.  
  
> [!CAUTION]
>  Ändern den Wert in der **doppelte** -Datenmember ändert sich den Wert dieses `COleDateTimeSpan` Objekt. Er ändert nicht den Status dieses `COleDateTimeSpan` Objekt.  
  
##  <a name="a-namemstatusa--coledatetimespanmstatus"></a><a name="m_status"></a>COleDateTimeSpan::m_status  
 Der Typ für dieses Datenelement ist den Aufzählungstyp **DateTimeSpanStatus**, definiert in der `COleDateTimeSpan` Klasse.  
  
```
DateTimeSpanStatus m_status;
```  
  
### <a name="remarks"></a>Hinweise  
 `enum DateTimeSpanStatus{`  
  
 `valid = 0,`  
  
 `invalid = 1,`  
  
 `null = 2,`  
  
 `};`  
  
 Eine kurze Beschreibung dieser Status-Werte finden Sie in der folgenden Liste:  
  
- **COleDateTimeSpan::valid** gibt an, dass diese `COleDateTimeSpan` -Objekt gültig ist.  
  
- **COleDateTimeSpan::invalid** gibt an, dass diese `COleDateTimeSpan` Objekt ist ungültig; d. h. möglicherweise der Wert falsch.  
  
- **COleDateTimeSpan::null** gibt an, dass diese `COleDateTimeSpan` Objekt null ist, d. h., dass für dieses Objekt kein Wert angegeben wurde. (Dies ist "null", in dem Sinne Datenbank mit"kein Wert" im Gegensatz zu C++ **NULL**.)  
  
 Der Status einer `COleDateTimeSpan` Objekt ist ungültig, in den folgenden Fällen:  
  
-   Wenn dieses Objekt einen Überlauf oder Unterlauf während eines Zuweisungsvorgangs arithmetische nämlich aufgetreten `+=` oder `-=`.  
  
-   Wenn ein ungültiger Wert für dieses Objekt zugewiesen wurde.  
  
-   Wenn der Status des Objekts explizit festgelegt wurde, um ungültige mit [SetStatus](#setstatus).  
  
 Weitere Informationen zu den Vorgängen, die den Status auf ungültige festlegen können, finden Sie unter [COleDateTimeSpan::operator +, -](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) und [COleDateTimeSpan::operator +=, -=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq).  
  
> [!CAUTION]
>  Dieses Datenelement ist für die Erweiterte Programmierung Situationen. Verwenden Sie die Inline-Memberfunktionen [GetStatus](#getstatus) und [SetStatus](#setstatus). Finden Sie unter `SetStatus` Weitere Warnhinweise in Bezug auf dieses Datenelement explizit festlegen.  
  
 Weitere Informationen über die Grenzen für `COleDateTimeSpan` Werte finden Sie im Artikel [Datum und Uhrzeit: Benutzeroberflächenautomatisierungs-Unterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="a-nameoperatoreqa--coledatetimespanoperator-"></a><a name="operator_eq"></a>COleDateTimeSpan::operator =  
 Kopiert einen `COleDateTimeSpan` Wert.  
  
```
COleDateTimeSpan& operator=(double dblSpanSrc) throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese überladenen Zuweisungsoperator kopiert den Wert des Datum/Zeit-Span in diesen `COleDateTimeSpan` Objekt.  
  
##  <a name="a-nameoperatoradd-a--coledatetimespanoperator---"></a><a name="operator_add_-"></a>COleDateTimeSpan::operator +, -  
 Hinzufügen, subtrahieren, und ändern Sie die Zeichen für `COleDateTimeSpan` Werte.  
  
```
COleDateTimeSpan operator+(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-() const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Die ersten beiden Operatoren können Sie die Addition und Subtraktion von Datum/Uhrzeit-Span-Werte. Die dritte können Sie die Vorzeichen einer Datum/Uhrzeit-Span-Werts zu ändern.  
  
 Wenn einer der Operanden null ist, ist den Status der resultierenden `COleDateTimeSpan` Wert ist null.  
  
 Wenn die Operanden ist ungültig, und der andere nicht null ist Operand, den Status der resultierenden `COleDateTimeSpan` Wert ist ungültig.  
  
 Weitere Informationen zu den gültig, ungültig und null-Status-Werte, finden Sie unter der [M_status](#m_status) Membervariablen gespeichert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&23;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_10.cpp)]  
  
##  <a name="a-nameoperatoraddeq-eqa--coledatetimespanoperator---"></a><a name="operator_add_eq_-_eq"></a>COleDateTimeSpan::operator +=, =  
 Addition und Subtraktion ein `COleDateTimeSpan` Wert aus diesem `COleDateTimeSpan` Wert.  
  
```
COleDateTimeSpan& operator+=(const COleDateTimeSpan dateSpan) throw();
COleDateTimeSpan& operator-=(const COleDateTimeSpan dateSpan) throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Operatoren können Sie die Addition und Subtraktion von Datum/Uhrzeit-Span-Werte aus dieser `COleDateTimeSpan` Objekt. Wenn einer der Operanden null ist, ist den Status der resultierenden `COleDateTimeSpan` Wert ist null.  
  
 Wenn die Operanden ist ungültig, und der andere nicht null ist Operand, den Status der resultierenden `COleDateTimeSpan` Wert ist ungültig.  
  
 Weitere Informationen zu den gültig, ungültig und null-Status-Werte, finden Sie unter der [M_status](#m_status) Membervariablen gespeichert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#24;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_11.cpp)]  
  
##  <a name="a-nameoperatordoublea--coledatetimespanoperator-double"></a><a name="operator_double"></a>Doppelte COleDateTimeSpan::operator  
 Konvertiert dieses `COleDateTimeSpan` -Wert in einem **doppelte**.  
  
```
operator double() const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator gibt den Wert dieses `COleDateTimeSpan` Wert als Gleitkommazahl von Tagen.  
  
##  <a name="a-namesetdatetimespana--coledatetimespansetdatetimespan"></a><a name="setdatetimespan"></a>COleDateTimeSpan::SetDateTimeSpan  
 Legt den Wert dieses Datum/Uhrzeit-Span-Werts.  
  
```
void SetDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lDays`, `nHours`, `nMins`, `nSecs`  
 Zeigen die Werte-Zeitraum und Zeitraum, in diese kopiert werden `COleDateTimeSpan` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Für Funktionen, die den Wert der Abfrage ein `COleDateTimeSpan` Objekt, das die folgenden Memberfunktionen:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&21;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_12.cpp)]  
  
##  <a name="a-namesetstatusa--coledatetimespansetstatus"></a><a name="setstatus"></a>COleDateTimeSpan::SetStatus  
 Setzt den Status (Gültigkeit) dieses `COleDateTimeSpan` Objekt.  
  
```
void SetStatus(DateTimeSpanStatus status) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *status*  
 Der neue Statuswert für diesen `COleDateTimeSpan` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die *Status* Parameterwert wird definiert, indem die **DateTimeSpanStatus** -Enumerationstyp definiert ist die `COleDateTimeSpan` Klasse.  
  
 `enum DateTimeSpanStatus{`  
  
 `valid = 0,`  
  
 `invalid = 1,`  
  
 `null = 2,`  
  
 `};`  
  
 Eine kurze Beschreibung dieser Status-Werte finden Sie in der folgenden Liste:  
  
- **COleDateTimeSpan::valid** gibt an, dass diese `COleDateTimeSpan` -Objekt gültig ist.  
  
- **COleDateTimeSpan::invalid** gibt an, dass diese `COleDateTimeSpan` Objekt ist ungültig; d. h. möglicherweise der Wert falsch.  
  
- **COleDateTimeSpan::null** gibt an, dass diese `COleDateTimeSpan` Objekt null ist, d. h., dass für dieses Objekt kein Wert angegeben wurde. (Dies ist "null", in dem Sinne Datenbank mit"kein Wert" im Gegensatz zu C++ **NULL**.)  
  
    > [!CAUTION]
    >  Diese Funktion ist für die Erweiterte Programmierung Situationen. Diese Funktion werden die Daten in diesem Objekt nicht geändert. Dieser wird am häufigsten verwendet, legen Sie den Status auf `null` oder **ungültige**. Beachten Sie, dass der Zuweisungsoperator ( [Operator =](#eq)) und [SetDateTimeSpan](#setdatetimespan) sollten Sie den Status des Objekts basierend auf der Quelle Werte festlegen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#22;](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_13.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [COleDateTime-Klasse](../../atl-mfc-shared/reference/coledatetime-class.md)   
 [CTime-Klasse](../../atl-mfc-shared/reference/ctime-class.md)   
 [CTimeSpan-Klasse](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [ATL/MFC-freigegeben Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)



