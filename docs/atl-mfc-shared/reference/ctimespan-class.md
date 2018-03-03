---
title: CTimeSpan Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTimeSpan
- ATLTIME/ATL::CTimeSpan
- ATLTIME/ATL::CTimeSpan::CTimeSpan
- ATLTIME/ATL::CTimeSpan::Format
- ATLTIME/ATL::CTimeSpan::GetDays
- ATLTIME/ATL::CTimeSpan::GetHours
- ATLTIME/ATL::CTimeSpan::GetMinutes
- ATLTIME/ATL::CTimeSpan::GetSeconds
- ATLTIME/ATL::CTimeSpan::GetTimeSpan
- ATLTIME/ATL::CTimeSpan::GetTotalHours
- ATLTIME/ATL::CTimeSpan::GetTotalMinutes
- ATLTIME/ATL::CTimeSpan::GetTotalSeconds
- ATLTIME/ATL::CTimeSpan::Serialize64
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cedf05bd8f5af198569891b4d6d59610d5098eb6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ctimespan-class"></a>CTimeSpan-Klasse
Eine Zeitspanne, die als die Anzahl der Sekunden, in dem Zeitraum intern gespeichert werden.  
  
## <a name="syntax"></a>Syntax  
  
```
class CTimeSpan
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTimeSpan::CTimeSpan](#ctimespan)|Erstellt `CTimeSpan` Objekte auf verschiedene Weise.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTimeSpan::Format](#format)|Konvertiert eine `CTimeSpan` in eine formatierte Zeichenfolge.|  
|[CTimeSpan::GetDays](#getdays)|Gibt einen Wert, der die Anzahl der in dieser vollständige Tage darstellt `CTimeSpan`.|  
|[CTimeSpan::GetHours](#gethours)|Gibt einen Wert, der die Anzahl der Stunden in den aktuellen Tag (-23 bis 23) darstellt.|  
|[CTimeSpan::GetMinutes](#getminutes)|Gibt einen Wert, der die Anzahl der Minuten in der aktuellen Stunde (-59 bis 59) darstellt.|  
|[CTimeSpan::GetSeconds](#getseconds)|Gibt einen Wert, der die Anzahl der Sekunden in der aktuellen Minute (-59 bis 59) darstellt.|  
|[CTimeSpan::GetTimeSpan](#gettimespan)|Gibt den Wert der `CTimeSpan` Objekt.|  
|[CTimeSpan::GetTotalHours](#gettotalhours)|Gibt einen Wert, der die Gesamtzahl der vollständige Stunden in diesem `CTimeSpan`.|  
|[CTimeSpan::GetTotalMinutes](#gettotalminutes)|Gibt einen Wert, der die Gesamtzahl der in dieser vollständige Minuten darstellt `CTimeSpan`.|  
|[CTimeSpan::GetTotalSeconds](#gettotalseconds)|Gibt einen Wert, der die Gesamtzahl der vollständige Sekunden in diesem `CTimeSpan`.|  
|[CTimeSpan::Serialize64](#serialize64)|Serialisiert Daten zu oder von einem Archiv.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[Operator + -](#operator_add_-)|Fügt und subtrahiert `CTimeSpan` Objekte.|  
|[Operator += =](#operator_add_eq_-_eq)|Fügt und subtrahiert einen `CTimeSpan` -Objekts in und aus diesem `CTimeSpan`.|  
|[Operator == < usw.](#ctimespan_comparison_operators)|Vergleicht zwei relative Time-Werten.|  
  
## <a name="remarks"></a>Hinweise  
 `CTimeSpan`eine Basisklasse verfügt nicht über.  
  
 `CTimeSpan`Funktionen konvertieren Sekunden, um verschiedene Kombinationen von Tagen, Stunden, Minuten und Sekunden.  
  
 Die `CTimeSpan` Objekt befindet sich in einem **__time64_t** -Struktur, die 8 Bytes beträgt.  
  
 Eine Begleitklasse [CTime](../../atl-mfc-shared/reference/ctime-class.md), einer absoluten Zeitpunkt darstellt.  
  
 Die `CTime` und `CTimeSpan` Klassen sind nicht für die Ableitung ausgelegt. Da es keine virtuellen Funktionen, die Größe beider sind `CTime` und `CTimeSpan` Objekte ist genau 8 Bytes. Die meisten Memberfunktionen enthält Inlinekommentare.  
  
 Weitere Informationen zur Verwendung von `CTimeSpan`, finden Sie in den Artikeln [Datum und Uhrzeit](../../atl-mfc-shared/date-and-time.md), und [Uhrzeitverwaltung](../../c-runtime-library/time-management.md) in der *Run-Time Library Reference*.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atltime.h  
  
##  <a name="ctimespan_comparison_operators"></a>CTimeSpan Vergleichsoperatoren  
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
 Diese Operatoren vergleichen zwei relative Time-Werten. Diese zurückgeben **"true"** , wenn die Bedingung, andernfalls "true ist" **"false"**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#169](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_1.cpp)]  
  
##  <a name="ctimespan"></a>CTimeSpan::CTimeSpan  
 Erstellt `CTimeSpan` Objekte auf verschiedene Weise.  
  
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
 Ein `CTimeSpan` bereits vorhandenen Objekts ab.  
  
 `time`  
 Ein **__time64_t** Zeitwert, der die Anzahl der Sekunden, in dem Zeitraum wurde.  
  
 `lDays`, `nHours`, `nMins`, `nSecs`  
 Tage, Stunden, Minuten und Sekunden, bzw.  
  
### <a name="remarks"></a>Hinweise  
 Alle diese Konstruktoren erstellen ein neues `CTimeSpan` Objekt, mit dem angegebenen relativen initialisiert wurde. Jeder Konstruktor wird im folgenden beschrieben:  
  
- **CTimeSpan ();**  Erstellt eine nicht initialisierte `CTimeSpan` Objekt.  
  
- **CTimeSpan (const CTimeSpan &);**  Erstellt eine `CTimeSpan` Objekt von einem anderen `CTimeSpan` Wert.  
  
- **CTimeSpan (__time64_t);**  Erstellt eine `CTimeSpan` -Objekt aus einem **__time64_t** Typ.  
  
- **CTimeSpan (LONG**, **Int, Int, Int);** Erstellt eine `CTimeSpan` Objekt von Komponenten mit einzelnen Komponenten eingeschränkt, die den folgenden Bereichen:  
  
    |Komponente|Bereich|  
    |---------------|-----------|  
    |`lDays`|0-25.000 (ungefähr)|  
    |`nHours`|0-23|  
    |`nMins`|0-59|  
    |`nSecs`|0-59|  
  
 Beachten Sie, dass die Debugversion von der Microsoft Foundation Class-Bibliothek bestätigt wird, wenn eine oder mehrere der Tag Komponenten außerhalb des Bereichs liegt. Es liegt in Ihrer Verantwortung So überprüfen Sie die Argumente vor dem Aufruf.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#162](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_2.cpp)]  
  
##  <a name="format"></a>CTimeSpan::Format  
 Generiert eine formatierte Zeichenfolge, die dies entspricht `CTimeSpan`.  
  
```
CString Format(LPCSTR pFormat) const;
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nID) const;
```  
  
### <a name="parameters"></a>Parameter  
 `pFormat`, `pszFormat`  
 Eine Formatierungszeichenfolge ähnelt der `printf` Formatierungszeichenfolge. Formatierungscodes vorangestellt Prozentsatz ( `%`) anmelden, werden mit den entsprechenden ersetzt `CTimeSpan` Komponente. Andere Zeichen in der Formatzeichenfolge werden in der zurückgegebenen Zeichenfolge unverändert kopiert. Der Wert und die Bedeutung von Formatierungscodes für **Format** sind nachfolgend aufgeführt:  
  
- **%D** Tage in dieser insgesamt`CTimeSpan`  
  
- **%H** Stunden den heutigen Tag  
  
- **%M** Minuten in der aktuellen Stunde  
  
- **%S** Sekunden in der aktuellen Minute  
  
- **%%**Prozentzeichen  
  
 `nID`  
 Die ID der Zeichenfolge, die dieses Format bezeichnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` Objekt, das die formatierte Uhrzeit enthält.  
  
