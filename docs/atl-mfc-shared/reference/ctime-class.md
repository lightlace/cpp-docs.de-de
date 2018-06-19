---
title: CTime-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ec195c7733255487b08f8b48379abe58e305f61
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366548"
---
# <a name="ctime-class"></a>CTime-Klasse
Stellt eine absolute Uhrzeit und Datum.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CTime  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTime:: CTime](#ctime)|Erstellt `CTime` Objekte auf verschiedene Weise.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTime::Format](#format)|Konvertiert eine `CTime` Objekt in eine formatierte Zeichenfolge – basierend auf der lokalen Zeitzone.|  
|[CTime::FormatGmt](#formatgmt)|Konvertiert eine `CTime` Objekt in eine formatierte Zeichenfolge – basierend auf UTC.|  
|[CTime::GetAsDBTIMESTAMP](#getasdbtimestamp)|Konvertiert die gespeicherten Uhrzeitinformationen der `CTime` Objekt in eine Win32-kompatibles DBTIMESTAMP-Struktur.|  
|[CTime::GetAsSystemTime](#getassystemtime)|Konvertiert die gespeicherten Uhrzeitinformationen der `CTime` Objekt in ein Win32-kompatibles [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur.|  
|[CTime:: GetCurrentTime](#getcurrenttime)|Erstellt eine `CTime` -Objekt, das die aktuelle Uhrzeit (statische Memberfunktion) darstellt.|  
|[CTime::GetDay](#getday)|Gibt den Tag darstellt, durch die `CTime` Objekt.|  
|[CTime::GetDayOfWeek](#getdayofweek)|Gibt den Tag des Wochentags, dargestellt durch die `CTime` Objekt.|  
|[CTime::GetGmtTm](#getgmttm)|Unterteilt eine `CTime` Objekt in Komponenten – basierend auf UTC.|  
|[CTime::GetHour](#gethour)|Gibt die Stunde, dargestellt durch die `CTime` Objekt.|  
|[CTime::GetLocalTm](#getlocaltm)|Unterteilt eine `CTime` Objekt in Komponenten – basierend auf der lokalen Zeitzone.|  
|[CTime::GetMinute](#getminute)|Gibt die Minute, dargestellt durch die `CTime` Objekt.|  
|[CTime::GetMonth](#getmonth)|Gibt den Monat, dargestellt durch die `CTime` Objekt.|  
|[CTime::GetSecond](#getsecond)|Gibt die zweite, dargestellt durch die `CTime` Objekt.|  
|[CTime::GetTime](#gettime)|Gibt eine **__time64_t** Wert für den angegebenen `CTime` Objekt.|  
|[CTime::GetYear](#getyear)|Gibt das Jahr, dargestellt durch die `CTime` Objekt.|  
|[CTime::Serialize64](#serialize64)|Serialisiert Daten zu oder von einem Archiv.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[Operator + -](#operator_add_-)|Diese Operatoren, Addition und Subtraktion `CTimeSpan` und `CTime` Objekte.|  
|[Operator +=, =](#operator_add_eq_-_eq)|Diese Operatoren, Addition und Subtraktion ein `CTimeSpan` -Objekts in und aus diesem `CTime` Objekt.|  
|[operator =](#operator_eq)|Der Zuweisungsoperator.|  
|[Operator ==, < usw..](#ctime_comparison_operators)|Vergleichsoperatoren.|  
  
## <a name="remarks"></a>Hinweise  
 `CTime` eine Basisklasse verfügt nicht über.  
  
 `CTime` Werte basieren auf koordinierte Weltzeit (UTC), die koordinierte Weltzeit (Greenwich Mean Time, GMT) entspricht. Finden Sie unter [Uhrzeitverwaltung](../../c-runtime-library/time-management.md) Informationen wie die Zeitzone bestimmt wird.  
  
 Beim Erstellen einer `CTime` Objekt, das Festlegen der `nDST` Parameter auf 0, um anzugeben, dass Normalzeit aktiviert ist, oder auf einen Wert größer als 0 weist darauf hin, Sommerzeit wirksam oder an einen Wert kleiner als 0 (null), damit die C-Laufzeitbibliothek Code Comput e, ob Normalzeit oder Sommerzeit wirksam ist. `tm_isdst` ist ein Pflichtfeld. Wenn nicht festgelegt ist, dessen Wert nicht definiert ist und der Rückgabewert [Mktime](../../c-runtime-library/reference/mktime-mktime32-mktime64.md) kann nicht berechnet werden. Wenn `timeptr` verweist auf eine tm-Struktur, die von einem vorherigen Aufruf zurückgegebene [Asctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md), [_gmtime_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md), oder [Localtime_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md), `tm_isdst` Feld enthält die richtiger Wert.  
  
 Eine Begleitklasse [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md), stellt ein Zeitintervall dar.  
  
 Die `CTime` und `CTimeSpan` Klassen sind nicht für die Ableitung ausgelegt. Da es keine virtuellen Funktionen, die Größe des sind `CTime` und `CTimeSpan` Objekte ist genau 8 Bytes. Die meisten Memberfunktionen enthält Inlinekommentare.  
  
> [!NOTE]
>  Die oberen Frist ist 12/31/3000. Die untere Grenze ist 1/1/1970 12:00:00 Uhr GMT.  
  
 Weitere Informationen zur Verwendung von `CTime`, finden Sie in den Artikeln [Datum und Uhrzeit](../../atl-mfc-shared/date-and-time.md), und [Uhrzeitverwaltung](../../c-runtime-library/time-management.md) in die Run-Time Library Reference.  
  
> [!NOTE]
>  Die `CTime` Struktur, die von MFC 7.1 in MFC 8.0 geändert. Wenn Sie Serialisieren einer `CTime` -Struktur unter Verwendung der `operator <<` MFC 8.0 oder höher ist die resultierende Datei nicht gelesen werden unter älteren Versionen von MFC.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atltime.h  
  
##  <a name="ctime_comparison_operators"></a>  CTime-Vergleichsoperatoren  
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
 Diese Operatoren vergleichen zwei absolute Zeiten und zurückgeben **"true"** , wenn die Bedingung, andernfalls "true ist" **"false"**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#161](../../atl-mfc-shared/codesnippet/cpp/ctime-class_1.cpp)]  
  
##  <a name="ctime"></a>  CTime:: CTime  
 Erstellt ein neues `CTime` Initialisiert mit dem angegebenen Objekt.  
  
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
 Gibt eine `CTime` bereits vorhandenen Objekts ab.  
  
 `time`  
 Ein **__time64_t** Time-Werten, die die Anzahl der Sekunden an, nach dem 1. Januar 1970 UTC ist. Beachten Sie, dass dies in die lokale Zeit angepasst wird. Angenommen, Sie befinden sich in Berlin und erstellen eine `CTime` -Objekt durch Übergeben eines Parameters von 0 (null) [CTime::GetMonth](#getmonth) 12 zurück.  

  
 `nYear`, `nMonth`, `nDay`, `nHour`, `nMin`, `nSec`  
 Gibt an, die Werte für Datum und Uhrzeit an, in die neue kopiert werden `CTime` Objekt.  
  
 `nDST`  
 Gibt an, ob die Sommerzeit wirksam ist. Dabei kann es sich um einen der drei folgenden Werte aufweisen:  
  
- `nDST` Set 0Standard Zeit ist aktiviert.  
  
- `nDST` Setzen Sie auf einen Wert größer als 0Daylight Winterzeit wirksam ist.  
  
- `nDST` Legen Sie auf einen Wert kleiner als 0The-Standard. Automatisch berechnet, ob Normalzeit oder Sommerzeit gilt.  
  
 `wDosDate`, `wDosTime`  
 MS-DOS-Datum und Uhrzeit-Werte in einen Datum/Uhrzeit-Wert konvertiert und kopiert in das neue `CTime` Objekt.  
  
 `st`  
 Ein [SYSTEMTIME](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/d6609fff-1931-4818-8a26-f042630af0b0/locales/en-us) Struktur in einen Datum/Uhrzeit-Wert konvertiert und kopiert in das neue `CTime` Objekt.  
  
 `ft`  
 Ein [FILETIME](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/979ce746-dc17-4147-89f8-41d05c5fcc5f/locales/en-us) Struktur in einen Datum/Uhrzeit-Wert konvertiert und kopiert in das neue `CTime` Objekt.  
  
 DBTS  
 Ein Verweis auf eine DBTIMESTAMP-Struktur, die die aktuelle lokale Zeit enthält.  
  
### <a name="remarks"></a>Hinweise  
 Jeder Konstruktor wird im folgenden beschrieben:  
  
- **CTime();**  Erstellt eine nicht initialisierte `CTime` Objekt. Mit diesem Konstruktor können Sie definieren `CTime` -Objekt des Arrays. Sie sollten diese Arrays mit gültigen Zeiten vor der Verwendung initialisieren.  
  
- **CTime (const CTime &);**  Erstellt eine `CTime` Objekt von einem anderen `CTime` Wert.  
  
- **CTime (__time64_t);**  Erstellt eine `CTime` -Objekt aus einem **__time64_t** Typ. Dieser Konstruktor erwartet eine UTC-Zeit und das Ergebnis vor dem Speichern des Ergebnisses in eine Ortszeit konvertiert.  
  
- **CTime (Int, Int,...)**  Erstellt eine `CTime` -Sitzungsobjekts Ortszeit Komponenten mit einzelnen Komponenten eingeschränkt, die den folgenden Bereichen:  
  
    |Komponente|Bereich|  
    |---------------|-----------|  
    |`nYear`|1970-3000|  
    |`nMonth`|1-12|  
    |`nDay`|1-31|  
    |`nHour`|0-23|  
    |`nMin`|0-59|  
    |`nSec`|0-59|  
  
     Dieser Konstruktor wird die entsprechende Konvertierung in UTC. Die Debugversion von der Microsoft Foundation Class-Bibliothek bestätigt wird, wenn eine oder mehrere der Time-Komponenten sind außerhalb des gültigen Bereichs. Sie müssen die Argumente vor dem Aufruf überprüfen. Dieser Konstruktor wird eine Ortszeit erwartet.  
  
- **CTime (WORD, WORD);**  Erstellt eine `CTime` Objekt aus der angegebenen MS-DOS-Datum und Uhrzeit-Werte. Dieser Konstruktor wird eine Ortszeit erwartet.  
  
- **CTime (const SYSTEMTIME &);**  Erstellt eine `CTime` -Objekt aus einer `SYSTEMTIME` Struktur. Dieser Konstruktor wird eine Ortszeit erwartet.  
  
- **CTime (const FILETIME &);**  Erstellt eine `CTime` -Objekt aus einer `FILETIME` Struktur. Verwenden Sie wahrscheinlich nicht `CTime FILETIME` -Initialisierung direkt. Bei Verwendung von einer `CFile` Objekt, das eine Datei zu manipulieren `CFile::GetStatus` Ruft den Zeitstempel der Datei für Sie durch eine `CTime` Objekt initialisiert wird, mit einer `FILETIME` Struktur. Dieser Konstruktor nimmt eine Uhrzeit (UTC) an und den Wert automatisch in die Ortszeit konvertiert, vor dem Speichern des Ergebnisses.  
  
    > [!NOTE]
    >  Der Konstruktor mit **DBTIMESTAMP** Parameter ist nur verfügbar, wenn "OleDb.h" enthalten ist.  
  
 Weitere Informationen finden Sie unter der [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) und [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) Struktur im Windows SDK. Siehe auch die [MS-DOS-Datum und Uhrzeit](http://msdn.microsoft.com/library/windows/desktop/ms724503) Eintrag im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#148](../../atl-mfc-shared/codesnippet/cpp/ctime-class_2.cpp)]  
  
##  <a name="format"></a>  CTime::Format  
 Rufen Sie diese Memberfunktion, um eine formatierte Darstellung von Datums-/ Uhrzeitwert zu erstellen.  
  
```  
CString Format(LPCTSTR pszFormat) const; 
CString Format(UINT nFormatID) const; 
```  
  
### <a name="parameters"></a>Parameter  
 `pszFormat`  
 Eine Formatierungszeichenfolge ähnelt der `printf` Formatierungszeichenfolge. Formatierungscodes vorangestellt Prozentsatz ( `%`) anmelden, werden mit den entsprechenden ersetzt `CTime` Komponente. Andere Zeichen in der Formatzeichenfolge werden in der zurückgegebenen Zeichenfolge unverändert kopiert. Finden Sie die Laufzeitfunktion [Strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) eine Liste der Formatierungscodes.  
  
 `nFormatID`  
 Die ID der Zeichenfolge, die dieses Format bezeichnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , die die formatierte Uhrzeit enthält.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Status dieser `CTime` Objekt null ist, wird eine leere Zeichenfolge zurückgegeben.  
  
 Diese Methode löst eine Ausnahme aus, wenn die Datums-/ Uhrzeitwert so formatieren Sie nicht im Bereich von Mitternacht, 1. Januar 1970 bis 31. Dezember 3000 ist Universal Coordinated Time (UTC).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#149](../../atl-mfc-shared/codesnippet/cpp/ctime-class_3.cpp)]  
  
##  <a name="formatgmt"></a>  CTime::FormatGmt  
 Generiert eine formatierte Zeichenfolge, die dies entspricht `CTime` Objekt.  
  
```  
CString FormatGmt(LPCTSTR pszFormat) const; 
CString FormatGmt(UINT nFormatID) const; 
```  
  
### <a name="parameters"></a>Parameter  
 `pszFormat`  
 Gibt eine Formatierungszeichenfolge, die ähnlich wie die `printf` Formatierungszeichenfolge. Finden Sie die Laufzeitfunktion [Strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) Details.  
  
 `nFormatID`  
 Die ID der Zeichenfolge, die dieses Format bezeichnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , die die formatierte Uhrzeit enthält.  
  
### <a name="remarks"></a>Hinweise  
 Time-Werten wird nicht konvertiert, und daher widerspiegelt UTC.  
  
 Diese Methode löst eine Ausnahme aus, wenn die Datums-/ Uhrzeitwert so formatieren Sie nicht im Bereich von Mitternacht, 1. Januar 1970 bis 31. Dezember 3000 ist Universal Coordinated Time (UTC).  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [CTime::Format](#format).  
  
##  <a name="getasdbtimestamp"></a>  CTime::GetAsDBTIMESTAMP  
 Rufen Sie diese Memberfunktion zum Konvertieren der gespeicherten Uhrzeitinformationen der `CTime` Objekt in eine Win32-kompatibles DBTIMESTAMP-Struktur.  
  
```  
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `dbts`  
 Ein Verweis auf eine DBTIMESTAMP-Struktur, die die aktuelle lokale Zeit enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Speichert die resultierende Uhrzeit in der referenzierten `dbts`-Struktur. Die **DBTIMESTAMP** Datenstruktur, die von dieser Funktion initialisiert hat seine **Bruch** Member auf 0 festgelegt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#150](../../atl-mfc-shared/codesnippet/cpp/ctime-class_4.cpp)]  
  
##  <a name="getassystemtime"></a>  CTime::GetAsSystemTime  
 Rufen Sie diese Memberfunktion zum Konvertieren der gespeicherten Uhrzeitinformationen der `CTime` Objekt in ein Win32-kompatibles [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur.  
  
```  
bool GetAsSystemTime(SYSTEMTIME& st) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 *timeDest*  
 Ein Verweis auf eine [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur, die das konvertierte Datums-/Uhrzeitwert der speichern die `CTime` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn erfolgreich; andernfalls "false".  
  
### <a name="remarks"></a>Hinweise  
 `GetAsSystemTime` Speichert die resultierende Uhrzeit in der referenzierten *TimeDest* Struktur. Die `SYSTEMTIME` Datenstruktur, die von dieser Funktion initialisiert hat seine **wMilliseconds** Member auf 0 festgelegt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#151](../../atl-mfc-shared/codesnippet/cpp/ctime-class_5.cpp)]  
  
##  <a name="getcurrenttime"></a>  CTime:: GetCurrentTime  
 Gibt eine `CTime` -Objekt, das die aktuelle Uhrzeit darstellt.  
  
```  
static CTime WINAPI GetCurrentTime() throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt das aktuelle Systemdatum und die Uhrzeit in Coordinated Universal Time (UTC) zurück.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#152](../../atl-mfc-shared/codesnippet/cpp/ctime-class_6.cpp)]  
  
##  <a name="getday"></a>  CTime::GetDay  
 Gibt den Tag darstellt, durch die `CTime` Objekt.  
  
```  
int GetDay() const throw(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Tag des Monats, basierend auf der Ortszeit oder im Bereich von 1 bis 31 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft `GetLocalTm`, verwendet einen internen, statisch zugeordneten Puffer. Die Daten in diesem Puffer werden aufgrund von Aufrufen von anderen überschrieben `CTime` Memberfunktionen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#153](../../atl-mfc-shared/codesnippet/cpp/ctime-class_7.cpp)]  
  
##  <a name="getdayofweek"></a>  CTime::GetDayOfWeek  
 Gibt den Tag des Wochentags, dargestellt durch die `CTime` Objekt.  
  
```  
int GetDayOfWeek() const throw(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Wochentag basierend auf der Ortszeit zurück. 1 = Sonntag, 2 = Montag, 7 = Samstag.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft `GetLocalTm`, die statisch eine interne verwendet zugeordneten Puffer. Die Daten in diesem Puffer werden aufgrund von Aufrufen von anderen überschrieben `CTime` Memberfunktionen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#154](../../atl-mfc-shared/codesnippet/cpp/ctime-class_8.cpp)]  
  
##  <a name="getgmttm"></a>  CTime::GetGmtTm  
 Ruft eine **Struktur tm** , enthält eine Zerlegung des der Zeitangabe in diesem `CTime` Objekt.  
  
```  
struct tm* GetGmtTm(struct tm* ptm) const; 
```  
  
### <a name="parameters"></a>Parameter  
 `ptm`  
 Zeigt auf einen Puffer, der die Zeitdaten erhält. Wenn dieser Zeiger ist **NULL**, wird eine Ausnahme ausgelöst.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine ausgefüllt **Struktur tm** gemäß Definition in der Includedatei Zeit. H. Finden Sie unter [Gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) für das Strukturlayout.  
  
### <a name="remarks"></a>Hinweise  
 `GetGmtTm` Gibt die UTC zurück.  
  
 `ptm` darf nicht `NULL` sein. Wenn Sie das alte Verhalten, in dem zurückkehren möchten `ptm` möglicherweise `NULL` um anzugeben, dass es sich bei ein interner, statisch zugeordneten Puffer verwendet werden soll, klicken Sie dann heben Sie die Definition `_SECURE_ATL`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#155](../../atl-mfc-shared/codesnippet/cpp/ctime-class_9.cpp)]  
  
##  <a name="gethour"></a>  CTime::GetHour  
 Gibt die Stunde, dargestellt durch die `CTime` Objekt.  
  
```  
int GetHour() const throw(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Stunde, basierend auf der Ortszeit oder im Bereich von 0 bis 23 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft `GetLocalTm`, die statisch eine interne verwendet zugeordneten Puffer. Die Daten in diesem Puffer werden aufgrund von Aufrufen von anderen überschrieben `CTime` Memberfunktionen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#156](../../atl-mfc-shared/codesnippet/cpp/ctime-class_10.cpp)]  
  
##  <a name="getlocaltm"></a>  CTime::GetLocalTm  
 Ruft eine **Struktur tm** , enthält eine Zerlegung des der Zeitangabe in diesem `CTime` Objekt.  
  
```  
struct tm* GetLocalTm(struct tm* ptm) const; 
```  
  
### <a name="parameters"></a>Parameter  
 `ptm`  
 Zeigt auf einen Puffer, der die Zeitdaten erhält. Wenn dieser Zeiger ist **NULL**, wird eine Ausnahme ausgelöst.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine ausgefüllt **Struktur tm** gemäß Definition in der Includedatei Zeit. H. Finden Sie unter [Gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) für das Strukturlayout.  
  
### <a name="remarks"></a>Hinweise  
 `GetLocalTm` Gibt die lokale Zeit zurück.  
  
 `ptm` darf nicht `NULL` sein. Wenn Sie das alte Verhalten, in dem zurückkehren möchten `ptm` möglicherweise `NULL` um anzugeben, dass es sich bei ein interner, statisch zugeordneten Puffer verwendet werden soll, klicken Sie dann heben Sie die Definition `_SECURE_ATL`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#157](../../atl-mfc-shared/codesnippet/cpp/ctime-class_11.cpp)]  
  
##  <a name="getminute"></a>  CTime::GetMinute  
 Gibt die Minute, dargestellt durch die `CTime` Objekt.  
  
```  
int GetMinute() const throw(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Minute, basierend auf der Ortszeit oder im Bereich von 0 bis 59 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft `GetLocalTm`, die statisch eine interne verwendet zugeordneten Puffer. Die Daten in diesem Puffer werden aufgrund von Aufrufen von anderen überschrieben `CTime` Memberfunktionen.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetHour](#gethour).  
  
##  <a name="getmonth"></a>  CTime::GetMonth  
 Gibt den Monat, dargestellt durch die `CTime` Objekt.  
  
```  
int GetMonth() const throw(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Monat, basierend auf der Ortszeit oder im Bereich von 1 bis 12 zurück (1 = Januar).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft `GetLocalTm`, die statisch eine interne verwendet zugeordneten Puffer. Die Daten in diesem Puffer werden aufgrund von Aufrufen von anderen überschrieben `CTime` Memberfunktionen.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetDay](#getday).  
  
##  <a name="getsecond"></a>  CTime::GetSecond  
 Gibt die zweite, dargestellt durch die `CTime` Objekt.  
  
```  
int GetSecond() const throw(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Sekunde basierend auf der Ortszeit oder im Bereich von 0 bis 59.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft `GetLocalTm`, die statisch eine interne verwendet zugeordneten Puffer. Die Daten in diesem Puffer werden aufgrund von Aufrufen von anderen überschrieben `CTime` Memberfunktionen.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetHour](#gethour).  
  
##  <a name="gettime"></a>  CTime::GetTime  
 Gibt eine **__time64_t** Wert für den angegebenen `CTime` Objekt.  
  
```  
__time64_t GetTime() const throw(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 **GetTime** gibt die Anzahl der Sekunden zwischen dem aktuellen zurück `CTime` Objekt und dem 1. Januar 1970.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#158](../../atl-mfc-shared/codesnippet/cpp/ctime-class_12.cpp)]  
  
##  <a name="getyear"></a>  CTime::GetYear  
 Gibt das Jahr, dargestellt durch die `CTime` Objekt.  
  
```  
int GetYear();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Jahr, basierend auf der Ortszeit oder im Bereich von Januar 1,1970, zu dem 18. Januar 2038 (inklusiv).  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ruft `GetLocalTm`, die statisch eine interne verwendet zugeordneten Puffer. Die Daten in diesem Puffer werden aufgrund von Aufrufen von anderen überschrieben `CTime` Memberfunktionen.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetDay](#getday).  
  
##  <a name="operator_eq"></a>  CTime::operator =  
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
 Diese überladenen Zuweisungsoperator kopiert die Quellzeit in diese `CTime` Objekt. Der interne Speicher in einem `CTime` Objekt wird unabhängig von der Zeitzone. Zeitzonenkonvertierung ist nicht erforderlich, bei der Zuordnung.  
  
##  <a name="operator_add_-"></a>  CTime::operator +, -  
 Diese Operatoren, Addition und Subtraktion `CTimeSpan` und `CTime` Objekte.  
  
```  
CTime operator+(CTimeSpan timeSpan) const throw(); 
CTime operator-(CTimeSpan timeSpan) const throw(); 
CTimeSpan operator-(CTime time) const throw(); 
```  
  
### <a name="parameters"></a>Parameter  
 *TimeSpan*  
 Die `CTimeSpan` Objekt, das hinzugefügt oder entfernt werden.  
  
 `time`  
 Die `CTime` Objekt, das subtrahiert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CTime` oder `CTimeSpan` Objekt, das das Ergebnis des Vorgangs darstellt.  
  
### <a name="remarks"></a>Hinweise  
 `CTime` -Objekte darstellen absoluten Zeitpunkt `CTimeSpan` Objekte relative Zeit darstellen. Die ersten beiden Operatoren können Sie von Addition und Subtraktion `CTimeSpan` Objekte in und aus `CTime` Objekte. Der dritte Operator können Sie eine subtrahieren `CTime` Objekt von einem anderen ergeben eine `CTimeSpan` Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#159](../../atl-mfc-shared/codesnippet/cpp/ctime-class_13.cpp)]  
  
##  <a name="operator_add_eq_-_eq"></a>  CTime::operator +=, =  
 Diese Operatoren, Addition und Subtraktion ein `CTimeSpan` -Objekts in und aus diesem `CTime` Objekt.  
  
```  
CTime& operator+=(CTimeSpan span) throw();
CTime& operator-=(CTimeSpan span) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `span`  
 Die `CTimeSpan` Objekt, das hinzugefügt oder entfernt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktualisierte `CTime` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Operatoren ermöglichen es Ihnen, Addition und Subtraktion ein `CTimeSpan` -Objekts in und aus diesem `CTime` Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#160](../../atl-mfc-shared/codesnippet/cpp/ctime-class_14.cpp)]  
  
##  <a name="serialize64"></a>  CTime::Serialize64  
  
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
 [asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)   
 [_ftime_s, _ftime32_s, _ftime64_s](../../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)   
 [gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)   
 [localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)   
 [strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)   
 [CTimeSpan-Klasse](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Freigegebene ATL-/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)


