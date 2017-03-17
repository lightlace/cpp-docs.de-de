---
title: CTime Class | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTime
- ATLTIME/ATL::CTime
- ATLTIME/ATL::CTime::CTime
- ATLTIME/ATL::CTime::Format
- ATLTIME/ATL::CTime::FormatGmt
- ATLTIME/ATL::CTime::GetAsDBTIMESTAMP
- ATLTIME/ATL::CTime::GetAsSystemTime
- ATLTIME/ATL::CTime::GetCurrentTime
- ATLTIME/ATL::CTime::GetDay
- ATLTIME/ATL::CTime::GetDayOfWeek
- ATLTIME/ATL::CTime::GetGmtTm
- ATLTIME/ATL::CTime::GetHour
- ATLTIME/ATL::CTime::GetLocalTm
- ATLTIME/ATL::CTime::GetMinute
- ATLTIME/ATL::CTime::GetMonth
- ATLTIME/ATL::CTime::GetSecond
- ATLTIME/ATL::CTime::GetTime
- ATLTIME/ATL::CTime::GetYear
- ATLTIME/ATL::CTime::Serialize64
dev_langs:
- C++
helpviewer_keywords:
- CTime class
- shared classes, CTime
ms.assetid: 0a299544-485b-48dc-9d3c-fdc30f57d612
caps.latest.revision: 30
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
ms.sourcegitcommit: 1a00023e4d3e31ddb6381e90a50231449b1de18d
ms.openlocfilehash: 56b8b5c3574a7a53a4e259412b1b1326973bcac9
ms.lasthandoff: 02/28/2017

