---
title: Mit der CTimeSpan-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CTimeSpan
- CTimeSpan
- timespan
- ATL::CTimeSpan
dev_langs:
- C++
helpviewer_keywords:
- elapsed time, CTimeSpan object
- timespan
- time span
- CTimeSpan class
- shared classes, CTimeSpan
- time, elapsed
ms.assetid: ee1e42f6-1839-477a-8435-fb26ad475140
caps.latest.revision: 17
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
ms.openlocfilehash: 5c76411f6c1302d406b07cc79d9c544e3ad8c43b
ms.lasthandoff: 02/24/2017

---
# <a name="ctimespan-class"></a>CTimeSpan-Klasse
Eine Zeitspanne, die intern als die Anzahl der Sekunden in dem Zeitraum gespeichert ist.  
  
## <a name="syntax"></a>Syntax  
  
```
class CTimeSpan
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTimeSpan::CTimeSpan](#ctimespan)|Erstellt `CTimeSpan` Objekte auf unterschiedliche Weise.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTimeSpan::Format](#format)|Konvertiert ein `CTimeSpan` in eine formatierte Zeichenfolge.|  
|[CTimeSpan::GetDays](#getdays)|Gibt einen Wert, der die Anzahl der vollständigen Tage in diesem `CTimeSpan`.|  
|[CTimeSpan::GetHours](#gethours)|Gibt einen Wert, der die Anzahl der Stunden in den aktuellen Tag (bis 23 -23) darstellt.|  
|[CTimeSpan::GetMinutes](#getminutes)|Gibt einen Wert, der die Anzahl der Minuten für die aktuelle Stunde (-59 bis 59) darstellt.|  
|[CTimeSpan::GetSeconds](#getseconds)|Gibt einen Wert, der die Anzahl der Sekunden in der aktuellen Minute (-59 bis 59) darstellt.|  
|[CTimeSpan::GetTimeSpan](#gettimespan)|Gibt den Wert der `CTimeSpan` Objekt.|  
|[CTimeSpan::GetTotalHours](#gettotalhours)|Gibt einen Wert, der die Gesamtzahl der vollständige Stunden in diesem `CTimeSpan`.|  
|[CTimeSpan::GetTotalMinutes](#gettotalminutes)|Gibt einen Wert, der die Gesamtanzahl der vollständige Minuten in diesem `CTimeSpan`.|  
|[CTimeSpan::GetTotalSeconds](#gettotalseconds)|Gibt einen Wert, der die Gesamtzahl der vollständige Sekunden in diesem `CTimeSpan`.|  
|[CTimeSpan::Serialize64](#serialize64)|Serialisiert Daten an oder von einem Archiv.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[Operator + -](#operator_add_-)|Fügt und subtrahiert `CTimeSpan` Objekte.|  
|[Operator += – =](#operator_add_eq_-_eq)|Fügt und subtrahiert einen `CTimeSpan` -Objekts in und aus diesem `CTimeSpan`.|  
|[Operator ==<>](#ctimespan_comparison_operators)|Vergleicht zwei Werte für relative Zeit.|  
  
## <a name="remarks"></a>Hinweise  
 `CTimeSpan`eine Basisklasse keinen.  
  
 `CTimeSpan`Funktionen konvertieren Sekunden, um verschiedene Kombinationen von Tagen, Stunden, Minuten und Sekunden.  
  
 Die `CTimeSpan` Objekt befindet sich in einem **__time64_t** -Struktur, die 8 Bytes ist.  
  
 Eine Begleitklasse [CTime](../../atl-mfc-shared/reference/ctime-class.md), eine absolute Zeit darstellt.  
  
 Die `CTime` und `CTimeSpan` Klassen sind nicht für die Ableitung konzipiert. Da keine virtuellen, die Größe beider Funktionen `CTime` und `CTimeSpan` Objekte genau 8 Bytes ist. Die meisten Member-Funktionen werden Inline.  
  
 Weitere Informationen zur Verwendung von `CTimeSpan`, finden Sie in den Artikeln [Datum und Uhrzeit](../../atl-mfc-shared/date-and-time.md), und [Zeitmanagement](../../c-runtime-library/time-management.md) in der *Run-Time Library Reference*.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atltime.h  
  
##  <a name="a-namectimespancomparisonoperatorsa--ctimespan-comparison-operators"></a><a name="ctimespan_comparison_operators"></a>CTimeSpan Vergleichsoperatoren  
 Vergleichsoperatoren.  
  
```
bool operator==(CTimeSpan span) const throw();
bool operator!=(CTimeSpan span) const throw();
bool operator<(CTimeSpan span) const throw();
bool operator>(CTimeSpan span) const throw();
bool operator<=(CTimeSpan span) const throw();
bool operator>=(CTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
  
 Das zu vergleichende Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Operatoren vergleichen zwei relative Time-Werte. Diese zurückgeben **true** Wenn die Bedingung true ist andernfalls **false**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#169;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_1.cpp)]  
  
##  <a name="a-namectimespana--ctimespanctimespan"></a><a name="ctimespan"></a>CTimeSpan::CTimeSpan  
 Erstellt `CTimeSpan` Objekte auf unterschiedliche Weise.  
  
```
CTimeSpan() throw();
CTimeSpan(__time64_t time) throw();

CTimeSpan(  
 LONG lDays,
 int nHours,
 int nMins,
 int nSecs) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *timeSpanSrc*  
 Ein `CTimeSpan` -Objekt, das bereits vorhanden ist.  
  
 `time`  
 Ein **__time64_t** Zeitwert, der die Anzahl der Sekunden in dem Zeitraum angibt. In Visual C++-Versionen 6.0 und früher `time` wurde ein Wert von `time_t`. Visual C++ .NET oder später im Hintergrund konvertiert eine `time_t` Parameter **__time64_t**.  
  
 `lDays`, `nHours`, `nMins`, `nSecs`  
 Tage, Stunden, Minuten und Sekunden bzw..  
  
### <a name="remarks"></a>Hinweise  
 Alle diese Konstruktoren erstellen ein neues `CTimeSpan` -Objekt mit der angegebenen relativen Zeit initialisiert. Jeder Konstruktor wird im folgenden beschrieben:  
  
- **CTimeSpan (); ** Erstellt ein nicht initialisiertes `CTimeSpan` Objekt.  
  
- **CTimeSpan (const CTimeSpan &); ** Erstellt eine `CTimeSpan` -Objekt von einem anderen `CTimeSpan` Wert.  
  
- **CTimeSpan (__time64_t); ** Erstellt eine `CTimeSpan` -Objekt aus einer **__time64_t** Typ.  
  
- **CTimeSpan (lange**, **Int, Int, Int);** Erstellt ein `CTimeSpan` Objekt von Komponenten mit den einzelnen Komponenten beschränkt, die den folgenden Bereichen:  
  
    |Komponente|Bereich|  
    |---------------|-----------|  
    |`lDays`|0 –&25;.000 (ungefähr)|  
    |`nHours`|0–23|  
    |`nMins`|0–59|  
    |`nSecs`|0–59|  
  
 Beachten Sie, dass die Version der Microsoft Foundation Class-Bibliothek bestätigt werden, wenn eine oder mehrere Komponenten Tageszeit außerhalb des Bereichs. Es ist Ihre Aufgabe so überprüfen Sie die Argumente vor dem Aufruf.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#162;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_2.cpp)]  
  
##  <a name="a-nameformata--ctimespanformat"></a><a name="format"></a>CTimeSpan::Format  
 Generiert eine formatierte Zeichenfolge, die dies entspricht `CTimeSpan`.  
  
```
CString Format(LPCSTR pFormat) const;
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nID) const;
```  
  
### <a name="parameters"></a>Parameter  
 `pFormat`, `pszFormat`  
 Eine Formatierungszeichenfolge ähnelt der `printf` Formatierungszeichenfolge. Formatierungscodes Prozentsatz vorangestellt ( `%`) anmelden, werden mit den entsprechenden ersetzt `CTimeSpan` Komponente. Andere Zeichen in der Formatierungszeichenfolge werden in der zurückgegebenen Zeichenfolge unverändert kopiert. Der Wert und die Bedeutung der Formatierungscodes für **Format** sind nachfolgend aufgeführt:  
  
- **%D** Tage in dieser insgesamt`CTimeSpan`  
  
- **"% H"** Stunden in den aktuellen Tag  
  
- **"% M"** in der aktuellen Stunde Minuten  
  
- **%S** Sekunden in der aktuellen Minute  
  
- **%%**Prozentzeichen  
  
 `nID`  
 Die ID der Zeichenfolge, die dieses Format identifiziert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` -Objekt, das die formatierte enthält.  
  