### <a name="remarks"></a>Hinweise  
 Die Debugversion der Bibliothek Formatierungscodes überprüft und bestätigt wird, wenn der Code nicht in der obigen Liste ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#163](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_3.cpp)]  
  
##  <a name="getdays"></a>CTimeSpan::GetDays  
 Gibt einen Wert, der die Anzahl der in dieser vollständige Tage darstellt `CTimeSpan`.  
  
```
LONGLONG GetDays() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Tage für vollständige 24-Stunden-Format in die Zeitspanne zurück. Dieser Wert möglicherweise negativ ist, wenn die Zeitspanne negativ ist.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, die Sommerzeit dazu `GetDays` potenziell überraschenden Ergebnis zurückgegeben. Beispielsweise wenn DST ist faktisch **GetDays** meldet die Anzahl der Tage zwischen dem 1. April und 1. Mai als 29 nicht 30, daran, dass ein Tag im April von einer Stunde gekürzt wird und daher nicht als vollständige Tag gezählt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#164](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_4.cpp)]  
  
##  <a name="gethours"></a>CTimeSpan::GetHours  
 Gibt einen Wert, der die Anzahl der Stunden in den aktuellen Tag (-23 bis 23) darstellt.  
  
```
LONG GetHours() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Stunden in den aktuellen Tag zurück. Der Bereich ist-23 bis 23.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#165](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_5.cpp)]  
  
