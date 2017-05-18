---
title: COleDateTimeSpan Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::COleDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::Format
- ATLCOMTIME/ATL::COleDateTimeSpan::GetDays
- ATLCOMTIME/ATL::COleDateTimeSpan::GetHours
- ATLCOMTIME/ATL::COleDateTimeSpan::GetMinutes
- ATLCOMTIME/ATL::COleDateTimeSpan::GetSeconds
- ATLCOMTIME/ATL::COleDateTimeSpan::GetStatus
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalDays
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalHours
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalMinutes
- ATLCOMTIME/ATL::COleDateTimeSpan::GetTotalSeconds
- ATLCOMTIME/ATL::COleDateTimeSpan::SetDateTimeSpan
- ATLCOMTIME/ATL::COleDateTimeSpan::SetStatus
- ATLCOMTIME/ATL::COleDateTimeSpan::m_span
- ATLCOMTIME/ATL::COleDateTimeSpan::m_status
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 0c696f59a6f4be7b4d966aad2a16a846d737009f
ms.contentlocale: de-de
ms.lasthandoff: 04/04/2017

---
# <a name="coledatetimespan-class"></a>COleDateTimeSpan-Klasse
Stellt eine relative Zeit, eine Zeitspanne dar.  
  
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
|[COleDateTimeSpan::Format](#format)|Generiert eine formatierte Zeichenfolgendarstellung ein `COleDateTimeSpan` Objekt.|  
|[COleDateTimeSpan::GetDays](#getdays)|Gibt dem Tagteil der Spanne dies `COleDateTimeSpan` -Objekt darstellt.|  
|[COleDateTimeSpan::GetHours](#gethours)|Gibt dem Stundenteil der Spanne dies `COleDateTimeSpan` -Objekt darstellt.|  
|[COleDateTimeSpan::GetMinutes](#getminutes)|Gibt dem Minutenteil der Spanne dies `COleDateTimeSpan` -Objekt darstellt.|  
|[COleDateTimeSpan::GetSeconds](#getseconds)|Gibt dem zweiten Teil der Spanne dies `COleDateTimeSpan` -Objekt darstellt.|  
|[COleDateTimeSpan::GetStatus](#getstatus)|Ruft ab, der den Status (Gültigkeit) `COleDateTimeSpan` Objekt.|  
|[COleDateTimeSpan::GetTotalDays](#gettotaldays)|Gibt die Anzahl der Tage dies `COleDateTimeSpan` -Objekt darstellt.|  
|[COleDateTimeSpan::GetTotalHours](#gettotalhours)|Gibt die Anzahl der Stunden dieser `COleDateTimeSpan` -Objekt darstellt.|  
|[COleDateTimeSpan::GetTotalMinutes](#gettotalminutes)|Gibt die Anzahl der Minuten dies `COleDateTimeSpan` -Objekt darstellt.|  
|[COleDateTimeSpan::GetTotalSeconds](#gettotalseconds)|Gibt die Anzahl der Sekunden dies `COleDateTimeSpan` -Objekt darstellt.|  
|[COleDateTimeSpan::SetDateTimeSpan](#setdatetimespan)|Legt den Wert dieses `COleDateTimeSpan` Objekt.|  
|[COleDateTimeSpan::SetStatus](#setstatus)|Legt den Status (Gültigkeit) dieses `COleDateTimeSpan` Objekt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|||  
|-|-|  
|[Operator +, -](#operator_add_-)|Hinzufügen, subtrahiert werden soll, und ändern Sie signieren, damit `COleDateTimeSpan` Werte.|  
|[Operator +=, =](#operator_add_eq_-_eq)|Addition und Subtraktion ein `COleDateTimeSpan` Wert aus diesem `COleDateTimeSpan` Wert.|  
|[Operator =](#operator_eq)|Kopiert ein `COleDateTimeSpan` Wert.|  
|[Operator ==,<,></,><>](#coledatetimespan_relational_operators)|Vergleichen Sie zwei `COleDateTimeSpan` Werte.|  
|[Operator double](#operator_double)|Konvertiert dieses `COleDateTimeSpan` -Wert in einen **doppelte**.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDateTimeSpan::m_span](#m_span)|Enthält die zugrunde liegende **doppelte** dafür `COleDateTimeSpan` Objekt.|  
|[COleDateTimeSpan::m_status](#m_status)|Enthält den Status dieses `COleDateTimeSpan` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `COleDateTimeSpan`eine Basisklasse verfügt nicht über.  
  
 Ein `COleDateTimeSpan` behält Zeit in Tagen.  
  
 `COleDateTimeSpan`wird verwendet, mit dessen Begleitklasse [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md). `COleDateTime`Kapselt die **Datum** -Datentyp der OLE-Automatisierung. `COleDateTime`Stellt die absoluten Zeitwerte dar. Alle `COleDateTime` Berechnungen umfassen `COleDateTimeSpan` Werte. Die Beziehung zwischen diesen Klassen ist analog zu den zwischen [CTime](../../atl-mfc-shared/reference/ctime-class.md) und [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md).  
  
 Weitere Informationen zu den `COleDateTime` und `COleDateTimeSpan` Klassen finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ATLComTime.h  
  
##  <a name="coledatetimespan_relational_operators"></a>COleDateTimeSpan relationale Operatoren  
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
 Diese Operatoren vergleichen zwei Werte für Datum/Uhrzeit-Spanne und zurückgeben **"true"** , wenn die Bedingung, andernfalls "true ist" **"false"**.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Ein ATLASSERT geschieht, wenn einer der Operanden ungültig ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities #25](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_1.cpp)]  
  
 [!code-cpp[NVC_ATLMFC_Utilities #26](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_2.cpp)]  
  
##  <a name="coledatetimespan"></a>COleDateTimeSpan::COleDateTimeSpan  
 Erstellt ein `COleDateTimeSpan`-Objekt.  
  
```
COleDateTimeSpan() throw();
COleDateTimeSpan(double dblSpanSrc) throw();
COleDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `dblSpanSrc`  
 Die Anzahl der Tage an, in die neue kopiert werden `COleDateTimeSpan` Objekt.  
  
 `lDays`, `nHours`, `nMins`, `nSecs`  
 Geben Sie die Werte für Datum und Uhrzeit an, in die neue kopiert werden `COleDateTimeSpan` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Alle diese Konstruktoren erstellen Sie eine neue `COleDateTimeSpan` Objekte, die auf den angegebenen Wert initialisiert. Eine kurze Beschreibung jeder dieser Konstruktoren lautet folgendermaßen:  
  
- **COleDateTimeSpan ()** erstellt eine `COleDateTimeSpan` Objekt mit 0 initialisiert.  
  
- **COleDateTimeSpan (** `dblSpanSrc` **)** erstellt eine `COleDateTimeSpan` Objekt aus einen Gleitkommawert.  
  
- **COleDateTimeSpan (** `lDays` **,** `nHours` **,** `nMins` **,** `nSecs` **)** erstellt eine `COleDateTimeSpan` Objekt mit den angegebenen numerischen Werten initialisiert.  
  
 Der Status der neuen `COleDateTimeSpan` Objekt zu gültigen festgelegt ist.  
  
 Weitere Informationen über die Grenzen für `COleDateTimeSpan` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities Nr. 14](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_3.cpp)]  
  
##  <a name="format"></a>COleDateTimeSpan::Format  
 Generiert eine formatierte Zeichenfolgendarstellung ein `COleDateTimeSpan` Objekt.  
  
```
CString Format(LPCTSTR pFormat) const;
CString Format(UINT nID) const;
```  
  
### <a name="parameters"></a>Parameter  
 `pFormat`  
 Eine Formatierungszeichenfolge ähnelt der `printf` Formatierungszeichenfolge. Formatierungscodes vorangestellt Prozentsatz ( `%`) anmelden, werden mit den entsprechenden ersetzt `COleDateTimeSpan` Komponente. Andere Zeichen in der Formatzeichenfolge werden in der zurückgegebenen Zeichenfolge unverändert kopiert. Der Wert und die Bedeutung von Formatierungscodes für **Format** sind nachfolgend aufgeführt:  
  
- **"% H"** Stunden den heutigen Tag  
  
- **"% M"** Minuten in der aktuellen Stunde  
  
- **"% S"** Sekunden in der aktuellen Minute  
  
- **%%**Prozentzeichen  
  
 Die vier oben aufgeführten Formatcodes handelt es sich um die einzige Codes, von denen Format akzeptiert.  
  
-  
  
 `nID`  
 Die Ressourcen-ID für die formatsteuerzeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` , der den formatierten Wert für Datum/Uhrzeit-Bereich enthält.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktionen, um eine formatierte Darstellung des Zeitspanne Werts. Wenn der Status dieser `COleDateTimeSpan` Objekt null ist, wird eine leere Zeichenfolge zurückgegeben. Wenn der Status ungültig ist, ist die Rückgabezeichenfolge eine Zeichenfolgenressource angegeben **IDS_INVALID_DATETIMESPAN**.  
  
 Eine kurze Beschreibung der Formate für diese Funktion lautet folgendermaßen:  
  
 **Format(** `pFormat` **)**  
 Dieses Formular formatiert den Wert, der mit der Formatzeichenfolge, die spezielle Formatierung Codes enthält, die einem Prozentzeichen (%) vorangestellt werden, wie in `printf`. Die Formatierungszeichenfolge wird als Parameter an die Funktion übergeben.  
  
 **Format(** `nID` **)**  
 Dieses Formular formatiert den Wert, der mit der Formatzeichenfolge, die spezielle Formatierung Codes enthält, die einem Prozentzeichen (%) vorangestellt werden, wie in `printf`. Die Formatzeichenfolge ist eine Ressource. Die ID der diesem Zeichenfolgenressource wird als Parameter übergeben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities #15](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_4.cpp)]  
  
##  <a name="getdays"></a>COleDateTimeSpan::GetDays  
 Ruft den Tagteil von diesen Wert für Datum/Uhrzeit-Spanne ab.  
  
```
LONG GetDays() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Tagteil dieser Wert für Datum/Uhrzeit-Spanne.  
  
### <a name="remarks"></a>Hinweise  
 Das zurückgegebene Werte aus dieser Funktion Bereich zwischen ca. - 3,615,000 und 3,615,000.  
  
 Für andere Funktionen, die den Wert der Abfrage eine `COleDateTimeSpan` Objekt, finden Sie unter den folgenden Member-Funktionen:  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities Nr. 16](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_5.cpp)]  
  
##  <a name="gethours"></a>COleDateTimeSpan::GetHours  
 Ruft den Stundenteil dieses Werts Datum/Uhrzeit-Spanne ab.  
  
```
LONG GetHours() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Teil Stunden dieser Wert für Datum/Uhrzeit-Spanne.  
  
### <a name="remarks"></a>Hinweise  
 Die Rückgabewerte von dieser Funktion zwischen - 23 und 23.  
  
 Für andere Funktionen, die den Wert der Abfrage eine `COleDateTimeSpan` Objekt, finden Sie unter den folgenden Member-Funktionen:  
  
- [GetDays](#getdays)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities #17](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_6.cpp)]  
  
##  <a name="getminutes"></a>COleDateTimeSpan::GetMinutes  
 Ruft den Minutenteil dieses Werts Datum/Uhrzeit-Spanne ab.  
  
```
LONG GetMinutes() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Minuten Teil dieser Wert für Datum/Uhrzeit-Spanne.  
  
### <a name="remarks"></a>Hinweise  
 Die Rückgabewerte von dieser Funktion zwischen - 59 und 59.  
  
 Für andere Funktionen, die den Wert der Abfrage eine `COleDateTimeSpan` Objekt, finden Sie unter den folgenden Member-Funktionen:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities Nr. 18](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_7.cpp)]  
  
##  <a name="getseconds"></a>COleDateTimeSpan::GetSeconds  
 Ruft den zweiten Teil dieser Wert für Datum/Uhrzeit-Spanne ab.  
  
```
LONG GetSeconds() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Sekundenangabe dieses Werts Datum/Uhrzeit-Spanne.  
  
### <a name="remarks"></a>Hinweise  
 Die Rückgabewerte von dieser Funktion zwischen - 59 und 59.  
  
 Für andere Funktionen, die den Wert der Abfrage eine `COleDateTimeSpan` Objekt, finden Sie unter den folgenden Member-Funktionen:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities Nr. 19](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_8.cpp)]  
  
##  <a name="getstatus"></a>COleDateTimeSpan::GetStatus  
 Ruft ab, der den Status (Gültigkeit) `COleDateTimeSpan` Objekt.  
  
```
DateTimeSpanStatus GetStatus() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Status dieser `COleDateTimeSpan` Wert.  
  
### <a name="remarks"></a>Hinweise  
 Der Rückgabewert wird definiert, indem die **DateTimeSpanStatus** Aufzählungstyp innerhalb definiert ist die `COleDateTimeSpan` Klasse.  
  
```  
enum DateTimeSpanStatus{  
   valid = 0,  
   invalid = 1,  
   null = 2,  
};  
```  
  
 Eine kurze Beschreibung von diesen Statuswerten verwenden finden Sie in der folgenden Liste:  
  
- **COleDateTimeSpan::valid** gibt an, dass diese `COleDateTimeSpan` -Objekt gültig ist.  
  
- **COleDateTimeSpan::invalid** gibt an, dass diese `COleDateTimeSpan` Objekt ist ungültig; d. h. der Wert ist möglicherweise falsch.  
  
- **COleDateTimeSpan::null** gibt an, dass diese `COleDateTimeSpan` ist null, d. h., dass für dieses Objekt kein Wert angegeben wurde. (Dies ist "null", in dem Sinne Datenbank mit"kein Wert" im Gegensatz zu C++ **NULL**.)  
  
 Der Status einer `COleDateTimeSpan` Objekt ist ungültig in den folgenden Fällen:  
  
-   Wenn dieses Objekt einen Überlauf oder Unterlauf während eines arithmetischen Zuweisungsvorgangs, nämlich aufgetreten `+=` oder `-=`.  
  
-   Wenn dieses Objekt ein ungültiger Wert zugewiesen wurde.  
  
-   Wenn der Status dieses Objekts explizit festgelegt wurde, um ungültige mit `SetStatus`.  
  
 Weitere Informationen zu den Vorgängen, die den Status auf ungültig festgelegt werden kann, finden Sie unter [COleDateTimeSpan::operator +, -](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) und [COleDateTimeSpan::operator +=, -=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq).  
  
 Weitere Informationen über die Grenzen für `COleDateTimeSpan` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="gettotaldays"></a>COleDateTimeSpan::GetTotalDays  
 Ruft dieses Datum/Uhrzeit-Spanne-Wert, ausgedrückt in Tagen ab.  
  
```
double GetTotalDays() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Dieses Datum/Uhrzeit-Spanne-Wert, ausgedrückt in Tagen. Obwohl diese Funktion Prototyp ein Double-Wert zurückgegeben wird, wird immer einen ganzzahligen Wert zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Die Rückgabewerte von dieser Funktion zwischen ca. - 3.65e6 und 3.65e6.  
  
 Für andere Funktionen, die den Wert der Abfrage eine `COleDateTimeSpan` Objekt, finden Sie unter den folgenden Member-Funktionen:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities Nr. 20](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_9.cpp)]  
  
##  <a name="gettotalhours"></a>COleDateTimeSpan::GetTotalHours  
 Ruft dieses Datum/Uhrzeit-Span-Wert, ausgedrückt in Stunden ab.  
  
```
double GetTotalHours() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Dieses Datum/Uhrzeit-Spanne-Wert, ausgedrückt in Stunden. Obwohl diese Funktion Prototyp ein Double-Wert zurückgegeben wird, wird immer einen ganzzahligen Wert zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Die Rückgabewerte von dieser Funktion zwischen ca. - 8.77e7 und 8.77e7.  
  
 Für andere Funktionen, die den Wert der Abfrage eine `COleDateTimeSpan` Objekt, finden Sie unter den folgenden Member-Funktionen:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetTotalDays](#gettotaldays).  
  
##  <a name="gettotalminutes"></a>COleDateTimeSpan::GetTotalMinutes  
 Ruft dieses Datum/Uhrzeit-Span-Wert, ausgedrückt in Minuten ab.  
  
```
double GetTotalMinutes() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Dieses Datum/Uhrzeit-Span-Wert, ausgedrückt in Minuten. Obwohl diese Funktion Prototyp ein Double-Wert zurückgegeben wird, wird immer einen ganzzahligen Wert zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Die Rückgabewerte von dieser Funktion zwischen ca. - 5.26e9 und 5.26e9.  
  
 Für andere Funktionen, die den Wert der Abfrage eine `COleDateTimeSpan` Objekt, finden Sie unter den folgenden Member-Funktionen:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetTotalDays](#gettotaldays).  
  
##  <a name="gettotalseconds"></a>COleDateTimeSpan::GetTotalSeconds  
 Ruft dieses Datum/Uhrzeit-Span-Wert in Sekunden ausgedrückt ab.  
  
```
double GetTotalSeconds() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Dieses Datum/Uhrzeit-Span-Wert in Sekunden angegeben. Obwohl diese Funktion Prototyp ein Double-Wert zurückgegeben wird, wird immer einen ganzzahligen Wert zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Die Rückgabewerte von dieser Funktion im Bereich zwischen ca. - 3.16e11 zu 3.16e11.  
  
 Für andere Funktionen, die den Wert der Abfrage eine `COleDateTimeSpan` Objekt, finden Sie unter den folgenden Member-Funktionen:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetTotalDays](#gettotaldays).  
  
##  <a name="m_span"></a>COleDateTimeSpan::m_span  
 Die zugrunde liegende **doppelte** Wert für diesen `COleDateTime` Objekt.  
  
```
double m_span;
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert gibt die Datum/Uhrzeit-Spanne in Tagen.  
  
> [!CAUTION]
>  Ändern des Werts in der **doppelte** Datenmember ändert sich den Wert dieses `COleDateTimeSpan` Objekt. Ändert nicht den Status dieses `COleDateTimeSpan` Objekt.  
  
##  <a name="m_status"></a>COleDateTimeSpan::m_status  
 Der Typ für dieses Datenelement ist der enumerierten Typ **DateTimeSpanStatus**, die definiert ist, in der `COleDateTimeSpan` Klasse.  
  
```
DateTimeSpanStatus m_status;
```  
  
### <a name="remarks"></a>Hinweise  
  
```  
enum DateTimeSpanStatus{  
   valid = 0,  
   invalid = 1,  
   null = 2,  
   };  
```  
  
 Eine kurze Beschreibung von diesen Statuswerten verwenden finden Sie in der folgenden Liste:  
  
- **COleDateTimeSpan::valid** gibt an, dass diese `COleDateTimeSpan` -Objekt gültig ist.  
  
- **COleDateTimeSpan::invalid** gibt an, dass diese `COleDateTimeSpan` Objekt ist ungültig; d. h. der Wert ist möglicherweise falsch.  
  
- **COleDateTimeSpan::null** gibt an, dass diese `COleDateTimeSpan` ist null, d. h., dass für dieses Objekt kein Wert angegeben wurde. (Dies ist "null", in dem Sinne Datenbank mit"kein Wert" im Gegensatz zu C++ **NULL**.)  
  
 Der Status einer `COleDateTimeSpan` Objekt ist ungültig in den folgenden Fällen:  
  
-   Wenn dieses Objekt einen Überlauf oder Unterlauf während eines arithmetischen Zuweisungsvorgangs, nämlich aufgetreten `+=` oder `-=`.  
  
-   Wenn dieses Objekt ein ungültiger Wert zugewiesen wurde.  
  
-   Wenn der Status dieses Objekts explizit festgelegt wurde, um ungültige mit [SetStatus](#setstatus).  
  
 Weitere Informationen zu den Vorgängen, die den Status auf ungültig festgelegt werden kann, finden Sie unter [COleDateTimeSpan::operator +, -](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_-) und [COleDateTimeSpan::operator +=, -=](../../atl-mfc-shared/reference/coledatetime-class.md#operator_add_eq_-_eq).  
  
> [!CAUTION]
>  Dieses Datenelement ist für Situationen, Erweiterte Programmierung. Sie sollten die Inline-Memberfunktionen verwenden [GetStatus](#getstatus) und [SetStatus](#setstatus). Finden Sie unter `SetStatus` weiteren Warnhinweise bezüglich dieses Datenelement explizit festlegen.  
  
 Weitere Informationen über die Grenzen für `COleDateTimeSpan` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="operator_eq"></a>COleDateTimeSpan::operator =  
 Kopiert ein `COleDateTimeSpan` Wert.  
  
```
COleDateTimeSpan& operator=(double dblSpanSrc) throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese überladenen Zuweisungsoperator kopiert den Datum/Uhrzeit-Spanne Quellwert in diese `COleDateTimeSpan` Objekt.  
  
##  <a name="operator_add_-"></a>COleDateTimeSpan::operator +, -  
 Hinzufügen, subtrahiert werden soll, und ändern Sie signieren, damit `COleDateTimeSpan` Werte.  
  
```
COleDateTimeSpan operator+(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTimeSpan& dateSpan) const throw();
COleDateTimeSpan operator-() const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Die ersten beiden Operatoren können Sie die Addition und Subtraktion von Datum/Uhrzeit-Bereich Werte. Das dritte können Sie die Vorzeichen des einen Wert für Datum/Uhrzeit-Bereich zu ändern.  
  
 Wenn einer der Operanden null ist, ist den Status des resultierenden `COleDateTimeSpan` Wert ist null.  
  
 Wenn entweder der Operanden ist ungültig, und der andere nicht null ist Operand, den Status des resultierenden `COleDateTimeSpan` Wert ist ungültig.  
  
 Weitere Informationen auf den Status gültig, ungültig und null-Werten finden Sie unter der [M_status](#m_status) Membervariablen gespeichert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities #23](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_10.cpp)]  
  
##  <a name="operator_add_eq_-_eq"></a>COleDateTimeSpan::operator +=, =  
 Addition und Subtraktion ein `COleDateTimeSpan` Wert aus diesem `COleDateTimeSpan` Wert.  
  
```
COleDateTimeSpan& operator+=(const COleDateTimeSpan dateSpan) throw();
COleDateTimeSpan& operator-=(const COleDateTimeSpan dateSpan) throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Operatoren können Sie die Addition und Subtraktion von Datum/Uhrzeit-Spanne Werte aus dieser `COleDateTimeSpan` Objekt. Wenn einer der Operanden null ist, ist den Status des resultierenden `COleDateTimeSpan` Wert ist null.  
  
 Wenn entweder der Operanden ist ungültig, und der andere nicht null ist Operand, den Status des resultierenden `COleDateTimeSpan` Wert ist ungültig.  
  
 Weitere Informationen auf den Status gültig, ungültig und null-Werten finden Sie unter der [M_status](#m_status) Membervariablen gespeichert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities #24](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_11.cpp)]  
  
##  <a name="operator_double"></a>Doppelte COleDateTimeSpan::operator  
 Konvertiert dieses `COleDateTimeSpan` -Wert in einen **doppelte**.  
  
```
operator double() const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator gibt den Wert dieses `COleDateTimeSpan` Wert als Gleitkommazahl von Tagen.  
  
##  <a name="setdatetimespan"></a>COleDateTimeSpan::SetDateTimeSpan  
 Legt den Wert dieses Werts Datum/Uhrzeit-Spanne.  
  
```
void SetDateTimeSpan(LONG lDays, int nHours, int nMins, int nSecs) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lDays`, `nHours`, `nMins`, `nSecs`  
 Zeigen die Zeitspanne und Zeitspanne Werte, die in diese kopiert werden `COleDateTimeSpan` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Für Funktionen, die den Wert der Abfrage eine `COleDateTimeSpan` Objekt, finden Sie unter den folgenden Member-Funktionen:  
  
- [GetDays](#getdays)  
  
- [GetHours](#gethours)  
  
- [GetMinutes](#getminutes)  
  
- [GetSeconds](#getseconds)  
  
- [GetTotalDays](#gettotaldays)  
  
- [GetTotalHours](#gettotalhours)  
  
- [GetTotalMinutes](#gettotalminutes)  
  
- [GetTotalSeconds](#gettotalseconds)  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities #21](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_12.cpp)]  
  
##  <a name="setstatus"></a>COleDateTimeSpan::SetStatus  
 Legt den Status (Gültigkeit) dieses `COleDateTimeSpan` Objekt.  
  
```
void SetStatus(DateTimeSpanStatus status) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *status*  
 Der neue Statuswert für diesen `COleDateTimeSpan` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die *Status* Parameterwert wird definiert, indem Sie die **DateTimeSpanStatus** Aufzählungstyp innerhalb definiert ist die `COleDateTimeSpan` Klasse.  
  
```  
enum DateTimeSpanStatus{  
   valid = 0,  
   invalid = 1,  
   null = 2,  
   };  
```  
  
 Eine kurze Beschreibung von diesen Statuswerten verwenden finden Sie in der folgenden Liste:  
  
- **COleDateTimeSpan::valid** gibt an, dass diese `COleDateTimeSpan` -Objekt gültig ist.  
  
- **COleDateTimeSpan::invalid** gibt an, dass diese `COleDateTimeSpan` Objekt ist ungültig; d. h. der Wert ist möglicherweise falsch.  
  
- **COleDateTimeSpan::null** gibt an, dass diese `COleDateTimeSpan` ist null, d. h., dass für dieses Objekt kein Wert angegeben wurde. (Dies ist "null", in dem Sinne Datenbank mit"kein Wert" im Gegensatz zu C++ **NULL**.)  
  
    > [!CAUTION]
    >  Diese Funktion ist für Situationen, Erweiterte Programmierung. Diese Funktion wird die Daten in dieses Objekt nicht verändert. Es am häufigsten verwendet werden, legen Sie den Status auf `null` oder **ungültige**. Beachten Sie, dass der Zuweisungsoperator ( [Operator =](#eq)) und [SetDateTimeSpan](#setdatetimespan) sollten Sie den Status des Objekts basierend auf der Quelle Werte festlegen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities #22](../../atl-mfc-shared/codesnippet/cpp/coledatetimespan-class_13.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [COleDateTime-Klasse](../../atl-mfc-shared/reference/coledatetime-class.md)   
 [CTime-Klasse](../../atl-mfc-shared/reference/ctime-class.md)   
 [CTimeSpan-Klasse](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Freigegebene ATL-/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)