### <a name="remarks"></a>Hinweise  
 Die Debugversion der Bibliothek Formatierungscodes überprüft und bestätigt wird, wenn der Code nicht in der obigen Liste ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#163;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_3.cpp)]  
  
##  <a name="a-namegetdaysa--ctimespangetdays"></a><a name="getdays"></a>CTimeSpan::GetDays  
 Gibt einen Wert, der die Anzahl der vollständigen Tage in diesem `CTimeSpan`.  
  
```
LONGLONG GetDays() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der vollständigen 24-Stunden-Tage in der Zeitspanne zurück. Dieser Wert möglicherweise negativ ist, wenn die Zeitspanne negativ ist.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, die Sommerzeit verursachen können `GetDays` potenziell überraschenden Ergebnis zurückgegeben. Zum Beispiel wenn DST gültig ist, **GetDays** meldet die Anzahl der Tage zwischen dem 1. April und Mai 1 als 29 nicht 30, da ein Tag im April von einer Stunde gekürzt wird und wird daher nicht als vollständige Tag angerechnet.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#164;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_4.cpp)]  
  
##  <a name="a-namegethoursa--ctimespangethours"></a><a name="gethours"></a>CTimeSpan::GetHours  
 Gibt einen Wert, der die Anzahl der Stunden in den aktuellen Tag (bis 23 -23) darstellt.  
  
```
LONG GetHours() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Stunden in den aktuellen Tag zurück. Der Bereich ist -23 bis 23.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#165;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_5.cpp)]  
  
