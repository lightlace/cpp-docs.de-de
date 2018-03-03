---
title: COleDateTime Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDateTime
- ATLCOMTIME/ATL::COleDateTime
- ATLCOMTIME/ATL::COleDateTime::COleDateTime
- ATLCOMTIME/ATL::COleDateTime::Format
- ATLCOMTIME/ATL::COleDateTime::GetAsDBTIMESTAMP
- ATLCOMTIME/ATL::COleDateTime::GetAsSystemTime
- ATLCOMTIME/ATL::COleDateTime::GetAsUDATE
- ATLCOMTIME/ATL::COleDateTime::GetCurrentTime
- ATLCOMTIME/ATL::COleDateTime::GetDay
- ATLCOMTIME/ATL::COleDateTime::GetDayOfWeek
- ATLCOMTIME/ATL::COleDateTime::GetDayOfYear
- ATLCOMTIME/ATL::COleDateTime::GetHour
- ATLCOMTIME/ATL::COleDateTime::GetMinute
- ATLCOMTIME/ATL::COleDateTime::GetMonth
- ATLCOMTIME/ATL::COleDateTime::GetSecond
- ATLCOMTIME/ATL::COleDateTime::GetStatus
- ATLCOMTIME/ATL::COleDateTime::GetYear
- ATLCOMTIME/ATL::COleDateTime::ParseDateTime
- ATLCOMTIME/ATL::COleDateTime::SetDate
- ATLCOMTIME/ATL::COleDateTime::SetDateTime
- ATLCOMTIME/ATL::COleDateTime::SetStatus
- ATLCOMTIME/ATL::COleDateTime::SetTime
- ATLCOMTIME/ATL::COleDateTime::m_dt
- ATLCOMTIME/ATL::COleDateTime::m_status
dev_langs:
- C++
helpviewer_keywords:
- shared classes, COleDateTime
- time-only values
- Date data type, MFC encapsulation of
- COleDateTime class
- dates, handling in MFC
- time, handling in MFC
ms.assetid: e718f294-16ec-4649-88b6-a4dbae5178fb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dbe0e831a644dfc09c6b4afb3c54f23b220850d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="coledatetime-class"></a>COleDateTime-Klasse
Kapselt die `DATE` -Datentyp, der in der OLE-Automatisierung verwendet wird.  
  
## <a name="syntax"></a>Syntax  
  
```
class COleDateTime
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDateTime::COleDateTime](#coledatetime)|Erstellt ein `COleDateTime`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDateTime::Format](#format)|Generiert eine formatierte Zeichenfolgendarstellung ein `COleDateTime` Objekt.|  
|[COleDateTime::GetAsDBTIMESTAMP](#getasdbtimestamp)|Rufen Sie diese Methode zum Abrufen der Zeit in die `COleDateTime` -Objekt als eine **DBTIMESTAMP** Datenstruktur.|  
|[COleDateTime::GetAsSystemTime](#getassystemtime)|Rufen Sie diese Methode zum Abrufen der Zeit in die `COleDateTime` -Objekt als eine [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Datenstruktur.|  
|[COleDateTime::GetAsUDATE](#getasudate)|Rufen Sie diese Methode zum Abrufen der Zeit in die `COleDateTime` als eine **Update** Datenstruktur.|  
|[COleDateTime::GetCurrentTime](#getcurrenttime)|Erstellt eine `COleDateTime` -Objekt, das die aktuelle Uhrzeit (statische Memberfunktion) darstellt.|  
|[COleDateTime::GetDay](#getday)|Gibt den Tag zurück dies `COleDateTime` Objekt darstellt (1-31).|  
|[COleDateTime::GetDayOfWeek](#getdayofweek)|Gibt den Tag der Woche zurück dies `COleDateTime` -Objekt darstellt (Sonntag = 1).|  
|[COleDateTime::GetDayOfYear](#getdayofyear)|Gibt den Tag des Jahres zurück dies `COleDateTime` -Objekt darstellt (1. Januar = 1).|  
|[COleDateTime::GetHour](#gethour)|Gibt die Stunde dies `COleDateTime` -Objekt darstellt (0 - 23).|  
|[COleDateTime::GetMinute](#getminute)|Gibt die Minute zurück dies `COleDateTime` -Objekt darstellt (0 - 59).|  
|[COleDateTime::GetMonth](#getmonth)|Gibt den Monat zurück dies `COleDateTime` Objekt darstellt (1-12).|  
|[COleDateTime::GetSecond](#getsecond)|Gibt der zweite dies `COleDateTime` -Objekt darstellt (0 - 59).|  
|[COleDateTime::GetStatus](#getstatus)|Ruft ab, der den Status (Gültigkeit) `COleDateTime` Objekt.|  
|[COleDateTime::GetYear](#getyear)|Gibt die Jahresangabe dies `COleDateTime` -Objekt darstellt.|  
|[COleDateTime::ParseDateTime](#parsedatetime)|Liest einen Datum/Uhrzeit-Wert aus einer Zeichenfolge und legt den Wert des `COleDateTime`.|  
|[COleDateTime::SetDate](#setdate)|Legt den Wert dieses `COleDateTime` Objekt mit dem angegebenen DATEONLY-Wert.|  
|[COleDateTime::SetDateTime](#setdatetime)|Legt den Wert dieses `COleDateTime` -Objekt mit dem angegebenen Datum/Uhrzeit-Wert.|  
|[COleDateTime::SetStatus](#setstatus)|Legt den Status (Gültigkeit) dieses `COleDateTime` Objekt.|  
|[COleDateTime::SetTime](#settime)|Legt den Wert dieses `COleDateTime` Objekt mit dem angegebenen ausschließlich zeitbezogene-Wert.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  

|Name|Beschreibung|  
|----------|-----------------|  
|[COleDateTime:: Operator == COleDateTime:: Operator < usw..](#coledatetime_relational_operators)|Vergleichen Sie zwei `COleDateTime` Werte.|  
|[COleDateTime:: Operator +, COleDateTime:: Operator-](#operator_add_-)|Addition und Subtraktion `COleDateTime` Werte.|  
|[COleDateTime:: Operator +=, COleDateTime:: Operator =](#operator_add_eq_-_eq)|Addition und Subtraktion ein `COleDateTime` Wert aus diesem `COleDateTime` Objekt.|  
|[COleDateTime:: Operator =](#operator_eq)|Kopiert ein `COleDateTime` Wert.|  
|[Datum, COleDateTime:: Operator COleDateTime:: Operator Datum *](#operator_date)|Konvertiert eine `COleDateTime` -Wert in einen `DATE` oder ein `DATE*`.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDateTime::m_dt](#m_dt)|Enthält die zugrunde liegende **Datum** dafür `COleDateTime` Objekt.|  
|[COleDateTime::m_status](#m_status)|Enthält den Status dieses `COleDateTime` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `COleDateTime`eine Basisklasse verfügt nicht über.  
  
 Dies ist eine der möglichen Typen für die [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) -Datentyp der OLE-Automatisierung. Ein `COleDateTime` Wert darstellt, absolute Datums- und Uhrzeitwert.  
  
 Die `DATE` Typ wird als Gleitkommawert implementiert. Tage werden aus dem 30. Dezember 1899 wieder, um Mitternacht gemessen. Die folgende Tabelle zeigt einige Datumsangaben und die zugehörigen Werte an:  
  
|Datum|Wert|  
|----------|-----------|  
|Mitternacht 29. Dezember 1899,|-1.0|  
|29. Dezember 1899, 6-Uhr|-1.25|  
|Mitternacht am 30. Dezember 1899|0.0|  
|Mitternacht am 31. Dezember 1899|1,0|  
|1. Januar 1900, 6 Uhr|2.25|  
  
> [!CAUTION]
>  Beachten Sie in der Tabelle oben, obwohl Tageswerte vor Mitternacht am 30. Dezember 1899 negativ Zeit des Tages Werte nicht ausführen. 6:00 Uhr wird beispielsweise immer durch ein Dezimalstellenwert 0,25 unabhängig davon, ob die ganze Zahl, die den Tag darstellt (nach dem 30. Dezember 1899 wieder) positiv oder negativ (vor dem 30. Dezember 1899 wieder) dargestellt. Dies bedeutet, dass ein einfacher floating Point-Vergleich fälschlicherweise sortieren würde eine `COleDateTime` für 6:00 am 12/29/1899 als **später** , die als eine 7:00 Uhr am selben Tag darstellt.  
  
 Die `COleDateTime` -Klasse behandelt Datumsangaben ab dem 1. Januar 100 bis zum 31. Dezember 9999. Die `COleDateTime` Klasse verwendet den gregorianischen Kalender; julianischen wird nicht unterstützt. `COleDateTime`ignoriert die Sommerzeit. (Siehe [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).)  
  
> [!NOTE]
>  Sie können die `%y` Format, um eine zweistellige Jahresangabe nur für Datumsangaben, die beginnend am 1900 abzurufen. Bei Verwendung der `%y` Format auf ein Datum vor 1900, den Code wird einen Assertionsfehler generiert.  
  
 Dieser Typ wird auch verwendet, um nur das Datum oder ausschließlich zeitbezogene Werte darzustellen. Gemäß der Konvention werden das Datum 0 (30. Dezember 1899) wird für ausschließlich zeitbezogene Werte verwendet und Uhrzeit 00:00 (Mitternacht) wird für reine Datum Werte verwendet.  
  
 Bei Erstellung einer `COleDateTime` Objekt ein Datum mit weniger als 100 ist, das Datum wird akzeptiert, aber nachfolgende Aufrufe von `GetYear`, `GetMonth`, `GetDay`, `GetHour`, `GetMinute`, und `GetSecond` fehl, und geben-1 zurück. Zuvor konnten Sie zweistellige Datumsangaben verwenden, aber Datumsangaben muss 100 oder größer in MFC 4.2 und höher.  
  
 Um Probleme zu vermeiden, geben Sie ein vierstelliges Datum. Zum Beispiel:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#1](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_1.cpp)]  
  
 Grundlegende arithmetische Operationen für die `COleDateTime` Werte verwenden Sie die begleitende Klasse [COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md). `COleDateTimeSpan`ein Zeitintervall definieren. Die Beziehung zwischen diesen Klassen ist mit dem Umwandlungsoperator zwischen [CTime](../../atl-mfc-shared/reference/ctime-class.md) und [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md).  
  
 Weitere Informationen zu den `COleDateTime` und `COleDateTimeSpan` Klassen finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ATLComTime.h  
  
##  <a name="coledatetime_relational_operators"></a>COleDateTime relationale Operatoren  
 Vergleichsoperatoren.  
  
```
bool operator==(const COleDateTime& date) const throw();
bool operator!=(const COleDateTime& date) const throw();
bool operator<(const COleDateTime& date) const throw();
bool operator>(const COleDateTime& date) const throw();
bool operator<=(const COleDateTime& date) const throw();
bool operator>=(const COleDateTime& date) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `date`  
 Die **COleDateTime** zu vergleichende Objekt.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Ein ATLASSERT geschieht, wenn eine der beiden Operanden ist ungültig.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#13](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_2.cpp)]  
  