---
# <a name="ctime-class"></a>CTime-Klasse
Stellt ein Datum und Uhrzeit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CTime  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTime:: CTime](#ctime)|Erstellt `CTime` Objekte auf unterschiedliche Weise.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTime::Format](#format)|Konvertiert ein `CTime` Objekt in eine formatierte Zeichenfolge – basierend auf der lokalen Zeitzone.|  
|[CTime::FormatGmt](#formatgmt)|Konvertiert ein `CTime` Objekt in eine formatierte Zeichenfolge – basierend auf UTC.|  
|[CTime::GetAsDBTIMESTAMP](#getasdbtimestamp)|Konvertiert die in gespeicherten Informationen dem `CTime` Objekt in eine Win32-kompatibles DBTIMESTAMP-Struktur.|  
|[CTime::GetAsSystemTime](#getassystemtime)|Konvertiert die Informationen gespeichert, die der `CTime` -Objekt in ein Win32-kompatibles [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur.|  
|[CTime:: GetCurrentTime](#getcurrenttime)|Erstellt ein `CTime` -Objekt, das die aktuelle Uhrzeit (statische Memberfunktion) darstellt.|  
|[CTime::GetDay](#getday)|Gibt die dargestellten Tag durch die `CTime` Objekt.|  
|[CTime::GetDayOfWeek](#getdayofweek)|Gibt den Tag des Wochentags, dargestellt durch die `CTime` Objekt.|  
|[CTime::GetGmtTm](#getgmttm)|Unterteilt ein `CTime` Objekt in Komponenten – basierend auf UTC.|  
|[CTime::GetHour](#gethour)|Gibt die Stunde, dargestellt durch die `CTime` Objekt.|  
|[CTime::GetLocalTm](#getlocaltm)|Unterteilt ein `CTime` Objekt in Komponenten – basierend auf der lokalen Zeitzone.|  
|[CTime::GetMinute](#getminute)|Gibt die Minute, dargestellt durch die `CTime` Objekt.|  
|[CTime::GetMonth](#getmonth)|Gibt die Monats, dargestellt durch die `CTime` Objekt.|  
|[CTime::GetSecond](#getsecond)|Gibt das zweite, dargestellt durch die `CTime` Objekt.|  
|[CTime::GetTime](#gettime)|Gibt eine **__time64_t** -Wert für den angegebenen `CTime` Objekt.|  
|[CTime::GetYear](#getyear)|Gibt das Jahr, dargestellt durch die `CTime` Objekt.|  
|[CTime::Serialize64](#serialize64)|Serialisiert Daten an oder von einem Archiv.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[Operator + -](#operator_add_-)|Diese Operatoren addieren und subtrahieren `CTimeSpan` und `CTime` Objekte.|  
|[Operator +=, =](#operator_add_eq_-_eq)|Diese Operatoren Addition und Subtraktion ein `CTimeSpan` -Objekts in und aus diesem `CTime` Objekt.|  
|[Operator =](#operator_eq)|Der Zuweisungsoperator.|  
|[Operator ==,< ,="">](#ctime_comparison_operators)|Vergleichsoperatoren.|  
  
## <a name="remarks"></a>Hinweise  
 `CTime`eine Basisklasse keinen.  
  
 `CTime`Werte basieren auf koordinierte Weltzeit (UTC), die koordinierte Weltzeit (Greenwich Mean Time, GMT) entspricht. Finden Sie unter [Uhrzeitverwaltung](../../c-runtime-library/time-management.md) Informationen darüber, wie die Zeitzone bestimmt wird.  
  
 Beim Erstellen einer `CTime` -Objekts der `nDST` -Parameter auf 0, um anzugeben, dass die Normalzeit gilt, oder auf einen Wert größer als 0 weist darauf hin, Sommerzeit gilt oder auf einen Wert kleiner als 0 (null), damit die C-Laufzeitbibliothek Code Compute, ob Normalzeit oder Sommerzeit gilt. `tm_isdst` ist ein Pflichtfeld. Wenn nicht festgelegt ist, dessen Wert nicht definiert ist und der Rückgabewert von [Mktime](../../c-runtime-library/reference/mktime-mktime32-mktime64.md) ist unvorhersehbar. Wenn `timeptr` verweist auf eine tm-Struktur, die von einem vorherigen Aufruf zurückgegebene [Asctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md), [_gmtime_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md), oder [Localtime_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md), `tm_isdst` Feld enthält den richtigen Wert.  
  
 Eine Begleitklasse [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md), stellt ein Zeitintervall dar.  
  
 Die `CTime` und `CTimeSpan` Klassen sind nicht für die Ableitung konzipiert. Da keine virtuellen, die Größe des Funktionen `CTime` und `CTimeSpan` Objekte genau 8 Bytes ist. Die meisten Member-Funktionen werden Inline.  
  
> [!NOTE]
>  Die oberen Frist ist 12/31/3000. Der untere Grenzwert ist 1/1/1970 12:00:00 Uhr GMT.  
  
 Weitere Informationen zur Verwendung `CTime`, finden Sie in den Artikeln [Datum und Uhrzeit](../../atl-mfc-shared/date-and-time.md), und [Uhrzeitverwaltung](../../c-runtime-library/time-management.md) in der Run-Time Library Reference.  
  
> [!NOTE]
>  Die `CTime` Struktur, die von MFC 7.1 in MFC 8.0 geändert. Wenn Sie Serialisieren einer `CTime` -Struktur unter Verwendung der `operator <<` unter MFC 8.0 oder höher, die resultierende Datei nicht gelesen werden unter älteren Versionen von MFC.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atltime.h  
  
##  <a name="ctime_comparison_operators"></a>CTime-Vergleichsoperatoren  
 Vergleichsoperatoren.  
  
```  
bool operator==(CTime time) const throw(); 
bool operator!=(CTime time) const throw();
bool operator<(CTime time) const throw();
bool operator>(CTime time) const throw();
bool operator<=(CTime time) const throw();
bool operator>=(CTime time) const throw(); 
```  
  
### <a name="parameters"></a>Parameter  
 `time`  
 Das zu vergleichende `CTime`-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Operatoren vergleichen zwei absolute Zeiten und zurückgeben **true** Wenn die Bedingung true ist andernfalls **false**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#161;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_1.cpp)]  
  
##  <a name="ctime"></a>CTime:: CTime  
 Erstellt ein neues `CTime` -Objekt mit der angegebenen Zeit initialisiert.  
  
```  
CTime() throw(); 
CTime(__time64_t time) throw();
CTime(int nYear, int nMonth, int nDay,
      int nHour, int nMin, int nSec, int nDST = -1);
CTime(WORD wDosDate, WORD wDosTime, int nDST = -1);
CTime(const SYSTEMTIME& st, int nDST = - 1) throw();
CTime(const FILETIME& ft, int nDST = - 1);
CTime(const DBTIMESTAMP& dbts,int nDST = -1) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `timeSrc`  
 Gibt ein `CTime` -Objekt, das bereits vorhanden ist.  
  
 `time`  
 Ein **__time64_t** Zeitwert, der die Anzahl der Sekunden an, nach dem 1. Januar 1970 UTC angibt. Beachten Sie, dass diese in die lokale Zeit angepasst wird. Angenommen, Sie befinden sich in New York und erstellen eine `CTime` -Objekt durch Übergeben eines Parameters 0 [CTime::GetMonth](#getmonth) 12 zurück.  
  
 In Visual C++-Versionen 6.0 und früher `time` wurde ein Wert von `time_t`. Visual C++ .NET und höher konvertiert eine `time_t` Parameter **__time64_t**.  
  
 `nYear`, `nMonth`, `nDay`, `nHour`, `nMin`, `nSec`  
 Zeigt die Werte für Datum und Uhrzeit in die neue kopiert werden `CTime` Objekt.  
  
 `nDST`  
 Gibt an, ob die Sommerzeit wirksam ist. Dabei kann es sich um einen von drei Werten haben:  
  
- `nDST`0Standard Zeit ist gültig.  
  
- `nDST`Setzen Sie auf einen Wert größer als 0Daylight, Zeit aktiviert ist.  
  
- `nDST`Legen Sie auf einen Wert kleiner als 0The Standard. Automatisch berechnet, ob Normalzeit oder Sommerzeit gilt.  
  
 `wDosDate`, `wDosTime`  
 MS-DOS-Datum und Uhrzeit-Werte in einen Datum/Uhrzeit-Wert konvertiert und in die neue kopiert `CTime` Objekt.  
  
 `st`  
 Ein [SYSTEMTIME](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/d6609fff-1931-4818-8a26-f042630af0b0/locales/en-us) Struktur in einen Datum/Uhrzeit-Wert konvertiert und in die neue kopiert `CTime` Objekt.  
  
 `ft`  
 Ein [FILETIME](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/979ce746-dc17-4147-89f8-41d05c5fcc5f/locales/en-us) Struktur in einen Datum/Uhrzeit-Wert konvertiert und in die neue kopiert `CTime` Objekt.  
  
 DBTS  
 Ein Verweis auf eine DBTIMESTAMP-Struktur, die mit der aktuellen Ortszeit.  
  
### <a name="remarks"></a>Hinweise  
 Jeder Konstruktor wird im folgenden beschrieben:  
  
- **CTime(); ** Erstellt ein nicht initialisiertes `CTime` Objekt. Mit diesem Konstruktor können Sie definieren `CTime` -Objekt des Arrays. Sie sollten solche Arrays mit welchen Zeiten vor der Verwendung initialisieren.  
  
- **CTime (const CTime &); ** Erstellt eine `CTime` -Objekt von einem anderen `CTime` Wert.  
  
- **CTime (__time64_t); ** Erstellt eine `CTime` -Objekt aus einer **__time64_t** Typ. Dieser Konstruktor erwartet eine UTC-Zeit und das Ergebnis in die lokale Zeit konvertiert, vor dem Speichern des Ergebnisses.  
  
- **CTime (Int, Int,...) ** Erstellt ein `CTime` Objekt Ortszeit Komponenten mit den einzelnen Komponenten beschränkt, die den folgenden Bereichen:  
  
    |Komponente|Bereich|  
    |---------------|-----------|  
    |`nYear`|1970–3000|  
    |`nMonth`|1–12|  
    |`nDay`|1–31|  
    |`nHour`|0-23|  
    |`nMin`|0-59|  
    |`nSec`|0-59|  
  
     Dieser Konstruktor wird die entsprechende Konvertierung in UTC. Die Version der Microsoft Foundation Class-Bibliothek bestätigt werden, wenn eine oder mehrere Zeitkomponenten liegt außerhalb des Bereichs. Sie müssen die Argumente vor dem Aufruf überprüfen. Dieser Konstruktor erwartet, dass eine lokale Zeit.  
  
- **CTime (WORD, WORD); ** Erstellt ein `CTime` Objekt aus den angegebenen Werten von MS-DOS-Datum und Uhrzeit. Dieser Konstruktor erwartet, dass eine lokale Zeit.  
  
- **CTime (const SYSTEMTIME &); ** Erstellt eine `CTime` -Objekt aus einer `SYSTEMTIME` Struktur. Dieser Konstruktor erwartet, dass eine lokale Zeit.  
  
- **CTime (const FILETIME &); ** Erstellt eine `CTime` -Objekt aus einer `FILETIME` Struktur. Verwenden Sie wahrscheinlich nicht `CTime FILETIME` -Initialisierung direkt. Bei Verwendung einer `CFile` Objekt um eine Datei zu manipulieren `CFile::GetStatus` Ruft den Zeitstempel der Datei für Sie durch eine `CTime` Objekt initialisiert wird, mit einer `FILETIME` Struktur. Dieser Konstruktor wird als Zeit basierend auf UTC-Zeit und konvertiert automatisch den Wert in die lokale Zeit vor dem Speichern des Ergebnisses.  
  
    > [!NOTE]
    >  Der Konstruktor mit **DBTIMESTAMP** Parameter ist nur verfügbar, wenn OLEDB.h enthalten ist.  
  
 Weitere Informationen finden Sie unter der [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) und [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Siehe auch die [MS-DOS-Datum und Uhrzeit](http://msdn.microsoft.com/library/windows/desktop/ms724503) Eintrag in der [!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#148;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_2.cpp)]  
  
##  <a name="format"></a>CTime::Format  
 Rufen Sie diese Memberfunktion, um eine formatierte Darstellung des DateTime-Werts zu erstellen.  
  
```  
CString Format(LPCTSTR pszFormat) const; 
CString Format(UINT nFormatID) const; 
```  
  
### <a name="parameters"></a>Parameter  
 `pszFormat`  
 Eine Formatierungszeichenfolge ähnelt der `printf` Formatierungszeichenfolge. Formatierungscodes Prozentsatz vorangestellt ( `%`) anmelden, werden mit den entsprechenden ersetzt `CTime` Komponente. Andere Zeichen in der Formatierungszeichenfolge werden in der zurückgegebenen Zeichenfolge unverändert kopiert. Finden Sie die Laufzeitfunktion [Strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) eine Liste der Formatierungscodes.  
  
 `nFormatID`  
 Die ID der Zeichenfolge, die dieses Format identifiziert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , die die formatierte Zeit enthält.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Status dieser `CTime` Objekt ist null, der Rückgabewert ist eine leere Zeichenfolge.  
  
 Diese Methode löst eine Ausnahme aus, wenn es sich bei der zu formatierenden Datum-Uhrzeit-Wert nicht im Bereich von Mitternacht, 1. Januar 1970 bis 31. Dezember 3000 ist koordinierte Weltzeit (UTC).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#149;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_3.cpp)]  
  
##  <a name="formatgmt"></a>CTime::FormatGmt  
 Generiert eine formatierte Zeichenfolge, die dies entspricht `CTime` Objekt.  
  
```  
CString FormatGmt(LPCTSTR pszFormat) const; 
CString FormatGmt(UINT nFormatID) const; 
```  
  
### <a name="parameters"></a>Parameter  
 `pszFormat`  
 Gibt eine-Formatierungszeichenfolge ähnelt der `printf` Formatierungszeichenfolge. Finden Sie die Laufzeitfunktion [Strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) Details.  
  
 `nFormatID`  
 Die ID der Zeichenfolge, die dieses Format identifiziert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , die die formatierte Zeit enthält.  
  
### <a name="remarks"></a>Hinweise  
 Der Zeitwert wird nicht konvertiert und entspricht somit UTC.  
  
 Diese Methode löst eine Ausnahme aus, wenn es sich bei der zu formatierenden Datum-Uhrzeit-Wert nicht im Bereich von Mitternacht, 1. Januar 1970 bis 31. Dezember 3000 ist koordinierte Weltzeit (UTC).  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CTime::Format](#format).  
  
##  <a name="getasdbtimestamp"></a>CTime::GetAsDBTIMESTAMP  
 Rufen Sie diese Memberfunktion konvertiert die Informationen gespeichert, die der `CTime` Objekt in eine Win32-kompatiblen DBTIMESTAMP-Struktur.  
  
```  
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `dbts`  
 Ein Verweis auf eine DBTIMESTAMP-Struktur, die mit der aktuellen Ortszeit.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Speichert die resultierende Uhrzeit in der referenzierten `dbts`-Struktur. Die **DBTIMESTAMP** -Datenstruktur, die von dieser Funktion initialisiert haben die **Bruch** Member auf&0; (null) festgelegt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#150;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_4.cpp)]  
  
##  <a name="getassystemtime"></a>CTime::GetAsSystemTime  
 Rufen Sie diese Memberfunktion konvertiert die Informationen gespeichert, die der `CTime` -Objekt, einem Win32-kompatiblen [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur.  
  
```  
bool GetAsSystemTime(SYSTEMTIME& st) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 *timeDest*  
 Ein Verweis auf eine [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) -Struktur, die den konvertierte Datums-/Uhrzeitwert von enthält die `CTime` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn erfolgreich; andernfalls False.  
  
### <a name="remarks"></a>Hinweise  
 `GetAsSystemTime`Speichert die resultierende Zeit in der referenzierten *TimeDest* Struktur. Die `SYSTEMTIME` -Datenstruktur, die von dieser Funktion initialisiert haben die **wMilliseconds** Element auf&0; (null) gesetzt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#151;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_5.cpp)]  
  
##  <a name="getcurrenttime"></a>CTime:: GetCurrentTime  
 Gibt ein `CTime` -Objekt, das die aktuelle Uhrzeit darstellt.  
  
```  
static CTime WINAPI GetCurrentTime() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt das aktuelle Systemdatum und die Uhrzeit in Coordinated Universal Time (UTC) zurück.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#152;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_6.cpp)]  
  
##  <a name="getday"></a>CTime::GetDay  
 Gibt die dargestellten Tag durch die `CTime` Objekt.  
  
```  
int GetDay() const throw(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Tag des Monats, basierend auf der lokalen Zeit, im Bereich von 1 bis 31 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft `GetLocalTm`, einen internen, statisch zugewiesenen Puffer verwendet. Die Daten in diesem Puffer werden aufgrund von Aufrufen an andere überschrieben `CTime` Memberfunktionen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#153;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_7.cpp)]  
  
##  <a name="getdayofweek"></a>CTime::GetDayOfWeek  
 Gibt den Tag des Wochentags, dargestellt durch die `CTime` Objekt.  
  
```  
int GetDayOfWeek() const throw(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Tag der Woche basierend auf der Ortszeit zurück. 1 = Sonntag 2 = Montag, 7 = Samstag.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft `GetLocalTm`, die statisch eine interne verwendet zugeordneten Puffer. Die Daten in diesem Puffer werden aufgrund von Aufrufen an andere überschrieben `CTime` Memberfunktionen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#154;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_8.cpp)]  
  
##  <a name="getgmttm"></a>CTime::GetGmtTm  
 Ruft eine **Struct tm** , enthält eine Aufgliederung der Zeit, die in diesem enthaltenen `CTime` Objekt.  
  
```  
struct tm* GetGmtTm(struct tm* ptm) const; 
```  
  
### <a name="parameters"></a>Parameter  
 `ptm`  
 Zeigt auf einen Puffer, der die Zeitdaten empfängt. Wenn dieser Zeiger ist **NULL**, wird eine Ausnahme ausgelöst.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine ausgefüllt **Struct tm** wie in der Includedatei Zeit definiert. H. Finden Sie unter [Gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) für das Strukturlayout.  
  
### <a name="remarks"></a>Hinweise  
 `GetGmtTm`Gibt die UTC zurück.  
  
 `ptm` darf nicht `NULL` sein. Wenn Sie das alte Verhalten, in dem möchten `ptm` möglicherweise `NULL` um anzugeben, dass ein interner, statisch zugewiesene Puffer verwendet werden soll, dann heben Sie die Definition `_SECURE_ATL`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#155;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_9.cpp)]  
  
##  <a name="gethour"></a>CTime::GetHour  
 Gibt die Stunde, dargestellt durch die `CTime` Objekt.  
  
```  
int GetHour() const throw(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Stunde, basierend auf der lokalen Zeit, im Bereich von 0 bis 23.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft `GetLocalTm`, die statisch eine interne verwendet zugeordneten Puffer. Die Daten in diesem Puffer werden aufgrund von Aufrufen an andere überschrieben `CTime` Memberfunktionen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#156;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_10.cpp)]  
  
##  <a name="getlocaltm"></a>CTime::GetLocalTm  
 Ruft eine **Struct tm** , enthält eine Aufgliederung der Zeit, die in diesem enthaltenen `CTime` Objekt.  
  
```  
struct tm* GetLocalTm(struct tm* ptm) const; 
```  
  
### <a name="parameters"></a>Parameter  
 `ptm`  
 Zeigt auf einen Puffer, der die Zeitdaten empfängt. Wenn dieser Zeiger ist **NULL**, wird eine Ausnahme ausgelöst.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine ausgefüllt **Struct tm** wie in der Includedatei Zeit definiert. H. Finden Sie unter [Gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) für das Strukturlayout.  
  
### <a name="remarks"></a>Hinweise  
 `GetLocalTm`Gibt die lokale Zeit zurück.  
  
 `ptm` darf nicht `NULL` sein. Wenn Sie das alte Verhalten, in dem möchten `ptm` möglicherweise `NULL` um anzugeben, dass ein interner, statisch zugewiesene Puffer verwendet werden soll, dann heben Sie die Definition `_SECURE_ATL`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#157;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_11.cpp)]  
  
##  <a name="getminute"></a>CTime::GetMinute  
 Gibt die Minute, dargestellt durch die `CTime` Objekt.  
  
```  
int GetMinute() const throw(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Minute, basierend auf der lokalen Zeit, im Bereich von 0 bis 59 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft `GetLocalTm`, die statisch eine interne verwendet zugeordneten Puffer. Die Daten in diesem Puffer werden aufgrund von Aufrufen an andere überschrieben `CTime` Memberfunktionen.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetHour](#gethour).  
  
##  <a name="getmonth"></a>CTime::GetMonth  
 Gibt die Monats, dargestellt durch die `CTime` Objekt.  
  
```  
int GetMonth() const throw(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Monat, basierend auf der lokalen Zeit, im Bereich von 1 bis 12 zurück (1 = Januar).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft `GetLocalTm`, die statisch eine interne verwendet zugeordneten Puffer. Die Daten in diesem Puffer werden aufgrund von Aufrufen an andere überschrieben `CTime` Memberfunktionen.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetDay](#getday).  
  
##  <a name="getsecond"></a>CTime::GetSecond  
 Gibt das zweite, dargestellt durch die `CTime` Objekt.  
  
```  
int GetSecond() const throw(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Sekunde basierend auf der lokalen Zeit, im Bereich von 0 bis 59.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft `GetLocalTm`, die statisch eine interne verwendet zugeordneten Puffer. Die Daten in diesem Puffer werden aufgrund von Aufrufen an andere überschrieben `CTime` Memberfunktionen.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetHour](#gethour).  
  
##  <a name="gettime"></a>CTime::GetTime  
 Gibt eine **__time64_t** -Wert für den angegebenen `CTime` Objekt.  
  
```  
__time64_t GetTime() const throw(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 **GetTime** gibt die Anzahl der Sekunden zwischen dem aktuellen `CTime` Objekt und dem 1. Januar 1970.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#158;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_12.cpp)]  
  
##  <a name="getyear"></a>CTime::GetYear  
 Gibt das Jahr, dargestellt durch die `CTime` Objekt.  
  
```  
int GetYear();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Jahr, basierend auf der lokalen Zeit, im Bereich von Januar 1,1970, um dem 18. Januar 2038 (inklusiv).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft `GetLocalTm`, die statisch eine interne verwendet zugeordneten Puffer. Die Daten in diesem Puffer werden aufgrund von Aufrufen an andere überschrieben `CTime` Memberfunktionen.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetDay](#getday).  
  
##  <a name="operator_eq"></a>CTime::operator =  
 Der Zuweisungsoperator.  
  
```  
CTime& operator=(__time64_t time) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `time`  
 Die neuen Datums-/Uhrzeit-Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktualisierte `CTime` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Dieser überladenen Zuweisungsoperator kopiert die Quellzeit in die `CTime` Objekt. Der interne Speicher ein `CTime` Objekt ist unabhängig von der Zeitzone. Konvertierung der Zeitzone ist bei der Zuordnung nicht erforderlich.  
  
##  <a name="operator_add_-"></a>CTime::operator +, -  
 Diese Operatoren addieren und subtrahieren `CTimeSpan` und `CTime` Objekte.  
  
```  
CTime operator+(CTimeSpan timeSpan) const throw(); 
CTime operator-(CTimeSpan timeSpan) const throw(); 
CTimeSpan operator-(CTime time) const throw(); 
```  
  
### <a name="parameters"></a>Parameter  
 *Zeitspanne*  
 Das `CTimeSpan` Objekt hinzugefügt oder entfernt werden soll.  
  
 `time`  
 Die `CTime` -Objekt, das subtrahiert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CTime` oder `CTimeSpan` -Objekt, das das Ergebnis des Vorgangs darstellt.  
  
### <a name="remarks"></a>Hinweise  
 `CTime`Objekte darstellen, absolute Zeit `CTimeSpan` Objekte relative Zeit darstellen. Die ersten beiden Operatoren können Sie addieren und subtrahieren `CTimeSpan` Objekte in und aus `CTime` Objekte. Der dritte Operator können Sie eine subtrahieren `CTime` -Objekt von einem anderen ergibt ein `CTimeSpan` Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#159;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_13.cpp)]  
  
##  <a name="operator_add_eq_-_eq"></a>CTime::operator +=, =  
 Diese Operatoren Addition und Subtraktion ein `CTimeSpan` -Objekts in und aus diesem `CTime` Objekt.  
  
```  
CTime& operator+=(CTimeSpan span) throw();
CTime& operator-=(CTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Das `CTimeSpan` Objekt hinzugefügt oder entfernt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktualisierte `CTime` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Operatoren ermöglichen es Ihnen, Addition und Subtraktion ein `CTimeSpan` -Objekts in und aus diesem `CTime` Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#160;](../../atl-mfc-shared/codesnippet/cpp/ctime-class_14.cpp)]  
  
##  <a name="serialize64"></a>CTime::Serialize64  
  
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
 [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [_ftime_s, _ftime32_s, _ftime64_s](../../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [CTimeSpan-Klasse](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [ATL/MFC-freigegeben Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)