##  <a name="a-namegetminutesa--ctimespangetminutes"></a><a name="getminutes"></a>CTimeSpan::GetMinutes  
 Gibt einen Wert, der die Anzahl der Minuten für die aktuelle Stunde (-59 bis 59) darstellt.  
  
```
LONG GetMinutes() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Minuten in die aktuelle Stunde zurück. Der Bereich ist -59 bis 59.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetHours](#gethours).  
  
##  <a name="a-namegetsecondsa--ctimespangetseconds"></a><a name="getseconds"></a>CTimeSpan::GetSeconds  
 Gibt einen Wert, der die Anzahl der Sekunden in der aktuellen Minute (-59 bis 59) darstellt.  
  
```
LONG GetSeconds() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Sekunden in der aktuellen Minute zurück. Der Bereich ist -59 bis 59.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetHours](#gethours).  
  
##  <a name="a-namegettimespana--ctimespangettimespan"></a><a name="gettimespan"></a>CTimeSpan::GetTimeSpan  
 Gibt den Wert der `CTimeSpan` Objekt.  
  
```
__ time64_t GetTimeSpan() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den aktuellen Wert von der `CTimeSpan` Objekt.  
  
##  <a name="a-namegettotalhoursa--ctimespangettotalhours"></a><a name="gettotalhours"></a>CTimeSpan::GetTotalHours  
 Gibt einen Wert, der die Gesamtzahl der vollständige Stunden in diesem `CTimeSpan`.  
  
```
LONGLONG GetTotalHours() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Gesamtzahl der Stunden vollständig in dieser `CTimeSpan`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#166;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_6.cpp)]  
  
##  <a name="a-namegettotalminutesa--ctimespangettotalminutes"></a><a name="gettotalminutes"></a>CTimeSpan::GetTotalMinutes  
 Gibt einen Wert, der die Gesamtanzahl der vollständige Minuten in diesem `CTimeSpan`.  
  
```
LONGLONG GetTotalMinutes() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Gesamtanzahl der Minuten abgeschlossen in dieser `CTimeSpan`.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetTotalHours](#gettotalhours).  
  
##  <a name="a-namegettotalsecondsa--ctimespangettotalseconds"></a><a name="gettotalseconds"></a>CTimeSpan::GetTotalSeconds  
 Gibt einen Wert, der die Gesamtzahl der vollständige Sekunden in diesem `CTimeSpan`.  
  
```
LONGLONG GetTotalSeconds() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Gesamtanzahl der vollständige Sekunden in diesem `CTimeSpan`.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetTotalHours](#gettotalhours).  
  
##  <a name="a-nameoperatoradd-a--ctimespanoperator---"></a><a name="operator_add_-"></a>CTimeSpan::operator +, -  
 Fügt und subtrahiert `CTimeSpan` Objekte.  
  
```
CTimeSpan operator+(CTimeSpan span) const throw();
CTimeSpan operator-(CTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Der hinzuzufügende Wert der `CTimeSpan` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CTimeSpan` Objekt, das das Ergebnis des Vorgangs darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Diese beiden Operatoren ermöglichen es Ihnen, Addition und Subtraktion `CTimeSpan` Objekte von und zu anderen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#167;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_7.cpp)]  
  
##  <a name="a-nameoperatoraddeq-eqa--ctimespanoperator---"></a><a name="operator_add_eq_-_eq"></a>CTimeSpan::operator +=, =  
 Fügt und subtrahiert einen `CTimeSpan` -Objekts in und aus diesem `CTimeSpan`.  
  
```
CTimeSpan& operator+=(CTimeSpan span) throw();
CTimeSpan& operator-=(CTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Der hinzuzufügende Wert der `CTimeSpan` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktualisierte `CTimeSpan` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Operatoren ermöglichen es Ihnen, Addition und Subtraktion ein `CTimeSpan` -Objekts in und aus diesem `CTimeSpan`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#168;](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_8.cpp)]  
  
##  <a name="a-nameserialize64a--ctimespanserialize64"></a><a name="serialize64"></a>CTimeSpan::Serialize64  
  
> [!NOTE]
>  Diese Methode ist nur in MFC-Projekten verfügbar.  
  
 Serialisiert die Membervariable auf oder aus einem Archiv zugeordneten Daten.  
  
```
CArchive& Serialize64(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
 `ar`  
 Die `CArchive` -Objekt, das Sie aktualisieren möchten.  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktualisierte `CArchive` Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [asctime, _wasctime](../../c-runtime-library/reference/asctime-wasctime.md)   
 [_ftime, _ftime32, _ftime64](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [localtime, _localtime32, _localtime64](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [ATL/MFC-freigegeben Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)