##  <a name="getminutes"></a>CTimeSpan::GetMinutes  
 Gibt einen Wert, der die Anzahl der Minuten in der aktuellen Stunde (-59 bis 59) darstellt.  
  
```
LONG GetMinutes() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Minuten in der aktuellen Stunde zurück. Der Bereich ist-59 bis 59.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetHours](#gethours).  
  
##  <a name="getseconds"></a>CTimeSpan::GetSeconds  
 Gibt einen Wert, der die Anzahl der Sekunden in der aktuellen Minute (-59 bis 59) darstellt.  
  
```
LONG GetSeconds() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Sekunden in der aktuellen Minute zurück. Der Bereich ist-59 bis 59.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetHours](#gethours).  
  
##  <a name="gettimespan"></a>CTimeSpan::GetTimeSpan  
 Gibt den Wert der `CTimeSpan` Objekt.  
  
```
__ time64_t GetTimeSpan() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den aktuellen Wert von der `CTimeSpan` Objekt.  
  
##  <a name="gettotalhours"></a>CTimeSpan::GetTotalHours  
 Gibt einen Wert, der die Gesamtzahl der vollständige Stunden in diesem `CTimeSpan`.  
  
```
LONGLONG GetTotalHours() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Gesamtzahl der Stunden vollständige in diesem `CTimeSpan`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#166](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_6.cpp)]  
  
##  <a name="gettotalminutes"></a>CTimeSpan::GetTotalMinutes  
 Gibt einen Wert, der die Gesamtzahl der in dieser vollständige Minuten darstellt `CTimeSpan`.  
  
```
LONGLONG GetTotalMinutes() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Gesamtzahl der Minuten vollständige in diesem `CTimeSpan`.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetTotalHours](#gettotalhours).  
  
##  <a name="gettotalseconds"></a>CTimeSpan::GetTotalSeconds  
 Gibt einen Wert, der die Gesamtzahl der vollständige Sekunden in diesem `CTimeSpan`.  
  
```
LONGLONG GetTotalSeconds() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Gesamtanzahl der vollständige Sekunden in diesem `CTimeSpan`.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetTotalHours](#gettotalhours).  
  
##  <a name="operator_add_-"></a>CTimeSpan::operator +, -  
 Fügt und subtrahiert `CTimeSpan` Objekte.  
  
```
CTimeSpan operator+(CTimeSpan span) const throw();
CTimeSpan operator-(CTimeSpan span) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Der Wert, der zum Hinzufügen der `CTimeSpan` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CTimeSpan` Objekt, das das Ergebnis des Vorgangs darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Diese beiden Operatoren ermöglichen es Ihnen, Addition und Subtraktion `CTimeSpan` Objekte in und aus anderen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#167](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_7.cpp)]  
  
##  <a name="operator_add_eq_-_eq"></a>CTimeSpan::operator +=, =  
 Fügt und subtrahiert einen `CTimeSpan` -Objekts in und aus diesem `CTimeSpan`.  
  
```
CTimeSpan& operator+=(CTimeSpan span) throw();
CTimeSpan& operator-=(CTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Der Wert, der zum Hinzufügen der `CTimeSpan` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktualisierte `CTimeSpan` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Operatoren ermöglichen es Ihnen, Addition und Subtraktion ein `CTimeSpan` -Objekts in und aus diesem `CTimeSpan`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#168](../../atl-mfc-shared/codesnippet/cpp/ctimespan-class_8.cpp)]  
  
##  <a name="serialize64"></a>CTimeSpan::Serialize64  
  
> [!NOTE]
>  Diese Methode ist nur in MFC-Projekten verfügbar.  
  
 Serialisiert die Membervariable zu oder von einem Archiv zugeordneten Daten.  
  
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
 [Freigegebene ATL-/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)