### <a name="example"></a>Beispiel  
 Die Operatoren  **>=** ,  **\< =** ,  **>** , und  **<** , Wenn implementiert die `COleDateTime` Objektsatz ist auf Null.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#170](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_3.cpp)]  
  
##  <a name="coledatetime"></a>COleDateTime::COleDateTime  
 Erstellt ein `COleDateTime`-Objekt.  
  
```
COleDateTime() throw();
COleDateTime(const VARIANT& varSrc) throw();
COleDateTime(DATE dtSrc) throw();
COleDateTime(time_t timeSrc) throw();
COleDateTime(__time64_t timeSrc) throw();
COleDateTime(const SYSTEMTIME& systimeSrc) throw();
COleDateTime(const FILETIME& filetimeSrc) throw();

COleDateTime(int nYear,
    int nMonth,
    int nDay,
    int nHour,
    int nMin,
    int nSec) throw();

COleDateTime(WORD wDosDate,
    WORD wDosTime) throw();
COleDateTime(const DBTIMESTAMP& dbts) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `dateSrc`  
 Eine vorhandene `COleDateTime` -Objekt, in das neue kopiert werden `COleDateTime` Objekt.  
  
 *varSrc*  
 Eine vorhandene **VARIANT** Datenstruktur (möglicherweise einer `COleVariant` Objekt) in einen Datum/Uhrzeit-Wert konvertiert werden soll ( `VT_DATE`) und kopiert Sie in das neue `COleDateTime` Objekt.  
  
 `dtSrc`  
 Eine Datum/Uhrzeit ( **Datum**) Wert in das neue kopiert werden `COleDateTime` Objekt.  
  
 `timeSrc`  
 Ein `time_t` oder **__time64_t** Wert in einen Datum/Uhrzeit-Wert konvertiert und kopiert in das neue `COleDateTime` Objekt.  
  
 *systimeSrc*  
 Ein `SYSTEMTIME` Struktur in einen Datum/Uhrzeit-Wert konvertiert und kopiert in das neue `COleDateTime` Objekt.  
  
 `filetimeSrc`  
 Ein `FILETIME` Struktur in einen Datum/Uhrzeit-Wert konvertiert und kopiert in das neue `COleDateTime` Objekt. Beachten Sie, dass `FILETIME` verwendet Universal Coordinated Time (UTC), damit Sie in der Struktur eine Ortszeit übergeben, die Ergebnisse werden falsche werden. Finden Sie unter [Dateizeiten](http://msdn.microsoft.com/library/windows/desktop/ms724290) in das Windows SDK für Weitere Informationen.  
  
 `nYear`, `nMonth`, `nDay`, `nHour`, `nMin`, `nSec`  
 Geben Sie die Werte für Datum und Uhrzeit an, in die neue kopiert werden `COleDateTime` Objekt.  
  
 `wDosDate`, `wDosTime`  
 MS-DOS-Datum und Uhrzeit-Werte in einen Datum/Uhrzeit-Wert konvertiert und kopiert in das neue `COleDateTime` Objekt.  
  
 `dbts`  
 Ein Verweis auf eine [DBTimeStamp](https://msdn.microsoft.com/library/system.data.oledb.oledbtype) Struktur, die die aktuelle lokale Zeit enthält.  
  
### <a name="remarks"></a>Hinweise  
 Alle diese Konstruktoren erstellen Sie eine neue `COleDateTime` Objekte, die auf den angegebenen Wert initialisiert. Die folgende Tabelle zeigt die gültigen Bereiche für jede Komponente Datum und Uhrzeit:  
  
|Datum/Uhrzeit-Komponente|Gültiger Bereich|  
|--------------------------|-----------------|  
|Jahr|100 - 9999|  
|Monat|0 - 12|  
|Tag|0 - 31|  
|Stunde|0 - 23|  
|Minute|0 - 59|  
|second|0 - 59|  
  
 Beachten Sie, die die tatsächliche obere Grenze für die Tageskomponente variiert basierend auf den Monat und Jahr-Komponenten. Einzelheiten finden Sie in der **SetDate** oder `SetDateTime` Memberfunktionen.  
  
 Es folgt eine kurze Beschreibung jeder Konstruktor:  
  
- `COleDateTime(`**)** Erstellt eine `COleDateTime` Objekt mit 0 (Mitternacht am 30. Dezember 1899) initialisiert.  
  
- `COleDateTime(``dateSrc` **)** Erstellt eine `COleDateTime` Objekt aus einer vorhandenen `COleDateTime` Objekt.  
  
- `COleDateTime(`*VarSrc* **)** erstellt eine `COleDateTime` Objekt. Versucht, Konvertieren einer `VARIANT` Struktur oder [COleVariant](../../mfc/reference/colevariant-class.md) Objekt um einen Datums-/Uhrzeitwert ( `VT_DATE`) Wert. Wenn die Konvertierung erfolgreich ist, wird der konvertierte Wert kopiert, in das neue `COleDateTime` Objekt. Ist dies nicht der Fall, den Wert, der die `COleDateTime` -Objekts auf 0 (Mitternacht am 30. Dezember 1899) und ihren Status auf ungültig festgelegt wird.  
  
- `COleDateTime(``dtSrc` **)** Erstellt eine `COleDateTime` -Objekt aus einem **Datum** Wert.  
  
- `COleDateTime(``timeSrc` **)** Erstellt eine `COleDateTime` -Objekt aus einem `time_t` Wert.  
  
- `COleDateTime(`*SystimeSrc* **)** erstellt eine `COleDateTime` -Objekt aus einem `SYSTEMTIME` Wert.  
  
- `COleDateTime(``filetimeSrc` **)** Erstellt eine `COleDateTime` -Objekt aus einem `FILETIME` Wert. sein. Beachten Sie, dass `FILETIME` verwendet Universal Coordinated Time (UTC), damit Sie in der Struktur eine Ortszeit übergeben, die Ergebnisse werden falsche werden. Finden Sie unter [Dateizeiten](http://msdn.microsoft.com/library/windows/desktop/ms724290) in das Windows SDK für Weitere Informationen.  
  
- `COleDateTime(``nYear`, `nMonth`, `nDay`, `nHour`, `nMin`, `nSec` **)** Erstellt eine `COleDateTime` Objekt aus den angegebenen numerischen Werten.  
  
- `COleDateTime(``wDosDate`, `wDosTime` **)** Erstellt eine `COleDateTime` Objekt aus der angegebenen MS-DOS-Datum und Uhrzeit-Werte.  
  
 Weitere Informationen zu den `time_t` -Datentyp, finden Sie unter der [Zeit](../../c-runtime-library/reference/time-time32-time64.md) -Funktion in der *Run-Time Library Reference*.  
  
 Weitere Informationen finden Sie unter der [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) und [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) Strukturen im Windows SDK.  
  
 Weitere Informationen über die Grenzen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
> [!NOTE]
>  Der Konstruktor mit **DBTIMESTAMP** Parameter ist nur verfügbar, wenn "OleDb.h" enthalten ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#2](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_4.cpp)]  
  
##  <a name="format"></a>COleDateTime::Format  
 Erstellt eine formatierte Darstellung von Datums-/Uhrzeitwert.  
  
```
CString Format(DWORD dwFlags = 0,  LCID lcid = LANG_USER_DEFAULT) const;
CString Format(LPCTSTR lpszFormat) const;
CString Format(UINT nFormatID) const;
```  
  
### <a name="parameters"></a>Parameter  
 `dwFlags`  
 Gibt einen der folgenden Gebietsschemas Flags:  
  
- `LOCALE_NOUSEROVERRIDE`Verwenden Sie anstelle von benutzerdefinierten Einstellungen Standardeinstellungen Gebietsschema des Systems.  
  
- `VAR_TIMEVALUEONLY`Ignorieren Sie den Datumsteil während der Analyse aus.  
  
- `VAR_DATEVALUEONLY`Ignorieren Sie den Zeitbereich während der Analyse aus.  
  
 `lcid`  
 Gibt die Gebietsschema-ID für die Konvertierung an. Weitere Informationen zu Sprachen-IDs finden Sie unter [Sprachbezeichner](http://msdn.microsoft.com/library/windows/desktop/dd318691).  
  
 `lpszFormat`  
 Eine Formatierungszeichenfolge ähnelt der `printf` Formatierungszeichenfolge. Jede Formatierung von Code, Prozentsatz vorangestellt ( `%`) anmelden, wird mit den entsprechenden ersetzt `COleDateTime` Komponente. Andere Zeichen in der Formatzeichenfolge werden in der zurückgegebenen Zeichenfolge unverändert kopiert. Finden Sie die Laufzeitfunktion [Strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) für Weitere Informationen. Der Wert und die Bedeutung von Formatierungscodes für `Format` sind:  
  
- `%H`Stunden den heutigen Tag  
  
- `%M`In der aktuellen Stunde Minuten  
  
- `%S`Sekunden in der aktuellen minute  
  
- `%%`Prozentzeichen  
  
 `nFormatID`  
 Die Ressourcen-ID für die formatsteuerzeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` , den formatierte Datum/Uhrzeit-Wert enthält.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Status dieser `COleDateTime` Objekt null ist, wird eine leere Zeichenfolge zurückgegeben. Wenn der Status ungültig ist, ist die Rückgabezeichenfolge eine Zeichenfolgenressource angegeben `ATL_IDS_DATETIME_INVALID`.  
  
 Eine kurze Beschreibung der drei Formen für diese Funktion lautet folgendermaßen:  
  
 `Format`( `dwFlags`, `lcid`)  
 Dieses Formular formatiert den Wert mit den Spezifikationen der Berichtsdefinitionssprache (Gebietsschema-IDs) für Datum und Uhrzeit. Mit den Standardparametern, wird das Datum und die Uhrzeit, Drucken des Formulars, wenn der Zeitteil 0 (Mitternacht ist), in diesem Fall wird nur das Datum drucken, oder der Datumsteil 0 (30. Dezember 1899 ist) in diesem Fall nur die Zeit gedruckt wird. Wenn der Datum/Uhrzeit-Wert 0 (am 30. Dezember 1899 Mitternacht) ist, wird dieses Formular mit den Standardparametern Mitternacht ausgegeben.  
  
 `Format`( `lpszFormat`)  
 Dieses Formular formatiert den Wert mit der Formatzeichenfolge die spezielle Formatierungscodes enthält, die einem Prozentzeichen (%) vorangestellt werden, wie in `printf`. Die Formatierungszeichenfolge wird als Parameter an die Funktion übergeben. Weitere Informationen zu den Formatierungscodes, finden Sie unter [Strftime, Wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) in die Run-Time Library Reference.  
  
 `Format`( `nFormatID`)  
 Dieses Formular formatiert den Wert mit der Formatzeichenfolge die spezielle Formatierungscodes enthält, die einem Prozentzeichen (%) vorangestellt werden, wie in `printf`. Die Formatzeichenfolge ist eine Ressource. Die ID der diesem Zeichenfolgenressource wird als Parameter übergeben. Weitere Informationen zu den Formatierungscodes, finden Sie unter [Strftime, Wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) in der *Run-Time Library Reference*.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#3](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_5.cpp)]  
  
##  <a name="getasdbtimestamp"></a>COleDateTime::GetAsDBTIMESTAMP  
 Rufen Sie diese Methode zum Abrufen der Zeit in die `COleDateTime` -Objekt als eine **DBTIMESTAMP** Datenstruktur.  
  
```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `dbts`  
 Ein Verweis auf eine [DBTimeStamp](https://msdn.microsoft.com/library/system.data.oledb.oledbtype) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Speichert die resultierende Uhrzeit in der referenzierten `dbts`-Struktur. Die **DBTIMESTAMP** Datenstruktur, die von dieser Funktion initialisiert hat seine **Bruch** Member auf 0 festgelegt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#4](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_6.cpp)]  
  
##  <a name="getassystemtime"></a>COleDateTime::GetAsSystemTime  
 Rufen Sie diese Methode zum Abrufen der Zeit in die `COleDateTime` -Objekt als eine `SYSTEMTIME` Datenstruktur.  
  
```
bool GetAsSystemTime(SYSTEMTIME& sysTime) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 *sysTime*  
 Ein Verweis auf eine [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur zum Empfangen der konvertierte Datums-/Uhrzeitwert aus der `COleDateTime` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** bei Erfolg; **"false"** , wenn die Konvertierung schlägt fehl, oder wenn die `COleDateTime` Objekt **NULL** oder ist ungültig.  
  
### <a name="remarks"></a>Hinweise  
 `GetAsSystemTime`Speichert die resultierende Uhrzeit in der referenzierten *SysTime* Objekt. Die `SYSTEMTIME` Datenstruktur, die von dieser Funktion initialisiert hat seine **wMilliseconds** Member auf 0 festgelegt.  
  
 Finden Sie unter [GetStatus](#getstatus) für Weitere Informationen auf den Statusinformationen im gehalten ein `COleDateTime` Objekt.  
  
##  <a name="getasudate"></a>COleDateTime::GetAsUDATE  
 Rufen Sie diese Methode zum Abrufen der Zeit in die `COleDateTime` -Objekt als eine **Update** Datenstruktur.  
  
```
bool GetAsUDATE(UDATE& udate) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `udate`  
 Ein Verweis auf eine **Update** Struktur zum Empfangen der konvertierte Datums-/Uhrzeitwert aus der `COleDateTime` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** bei Erfolg; **"false"** , wenn die Konvertierung schlägt fehl, oder wenn die `COleDateTime` Objekt **NULL** oder ist ungültig.  
  
### <a name="remarks"></a>Hinweise  
 Ein **Update** Struktur eine "entpackt" Datum darstellt.  
  
##  <a name="getcurrenttime"></a>COleDateTime::GetCurrentTime  
 Rufen Sie diese statische Memberfunktion, um die aktuellen Datums-/Uhrzeitwert zurück.  
  
```
static COleDateTime WINAPI GetCurrentTime() throw();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#5](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_7.cpp)]  
  
##  <a name="getday"></a>COleDateTime::GetDay  
 Ruft den Tag des Monats, von diesem Datum/Uhrzeit-Wert dargestellt.  
  
```
int GetDay() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Tag des Monats, dargestellt durch den Wert dieses `COleDateTime` Objekt oder `COleDateTime::error` Wenn das Tag nicht abgerufen werden konnte.  
  
### <a name="remarks"></a>Hinweise  
 Gültige Rückgabetypen Wertebereich liegt zwischen 1 und 31.  
  
 Informationen zu anderen Memberfunktionen, die den Wert dieses Abfragen `COleDateTime` Objekt, finden Sie unter den folgenden Member-Funktionen:  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#6](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_8.cpp)]  
  
##  <a name="getdayofweek"></a>COleDateTime::GetDayOfWeek  
 Ruft den Tag des Monats, von diesem Datum/Uhrzeit-Wert dargestellt.  
  
```
int GetDayOfWeek() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Tag der Woche dargestellt, die durch den Wert dieses `COleDateTime` Objekt oder `COleDateTime::error` Wenn der Tag der Woche konnte nicht abgerufen werden.  
  
### <a name="remarks"></a>Hinweise  
 Gültige Rückgabetypen mögliche Werte liegen zwischen 1 und 7, wobei 1 = Sonntag, 2 = Montag und so weiter.  
  
 Informationen zu anderen Memberfunktionen, die den Wert dieses Abfragen `COleDateTime` Objekt, finden Sie unter den folgenden Member-Funktionen:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#7](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_9.cpp)]  
  
##  <a name="getdayofyear"></a>COleDateTime::GetDayOfYear  
 Ruft den Tag des Jahres dargestellt, die von diesem Datum/Uhrzeit-Wert ab.  
  
```
int GetDayOfYear() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Tag des Jahres durch den Wert dieses dargestellte `COleDateTime` Objekt oder `COleDateTime::error` Wenn der Tag des Jahres konnte nicht abgerufen werden.  
  
### <a name="remarks"></a>Hinweise  
 Gültige Rückgabetypen Werte liegen zwischen 1 und 366, in dem 1. Januar = 1.  
  
 Informationen zu anderen Memberfunktionen, die den Wert dieses Abfragen `COleDateTime` Objekt, finden Sie unter den folgenden Member-Funktionen:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#8](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_10.cpp)]  
  
##  <a name="gethour"></a>COleDateTime::GetHour  
 Ruft ab, der durch diesen Wert für Datum/Uhrzeit dargestellte Stunde angezeigt.  
  
```
int GetHour() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Stunde, die durch den Wert dieses dargestellte `COleDateTime` Objekt oder `COleDateTime::error` Wenn die Stunde konnte nicht abgerufen werden.  
  
### <a name="remarks"></a>Hinweise  
 Gültige Rückgabetypen Wertebereich liegt zwischen 0 und 23.  
  
 Informationen zu anderen Memberfunktionen, die den Wert dieses Abfragen `COleDateTime` Objekt, finden Sie unter den folgenden Member-Funktionen:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#9](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_11.cpp)]  
  
##  <a name="getminute"></a>COleDateTime::GetMinute  
 Ruft ab, der Minute, der von diesem Datum/Uhrzeit-Wert dargestellt.  
  
```
int GetMinute() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Minute, der durch den Wert dieses dargestellte `COleDateTime` Objekt oder `COleDateTime::error` Wenn die Minute konnte nicht abgerufen werden.  
  
### <a name="remarks"></a>Hinweise  
 Gültige Rückgabetypen Wertebereich liegt zwischen 0 und 59.  
  
 Informationen zu anderen Memberfunktionen, die den Wert dieses Abfragen `COleDateTime` Objekt, finden Sie unter den folgenden Member-Funktionen:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetHour](#gethour).  
  
##  <a name="getmonth"></a>COleDateTime::GetMonth  
 Ruft den Monat, die von diesem Datum/Uhrzeit-Wert dargestellt.  
  
```
int GetMonth() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Monats, dargestellt durch den Wert dieses `COleDateTime` Objekt oder `COleDateTime::error` Wenn Monats konnte nicht abgerufen werden.  
  
### <a name="remarks"></a>Hinweise  
 Gültige Rückgabetypen Wertebereich liegt zwischen 1 und 12.  
  
 Informationen zu anderen Memberfunktionen, die den Wert dieses Abfragen `COleDateTime` Objekt, finden Sie unter den folgenden Member-Funktionen:  
  
- [GetDay](#getday)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetDay](#getday).  
  
##  <a name="getsecond"></a>COleDateTime::GetSecond  
 Ruft das zweite, die von diesem Datum/Uhrzeit-Wert dargestellt.  
  
```
int GetSecond() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die zweite durch den Wert dieses dargestellte `COleDateTime` Objekt oder `COleDateTime::error` Wenn die zweite konnte nicht abgerufen werden.  
  
### <a name="remarks"></a>Hinweise  
 Gültige Rückgabetypen Wertebereich liegt zwischen 0 und 59.  
  
> [!NOTE]
>  Die `COleDateTime` Klasse Schaltsekunden nicht unterstützt.  
  
 Weitere Informationen über die Implementierung für `COleDateTime`, finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
 Informationen zu anderen Memberfunktionen, die den Wert dieses Abfragen `COleDateTime` Objekt, finden Sie unter den folgenden Member-Funktionen:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetHour](#gethour).  
  
##  <a name="getstatus"></a>COleDateTime::GetStatus  
 Ruft den Status (Gültigkeit) ab einem bestimmten `COleDateTime` Objekt.  
  
```
DateTimeStatus GetStatus() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Status dieses `COleDateTime` Wert. Beim Aufrufen **GetStatus** auf eine `COleDateTime` Objekt erstellt hat den Standardwert, wird zurückgegeben, die gültig. Beim Aufrufen **GetStatus** auf eine `COleDateTime` Objekt mit dem Konstruktor auf null festgelegt ist, initialisiert **GetStatus** gibt null zurück. Finden Sie unter **"Hinweise"** für Weitere Informationen.  
  
### <a name="remarks"></a>Hinweise  
 Der Rückgabewert wird definiert, indem die **DateTimeStatus** Aufzählungstyp innerhalb definiert ist die `COleDateTime` Klasse.  
  
```  
enum DateTimeStatus  
{  
   error = -1,  
   valid = 0,  
   invalid = 1,    // Invalid date (out of range, etc.)  
   null = 2,       // Literally has no value  
};  
```  
  
 Eine kurze Beschreibung von diesen Statuswerten verwenden finden Sie in der folgenden Liste:  
  
- `COleDateTime::error`Gibt an, dass beim Versuch, die Teil der Datum/Uhrzeit-Wert abzurufen, ist ein Fehler aufgetreten.  
  
- **COleDateTime::valid** gibt an, dass diese `COleDateTime` -Objekt gültig ist.  
  
- **COleDateTime::invalid** gibt an, dass diese `COleDateTime` Objekt ist ungültig; d. h. der Wert ist möglicherweise falsch.  
  
- **COleDateTime::null** gibt an, dass diese `COleDateTime` ist null, d. h., dass für dieses Objekt kein Wert angegeben wurde. (Dies ist "null", in dem Sinne Datenbank mit"kein Wert" im Gegensatz zu C++ **NULL**.)  
  
 Der Status einer `COleDateTime` Objekt ist ungültig in den folgenden Fällen:  
  
-   Wenn der Wert, von gesetzt wird einem **VARIANT** oder `COleVariant` Wert, der nicht in einen Datum/Uhrzeit-Wert konvertiert werden konnte.  
  
-   Wenn der Wert, von gesetzt wird einem `time_t`, `SYSTEMTIME`, oder `FILETIME` Wert, der nicht in einen gültigen Datum-/Zeit-Wert konvertiert werden konnte.  
  
-   Wenn der Wert, durch festgelegt ist `SetDateTime` mit ungültigen Parameterwerten.  
  
-   Wenn dieses Objekt einen Überlauf oder Unterlauf während eines arithmetischen Zuweisungsvorgangs, nämlich aufgetreten `+=` oder `-=`.  
  
-   Wenn dieses Objekt ein ungültiger Wert zugewiesen wurde.  
  
-   Wenn der Status dieses Objekts explizit festgelegt wurde, um ungültige mit `SetStatus`.  
  
 Weitere Informationen zu den Vorgängen, die den Status ungültig, finden Sie unter den folgenden Memberfunktionen festgelegt werden können:  
  
- [COleDateTime](#coledatetime)  
  
- [SetDateTime](#setdatetime)  
  
- [Operator +, -](#operator_add_-)  
  
- [Operator +=, =](#operator_add_eq_-_eq)  
  
 Weitere Informationen über die Grenzen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#10](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_12.cpp)]  
  
##  <a name="getyear"></a>COleDateTime::GetYear  
 Ruft das Jahr, die von diesem Datum/Uhrzeit-Wert dargestellt.  
  
```
int GetYear() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Jahr durch den Wert dieses dargestellte `COleDateTime` Objekt oder `COleDateTime::error` Wenn das Jahr konnte nicht abgerufen werden.  
  
### <a name="remarks"></a>Hinweise  
 Gültige Rückgabewerte Bereich zwischen 100 und 9999, darunter das Jahrhundert.  
  
 Informationen zu anderen Memberfunktionen, die den Wert dieses Abfragen `COleDateTime` Objekt, finden Sie unter den folgenden Member-Funktionen:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 Weitere Informationen über die Grenzen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetDay](#getday).  
  
##  <a name="m_dt"></a>COleDateTime::m_dt  
 Die zugrunde liegende **Datum** Struktur für dieses `COleDateTime` Objekt.  
  
```
DATE m_dt;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!CAUTION]
>  Ändern des Werts in der **Datum** zugegriffen wird, den der Zeiger verweist, die von dieser Funktion zurückgegebenen Objekts ändert sich den Wert dieses `COleDateTime` Objekt. Ändert nicht den Status dieses `COleDateTime` Objekt.  
  
 Weitere Informationen zur Implementierung von der **Datum** Objekt, finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="m_status"></a>COleDateTime::m_status  
 Enthält den Status dieses `COleDateTime` Objekt.  
  
```
DateTimeStatus m_status;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ dieses Datenelements ist den enumerierten Typ **DateTimeStatus**, die definiert ist, in der `COleDateTime` Klasse. Finden Sie unter [COleDateTime::GetStatus](#getstatus) für Details.  
  
> [!CAUTION]
>  Dieses Datenelement ist für Situationen, Erweiterte Programmierung. Sie sollten die Inline-Memberfunktionen verwenden [GetStatus](#getstatus) und [SetStatus](#setstatus). Finden Sie unter `SetStatus` weiteren Warnhinweise bezüglich dieses Datenelement explizit festlegen.  
  
##  <a name="operator_eq"></a>COleDateTime:: Operator =  
 Kopiert ein `COleDateTime` Wert.  
  
```
COleDateTime& operator=(const VARIANT& varSrc) throw();
COleDateTime& operator=(DATE dtSrc) throw();
COleDateTime& operator=(const time_t& timeSrc) throw();
COleDateTime& operator=(const __time64_t& timeSrc) throw();
COleDateTime& operator=(const SYSTEMTIME& systimeSrc) throw();
COleDateTime& operator=(const FILETIME& filetimeSrc) throw();
COleDateTime& operator=(const UDATE& udate) throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese überladenen Zuweisungsoperatoren Quelle Datums-/Uhrzeitwert in diese kopieren `COleDateTime` Objekt. Eine kurze Beschreibung jeder dieser überladen Zuweisung Operatoren folgt:  
  
- **Operator = (** `dateSrc` **)** den Wert und den Status des Operanden werden in diese kopiert `COleDateTime` Objekt.  
  
- **Operator = (** *VarSrc* **)** Wenn die Konvertierung von der [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) Wert (oder [COleVariant](../../mfc/reference/colevariant-class.md) Objekt) in einen Datum/Uhrzeit ( `VT_DATE`) ist erfolgreich, wird der konvertierte Wert in diese kopiert `COleDateTime` Objekt und dessen Status auf ungültig festgelegt ist. Wenn die Konvertierung nicht erfolgreich ist, wird der Wert dieses Objekts auf 0 (null) (am 30. Dezember 1899 Mitternacht) festgelegt und ihren Status auf ungültig.  
  
- **Operator = (** `dtSrc` **)** der **Datum** Wert wird in diese kopiert `COleDateTime` Objekt und dessen Status auf ungültig festgelegt ist.  
  
- **Operator = (** `timeSrc` **)** der `time_t` oder **__time64_t** Wert konvertiert und in diese kopiert `COleDateTime` Objekt. Wenn die Konvertierung erfolgreich ist, wird der Status dieses Objekts auf ungültig festgelegt. Wenn dies nicht gelingt, festgelegt wird, ungültig.  
  
- **Operator = (** *SystimeSrc* **)** der [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Wert konvertiert und in diese kopiert `COleDateTime` Objekt. Wenn die Konvertierung erfolgreich ist, wird der Status dieses Objekts auf ungültig festgelegt. Wenn dies nicht gelingt, festgelegt wird, ungültig.  
  
- **Operator = (** `udate` **)** der **Update** Wert konvertiert und in diese kopiert `COleDateTime` Objekt. Wenn die Konvertierung erfolgreich ist, wird der Status dieses Objekts auf ungültig festgelegt. Wenn dies nicht gelingt, festgelegt wird, ungültig. Ein **Update** Struktur eine "entpackt" Datum darstellt. Finden Sie im Funktion [VarDateFromUdate](http://msdn.microsoft.com/en-us/1c924ac5-b896-49e1-9ccf-825ac7a030c8) Weitere Details.  
  
- **Operator = (** `filetimeSrc` **)** der [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) Wert konvertiert und in diese kopiert `COleDateTime` Objekt. Wenn die Konvertierung erfolgreich ist, wird der Status dieses Objekts auf ungültig festgelegt. Andernfalls wird festgelegt, ungültig. `FILETIME`Universal Coordinated Time (UTC) verwendet, wenn Sie eine UTC-Zeit in der Struktur übergeben, die Ergebnisse aus UTC-Zeit in die Ortszeit konvertiert und als variant-Zeit gespeichert werden. Dieses Verhalten ist in Visual C++ 6.0- und Visual C++ .NET 2003 SP2 identisch. Finden Sie unter [Dateizeiten](http://msdn.microsoft.com/library/windows/desktop/ms724290) in das Windows SDK für Weitere Informationen.  
  
 Weitere Informationen finden Sie unter der [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) Eintrag im Windows SDK.  
  
 Weitere Informationen zu den `time_t` -Datentyp, finden Sie unter der [Zeit](../../c-runtime-library/reference/time-time32-time64.md) -Funktion in der *Run-Time Library Reference*.  
  
 Weitere Informationen finden Sie unter der [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) und [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) Strukturen im Windows SDK.  
  
 Weitere Informationen über die Grenzen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="operator_add_-"></a>COleDateTime:: Operator +, -  
 Addition und Subtraktion **ColeDateTime** Werte.  
  
```
COleDateTime operator+(COleDateTimeSpan dateSpan) const throw();
COleDateTime operator-(COleDateTimeSpan dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTime& date) const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 `COleDateTime`-Objekte stellen die absolute Zeiten dar. [COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md) -Objekte stellen die relative Häufigkeit dar. Die ersten beiden Operatoren können Sie von Addition und Subtraktion ein `COleDateTimeSpan` Wert aus einem `COleDateTime` Wert. Der dritte Operator können Sie eine subtrahieren `COleDateTime` Wert aus einer anderen ergeben eine `COleDateTimeSpan` Wert.  
  
 Wenn einer der Operanden null ist, ist den Status des resultierenden `COleDateTime` Wert ist null.  
  
 Wenn das resultierende `COleDateTime` Wert liegt außerhalb des gültigen Bereichs zulässiger Werte, der Status dieser `COleDateTime` Wert ist ungültig.  
  
 Wenn entweder der Operanden ist ungültig, und der andere nicht null ist Operand, den Status des resultierenden `COleDateTime` Wert ist ungültig.  
  
 Die  **+**  und  **-**  Operatoren implementiert, wenn die `COleDateTime` Objektsatz ist auf Null. Finden Sie unter [COleDateTime relationale Operatoren](#coledatetime_relational_operators) ein Beispiel.  
  
 Weitere Informationen auf den Status gültig, ungültig und null-Werten finden Sie unter der [M_status](#m_status) Membervariablen gespeichert.  
  
 Weitere Informationen über die Grenzen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#12](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_13.cpp)]  
  
##  <a name="operator_add_eq_-_eq"></a>COleDateTime:: Operator +=, =  
 Addition und Subtraktion ein **ColeDateTime** Wert aus diesem `COleDateTime` Objekt.  
  
```
COleDateTime& operator+=(COleDateTimeSpan dateSpan) throw();
COleDateTime& operator-=(COleDateTimeSpan dateSpan) throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Operatoren ermöglichen es Ihnen, Addition und Subtraktion ein `COleDateTimeSpan` Wert verschiedene andere und aus dieser `COleDateTime`. Wenn einer der Operanden null ist, ist den Status des resultierenden `COleDateTime` Wert ist null.  
  
 Wenn das resultierende `COleDateTime` Wert liegt außerhalb des gültigen Bereichs zulässiger Werte, der den Status `COleDateTime` Wert festgelegt wird, ungültig.  
  
 Wenn einer der Operanden ist ungültig und andere nicht null ist, den Status des resultierenden `COleDateTime` Wert ist ungültig.  
  
 Weitere Informationen auf den Status gültig, ungültig und null-Werten finden Sie unter der [M_status](#m_status) Membervariablen gespeichert.  
  
 Die  **+=**  und  **-=**  Operatoren implementiert, wenn die `COleDateTime` Objektsatz ist auf Null. Finden Sie unter [COleDateTime relationale Operatoren](#coledatetime_relational_operators) ein Beispiel.  
  
 Weitere Informationen über die Grenzen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="operator_date"></a>COleDateTime:: Operator Datum  
 Konvertiert eine **ColeDateTime** -Wert in einen **Datum**.  
  
```
operator DATE() const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator gibt einen **Datum** -Objekt, dessen Wert wird aus dieser kopiert `COleDateTime` Objekt. Weitere Informationen zur Implementierung von der **Datum** Objekt, finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
 Die **Datum** Operator implementiert, wenn die `COleDateTime` Objektsatz ist auf Null. Finden Sie unter [COleDateTime relationale Operatoren](#coledatetime_relational_operators) ein Beispiel.  
  
##  <a name="parsedatetime"></a>COleDateTime::ParseDateTime  
 Analysiert eine Zeichenfolge, um einen Datums-/Uhrzeitwert zu lesen.  
  
```
bool ParseDateTime(  
 LPCTSTR lpszDate,
 DWORD dwFlags = 0,
 LCID lcid = LANG_USER_DEFAULT) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpszDate`  
 Ein Zeiger auf die Null-terminierte Zeichenfolge, die analysiert werden soll. Einzelheiten finden Sie unter "Hinweise".  
  
 `dwFlags`  
 Gibt Flags für das Gebietsschema und die Analyse an. Eine oder mehrere der folgenden Flags:  
  
- **LOCALE_NOUSEROVERRIDE** die Systemeinstellungen für Standard-Gebietsschema, anstelle von benutzerdefinierten Einstellungen verwenden.  
  
- **VAR_TIMEVALUEONLY** den Datumsteil während der Analyse ignoriert.  
  
- **VAR_DATEVALUEONLY** Uhrzeitteil während der Analyse ignoriert.  
  
 `lcid`  
 Gibt die Gebietsschema-ID für die Konvertierung an.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** wurde die Zeichenfolge erfolgreich andernfalls in einem Datums-/Uhrzeitwert konvertiert **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Zeichenfolge in einen Datums-/Uhrzeitwert erfolgreich konvertiert wurde Wert ist, wird den Wert dieses `COleDateTime` -Objekts auf diesen Wert und ihren Status auf ungültig festgelegt wird.  
  
> [!NOTE]
>  Werte für Jahreszahlen müssen zwischen 100 und 9999 liegen.  
  
 Die `lpszDate` Parameter kann eine Vielzahl von Formaten annehmen. Beispielsweise enthalten die folgenden Zeichenfolgen zulässige Datum/Uhrzeit-Formate:  
  
 `"25 January 1996"`  
  
 `"8:30:00"`  
  
 `"20:30:00"`  
  
 `"January 25, 1996 8:30:00"`  
  
 `"8:30:00 Jan. 25, 1996"`  
  
 `"1/25/1996 8:30:00"  // always specify the full year, even in a 'short date' format`  
  
 Beachten Sie, dass die Gebietsschema-ID auch beeinflusst, ob das Format der Zeichenfolge für die Konvertierung in einen Datum/Uhrzeit-Wert zulässig ist.  
  
 Im Fall von **VAR_DATEVALUEONLY**, den Zeitpunkt, der Wert auf 0-Zeit oder Mitternacht festgelegt ist. Im Fall von **VAR_TIMEVALUEONLY**, das Datum, bis Datum 0, d. h. am 30. Dezember 1899 Wert festgelegt ist.  
  
 Wenn die Zeichenfolge nicht in einen Datum/Uhrzeit-Wert konvertiert werden konnte oder gab es einem numerischen Überlauf, der Status dieser `COleDateTime` Objekt ist ungültig.  
  
 Weitere Informationen zu den Grenzen und die Implementierung für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="setdate"></a>COleDateTime::SetDate  
 Legt das Datum dieser `COleDateTime` Objekt.  
  
```
int SetDate(  
 int nYear,
 int nMonth,
 int nDay) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nYear`, `nMonth`, `nDay`  
 Geben Sie die Datenkomponenten, die in diese kopiert werden `COleDateTime` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 NULL, wenn der Wert dieses `COleDateTime` Objekt wurde erfolgreich ist, andernfalls 1 festgelegt. Dieser Rückgabewert basiert auf der **DateTimeStatus** Aufzählungstyp. Weitere Informationen finden Sie unter der [SetStatus](#setstatus) Memberfunktion.  
  
### <a name="remarks"></a>Hinweise  
 Das Datum wird auf die angegebenen Werte festgelegt. Die Zeit wird auf die Zeit 0, Mitternacht festgelegt.  
  
 Finden Sie in der folgenden Tabelle werden die Grenzen für die Parameterwerte:  
  
|Parameter|Grenzen|  
|---------------|------------|  
|`nYear`|100 - 9999|  
|`nMonth`|1 - 12|  
|`nDay`|0 - 31|  
  
 Wenn Sie der Tag des Monats überläuft, wird es bis zum richtigen Tag des Monats und den Monat konvertiert und/oder Jahr entsprechend erhöht wird. Ein Tageswert von 0 (null) gibt den letzten Tag des vorherigen Monats an. Das Verhalten ist identisch mit `SystemTimeToVariantTime`.  
  
 Wenn der Date-Wert, der von den Parametern angegebenen nicht gültig ist, wird der Status dieses Objekts auf gesetzt **COleDateTime::invalid**. Verwenden Sie [GetStatus](#getstatus) überprüft die Gültigkeit der **Datum** -Wert und sollten nicht davon ausgehen, die den Wert der [M_dt](#m_dt) bleiben unverändert.  
  
 Hier sind einige Beispiele von Datumswerten:  
  
|`nYear`|`nMonth`|`nDay`|Wert|  
|-------------|--------------|------------|-----------|  
|2000|2|29|29. Februar 2000|  
|1776|7|4|4 Juli 1776|  
|1925|4|35|35 April 1925 (ungültiges Datum)|  
|10000|1|1|1. Januar 10000 (ungültiges Datum)|  
  
 Zum Festlegen von Datum und Uhrzeit finden Sie unter [COleDateTime::SetDateTime](#setdatetime).  
  
 Informationen über Memberfunktionen, die den Wert dieses Abfragen `COleDateTime` Objekt, finden Sie unter den folgenden Member-Funktionen:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 Weitere Informationen über die Grenzen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities#11](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_14.cpp)]  
  
##  <a name="setdatetime"></a>COleDateTime::SetDateTime  
 Legt das Datum und Uhrzeit dieser `COleDateTime` Objekt.  
  
```
int SetDateTime(  
 int nYear,
 int nMonth,
 int nDay,
 int nHour,
 int nMin,
 int nSec) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nYear`, `nMonth`, `nDay`, `nHour`, `nMin`, `nSec`  
 Angeben der Datums- und Zeitkomponenten in diese kopiert werden `COleDateTime` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 NULL, wenn der Wert dieses `COleDateTime` Objekt wurde erfolgreich ist, andernfalls 1 festgelegt. Dieser Rückgabewert basiert auf der **DateTimeStatus** Aufzählungstyp. Weitere Informationen finden Sie unter der [SetStatus](#setstatus) Memberfunktion.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie in der folgenden Tabelle werden die Grenzen für die Parameterwerte:  
  
|Parameter|Grenzen|  
|---------------|------------|  
|`nYear`|100 - 9999|  
|`nMonth`|1 - 12|  
|`nDay`|0 - 31|  
|`nHour`|0 - 23|  
|`nMin`|0 - 59|  
|`nSec`|0 - 59|  
  
 Wenn Sie der Tag des Monats überläuft, wird es bis zum richtigen Tag des Monats und den Monat konvertiert und/oder Jahr entsprechend erhöht wird. Ein Tageswert von 0 (null) gibt den letzten Tag des vorherigen Monats an. Das Verhalten ist identisch mit [SystemTimeToVariantTime](http://msdn.microsoft.com/en-us/d9d69521-9b33-4fc5-8a1c-929f216db450).  
  
 Wenn die Datums- oder Uhrzeitwert fest, die von den Parametern angegebenen ungültig ist, wird der Status dieses Objekts auf "Invalid" und der Wert dieses Objekts festgelegt ist, wird nicht geändert.  
  
 Hier sind einige Beispiele für die Time-Werten:  
  
|`nHour`|`nMin`|`nSec`|Wert|  
|-------------|------------|------------|-----------|  
|1|3|3|01:03:03|  
|23|45|0|23:45:00|  
|25|30|0|Ungültig|  
|9|60|0|Ungültig|  
  
 Hier sind einige Beispiele von Datumswerten:  
  
|`nYear`|`nMonth`|`nDay`|Wert|  
|-------------|--------------|------------|-----------|  
|1995|4|15|15. April 1995|  
|1789|7|14|17 Juli 1789|  
|1925|2|30|Ungültig|  
|10000|1|1|Ungültig|  
  
 Um nur das Datum festzulegen, finden Sie unter [COleDateTime::SetDate](#setdate). Um nur die Uhrzeit festzulegen, finden Sie unter [COleDateTime::SetTime](#settime).  
  
 Informationen über Memberfunktionen, die den Wert dieses Abfragen `COleDateTime` Objekt, finden Sie unter den folgenden Member-Funktionen:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 Weitere Informationen über die Grenzen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetStatus](#getstatus).  
  
##  <a name="setstatus"></a>COleDateTime::SetStatus  
 Legt den Status dieses `COleDateTime` Objekt.  
  
```
void SetStatus(DateTimeStatus status) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *status*  
 Der neue Statuswert für diesen `COleDateTime` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die *Status* Parameterwert wird definiert, indem Sie die **DateTimeStatus** Aufzählungstyp innerhalb definiert ist die `COleDateTime` Klasse. Finden Sie unter [COleDateTime::GetStatus](#getstatus) für Details.  
  
> [!CAUTION]
>  Diese Funktion ist für Situationen, Erweiterte Programmierung. Diese Funktion wird die Daten in dieses Objekt nicht verändert. Es am häufigsten verwendet werden, legen Sie den Status auf `null` oder **ungültige**. Beachten Sie, dass der Zuweisungsoperator ( [Operator =](#eq)) und [SetDateTime](#setdatetime) sollten Sie den Status des Objekts basierend auf der Quelle Werte festlegen.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetStatus](#getstatus).  
  
##  <a name="settime"></a>COleDateTime::SetTime  
 Festlegen der Zeit dieses `COleDateTime` Objekt.  
  
```
int SetTime(  
 int nHour,
 int nMin,
 int nSec) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nHour`, `nMin`, `nSec`  
 Geben Sie die Zeitkomponenten in diese kopiert werden `COleDateTime` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 NULL, wenn der Wert dieses `COleDateTime` Objekt wurde erfolgreich ist, andernfalls 1 festgelegt. Dieser Rückgabewert basiert auf der **DateTimeStatus** Aufzählungstyp. Weitere Informationen finden Sie unter der [SetStatus](#setstatus) Memberfunktion.  
  
### <a name="remarks"></a>Hinweise  
 Die Gültigkeitsdauer wird auf die angegebenen Werte festgelegt. Das Datum wird in Datum 0, d. h. am 30. Dezember 1899 festgelegt.  
  
 Finden Sie in der folgenden Tabelle werden die Grenzen für die Parameterwerte:  
  
|Parameter|Grenzen|  
|---------------|------------|  
|`nHour`|0 - 23|  
|`nMin`|0 - 59|  
|`nSec`|0 - 59|  
  
 Wenn die Zeit, die durch den Parameter angegebene Wert ungültig ist, ist der Status dieses Objekts auf "Invalid" und der Wert dieses Objekts festgelegt ist, wird nicht geändert.  
  
 Hier sind einige Beispiele für die Time-Werten:  
  
|`nHour`|`nMin`|`nSec`|Wert|  
|-------------|------------|------------|-----------|  
|1|3|3|01:03:03|  
|23|45|0|23:45:00|  
|25|30|0|Ungültig|  
|9|60|0|Ungültig|  
  
 Zum Festlegen von Datum und Uhrzeit finden Sie unter [COleDateTime::SetDateTime](#setdatetime).  
  
 Informationen über Memberfunktionen, die den Wert dieses Abfragen `COleDateTime` Objekt, finden Sie unter den folgenden Member-Funktionen:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 Weitere Informationen über die Grenzen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Automatisierungsunterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [SetDate](#setdate).  
  
## <a name="see-also"></a>Siehe auch  
 [COleVariant-Klasse](../../mfc/reference/colevariant-class.md)   
 [CTime-Klasse](../../atl-mfc-shared/reference/ctime-class.md)   
 [CTimeSpan-Klasse](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Freigegebene ATL-/MFC-Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)



