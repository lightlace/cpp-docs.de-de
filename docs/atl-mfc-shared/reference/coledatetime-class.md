---
title: COleDateTime-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDateTime
- ATL.COleDateTime
- ATL::COleDateTime
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
caps.latest.revision: 34
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
ms.openlocfilehash: ecb32876e55c9801b28fefa1a189508ffbc8b78c
ms.lasthandoff: 02/24/2017

---
# <a name="coledatetime-class"></a>COleDateTime-Klasse
Kapselt die `DATE` -Datentyp, der in der OLE-Automatisierung verwendet wird.  
  
## <a name="syntax"></a>Syntax  
  
```
class COleDateTime
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDateTime::COleDateTime](#coledatetime)|Erstellt ein `COleDateTime`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDateTime::Format](#format)|Generiert eine formatierte Zeichenfolge-Darstellung des ein `COleDateTime` Objekt.|  
|[COleDateTime::GetAsDBTIMESTAMP](#getasdbtimestamp)|Rufen Sie diese Methode zum Abrufen der Uhrzeit in der `COleDateTime` -Objekt als ein **DBTIMESTAMP** Datenstruktur.|  
|[COleDateTime::GetAsSystemTime](#getassystemtime)|Rufen Sie diese Methode zum Abrufen der Uhrzeit in der `COleDateTime` -Objekt als ein [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Datenstruktur.|  
|[COleDateTime::GetAsUDATE](#getasudate)|Rufen Sie diese Methode zum Abrufen der Uhrzeit in der `COleDateTime` als ein **Update** Datenstruktur.|  
|[COleDateTime::GetCurrentTime](#getcurrenttime)|Erstellt ein `COleDateTime` -Objekt, das die aktuelle Uhrzeit (statische Memberfunktion) darstellt.|  
|[COleDateTime::GetDay](#getday)|Gibt dem Tag dies `COleDateTime` Objekt darstellt (1-31).|  
|[COleDateTime::GetDayOfWeek](#getdayofweek)|Gibt den Tag der Woche zurück dies `COleDateTime` -Objekt darstellt (Sonntag = 1).|  
|[COleDateTime::GetDayOfYear](#getdayofyear)|Gibt dem Tag des Jahres dies `COleDateTime` -Objekt darstellt (1. Januar = 1).|  
|[COleDateTime::GetHour](#gethour)|Gibt die Stunde dies `COleDateTime` -Objekt darstellt (0-23).|  
|[COleDateTime::GetMinute](#getminute)|Gibt der Minute dies `COleDateTime` -Objekt darstellt (0-59).|  
|[COleDateTime::GetMonth](#getmonth)|Gibt den Monat zurück, das `COleDateTime` Objekt darstellt (1-12).|  
|[COleDateTime::GetSecond](#getsecond)|Gibt der zweite dieser `COleDateTime` -Objekt darstellt (0-59).|  
|[COleDateTime::GetStatus](#getstatus)|Ruft ab, der den Status (Gültigkeit) `COleDateTime` Objekt.|  
|[COleDateTime::GetYear](#getyear)|Gibt dem Jahr dies `COleDateTime` -Objekt darstellt.|  
|[COleDateTime::ParseDateTime](#parsedatetime)|Liest einen Datum/Uhrzeit-Wert aus einer Zeichenfolge und legt den Wert des `COleDateTime`.|  
|[COleDateTime::SetDate](#setdate)|Legt den Wert dieses `COleDateTime` -Objekts auf den angegebenen Wert nur das Datum.|  
|[COleDateTime::SetDateTime](#setdatetime)|Legt den Wert dieses `COleDateTime` -Objekt mit dem angegebenen Datum/Uhrzeit-Wert.|  
|[COleDateTime::SetStatus](#setstatus)|Setzt den Status (Gültigkeit) dieses `COleDateTime` Objekt.|  
|[COleDateTime::SetTime](#settime)|Legt den Wert dieses `COleDateTime` -Objekts auf den angegebenen Wert nur.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  

|Name|Beschreibung|  
|----------|-----------------|  
|[COleDateTime:: Operator == COleDateTime:: Operator<,></,>](#coledatetime_relational_operators)|Vergleicht zwei `COleDateTime` Werte.|  
|[COleDateTime:: Operator +, COleDateTime:: Operator-](#operator_add_-)|Addieren und subtrahieren `COleDateTime` Werte.|  
|[COleDateTime:: Operator +=, COleDateTime:: Operator =](#operator_add_eq_-_eq)|Addition und Subtraktion ein `COleDateTime` Wert aus diesem `COleDateTime` Objekt.|  
|[COleDateTime:: Operator =](#operator_eq)|Kopiert einen `COleDateTime` Wert.|  
|[Datum, COleDateTime:: Operator COleDateTime:: Operator Datum *](#operator_date)|Konvertiert eine `COleDateTime` Wert in einem `DATE` oder `DATE*`.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[COleDateTime::m_dt](#m_dt)|Enthält die zugrunde liegende **Datum** für dieses `COleDateTime` Objekt.|  
|[COleDateTime::m_status](#m_status)|Enthält den Status dieser `COleDateTime` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `COleDateTime`eine Basisklasse keinen.  
  
 Es gibt die möglichen Typen für die [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) -Datentyp der OLE-Automatisierung. Ein `COleDateTime` Wert darstellt, ein absolutes Datum und Zeitwert.  
  
 Die `DATE` Typ wird als Gleitkommawert implementiert. Tage werden von dem 30. Dezember 1899 um Mitternacht gemessen. Die folgende Tabelle zeigt einige Daten und die zugehörigen Werte:  
  
|Datum|Wert|  
|----------|-----------|  
|Am 29. Dezember 1899 Mitternacht|-1.0|  
|29. Dezember 1899, 6 Uhr|-1.25|  
|Mitternacht am 30. Dezember 1899|0.0|  
|Am 31. Dezember 1899 Mitternacht|1.0|  
|1. Januar 1900, 6 Uhr|2.25|  
  
> [!CAUTION]
>  Beachten Sie, obwohl Werte für Tag vor dem 30. Dezember 1899 Mitternacht negativ Zeit des Tages Werte nicht in der obigen Tabelle. 6:00 Uhr wird z. B. immer durch einen Teilwert 0,25, unabhängig davon, ob die ganze Zahl, die den Tag darstellt (nach dem 30. Dezember 1899) positiv oder negativ (vor dem 30. Dezember 1899) dargestellt. Dies bedeutet, dass ein einfacher floating Point-Vergleich fälschlicherweise sortieren würde eine `COleDateTime` für 6:00 auf 12/29/1899 als **später** , die als 7:00 Uhr am selben Tag darstellt.  
  
 Die `COleDateTime` Klasse behandelt Datumsangaben zwischen dem 1. Januar 100 bis zum 31. Dezember 9999. Die `COleDateTime` Klasse verwendet den gregorianischen Kalender; julianischen wird nicht unterstützt. `COleDateTime`Sommerzeit wird ignoriert. (Siehe [Datum und Uhrzeit: Benutzeroberflächenautomatisierungs-Unterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).)  
  
> [!NOTE]
>  Sie können die `%y` Format, um eine zweistellige Jahresangabe nur für Datumsangaben, die beginnend am 1900 abzurufen. Bei Verwendung der `%y` Format auf ein Datum vor 1900 der Code generiert einen Assertionsfehler.  
  
 Dieser Typ wird auch verwendet, um nur das Datum oder Uhrzeit nur Werte darzustellen. Gemäß der Konvention das Datum 0 (30. Dezember 1899) wird nur Werte verwendet, und die Uhrzeit 00:00 (Mitternacht) wird für reine Werte verwendet.  
  
 Bei der Erstellung einer `COleDateTime` Objekt ein Datum mit weniger als 100 ist, ist das Datum akzeptiert, aber nachfolgende Aufrufe von `GetYear`, `GetMonth`, `GetDay`, `GetHour`, `GetMinute`, und `GetSecond` fehl und gibt-1 zurück. Früher konnten Sie zweistellige Datumsangaben verwenden, aber Datumsangaben muss 100 oder größer in MFC 4.2 und höher.  
  
 Um Probleme zu vermeiden, geben Sie ein vierstelliges Datum. Zum Beispiel:  
  
 [!code-cpp[NVC_ATLMFC_Utilities&#1;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_1.cpp)]  
  
 Grundlegende arithmetische Operationen für die `COleDateTime` Werte verwenden der Begleitklasse [COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md). `COleDateTimeSpan`definieren ein bestimmten Zeitintervalls. Die Beziehung zwischen diesen Klassen ist ähnlich dem zwischen [CTime](../../atl-mfc-shared/reference/ctime-class.md) und [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md).  
  
 Weitere Informationen zu den `COleDateTime` und `COleDateTimeSpan` -Klassen finden Sie im Artikel [Datum und Uhrzeit: Benutzeroberflächenautomatisierungs-Unterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ATLComTime.h  
  
##  <a name="a-namecoledatetimerelationaloperatorsa--coledatetime-relational-operators"></a><a name="coledatetime_relational_operators"></a>COleDateTime relationale Operatoren  
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
 Die **COleDateTime** Objekt verglichen werden soll.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Ein ATLASSERT treten auf, wenn eine der beiden Operanden ist ungültig.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#13;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_2.cpp)]  
  
### <a name="example"></a>Beispiel  
 The operators **>=**, **\<=**, **>**, and **<**, will assert if the `COleDateTime` object is set to null.  
  
 [!code-cpp[NVC_ATLMFC_Utilities&#170;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_3.cpp)]  
  
##  <a name="a-namecoledatetimea--coledatetimecoledatetime"></a><a name="coledatetime"></a>COleDateTime::COleDateTime  
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
 Eine vorhandene **VARIANT** Datenstruktur (möglicherweise eine `COleVariant` Objekt), um einen Datums-/Uhrzeitwert konvertiert werden soll ( `VT_DATE`) und kopiert Sie in die neue `COleDateTime` Objekt.  
  
 `dtSrc`  
 Ein Datum/Uhrzeit ( **Datum**) Wert in die neue kopiert werden `COleDateTime` Objekt.  
  
 `timeSrc`  
 Ein `time_t` oder **__time64_t** Wert in einen Datum/Uhrzeit-Wert konvertiert und in die neue kopiert `COleDateTime` Objekt.  
  
 *systimeSrc*  
 Ein `SYSTEMTIME` Struktur in einen Datum/Uhrzeit-Wert konvertiert und in die neue kopiert `COleDateTime` Objekt.  
  
 `filetimeSrc`  
 Ein `FILETIME` Struktur in einen Datum/Uhrzeit-Wert konvertiert und in die neue kopiert `COleDateTime` Objekt. Beachten Sie, dass `FILETIME` verwendet die koordinierte Weltzeit (UTC), sodass, wenn Sie eine lokale Zeit in die Struktur übergeben, die Ergebnisse falsch. Finden Sie unter [Dateizeiten](http://msdn.microsoft.com/library/windows/desktop/ms724290) in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Informationen.  
  
 `nYear`, `nMonth`, `nDay`, `nHour`, `nMin`, `nSec`  
 Geben Sie die Werte für Datum und Uhrzeit in die neue kopiert werden `COleDateTime` Objekt.  
  
 `wDosDate`, `wDosTime`  
 MS-DOS-Datum und Uhrzeit-Werte in einen Datum/Uhrzeit-Wert konvertiert und in die neue kopiert `COleDateTime` Objekt.  
  
 `dbts`  
 Ein Verweis auf eine [DBTimeStamp](https://msdn.microsoft.com/library/system.data.oledb.oledbtype) Struktur, die die aktuelle lokale Zeit enthält.  
  
### <a name="remarks"></a>Hinweise  
 Alle diese Konstruktoren Erstellen neuer `COleDateTime` Objekte, die mit dem angegebenen Wert initialisiert. Die folgende Tabelle zeigt die gültigen Bereiche für die einzelnen Komponenten für Datum und Uhrzeit:  
  
|Datum/Uhrzeit-Komponente|Gültiger Bereich|  
|--------------------------|-----------------|  
|Jahr|100 – 9999|  
|Monat|0 – 12|  
|Tag|0 – 31|  
|Stunde|0 – 23|  
|Minute|0 – 59|  
|second|0 – 59|  
  
 Hinweis, der die tatsächliche Obergrenze für die Tageskomponente variiert basierend auf den Monat und Jahr Komponenten. Weitere Informationen finden Sie unter der **SetDate** oder `SetDateTime` Memberfunktionen.  
  
 Es folgt eine kurze Beschreibung jeder Konstruktor:  
  
- `COleDateTime(`**)** Erstellt ein `COleDateTime` -Objekt auf 0 (Mitternacht, 30. Dezember 1899) initialisiert.  
  
- `COleDateTime(``dateSrc` **)** Erstellt eine `COleDateTime` -Objekt aus einem vorhandenen `COleDateTime` Objekt.  
  
- `COleDateTime(`*VarSrc* **)** erstellt ein `COleDateTime` Objekt. Versucht, Konvertieren einer `VARIANT` Struktur oder [COleVariant](../../mfc/reference/colevariant-class.md) Objekt, das ein Datum/Uhrzeit ( `VT_DATE`) Wert. Wenn die Konvertierung erfolgreich ist, wird der konvertierte Wert in die neue kopiert `COleDateTime` Objekt. Ist dies nicht der Fall, den Wert der `COleDateTime` -Objekts auf 0 (Mitternacht, 30. Dezember 1899) und ihren Status auf ungültige festgelegt wird.  
  
- `COleDateTime(``dtSrc` **)** Erstellt eine `COleDateTime` -Objekt aus einer **Datum** Wert.  
  
- `COleDateTime(``timeSrc` **)** Erstellt eine `COleDateTime` -Objekt aus einem `time_t` Wert.  
  
- `COleDateTime(`*SystimeSrc* **)** erstellt eine `COleDateTime` -Objekt aus einem `SYSTEMTIME` Wert.  
  
- `COleDateTime(``filetimeSrc` **)** Erstellt eine `COleDateTime` -Objekt aus einem `FILETIME` Wert. . Beachten Sie, dass `FILETIME` verwendet die koordinierte Weltzeit (UTC), sodass, wenn Sie eine lokale Zeit in die Struktur übergeben, die Ergebnisse falsch. Finden Sie unter [Dateizeiten](http://msdn.microsoft.com/library/windows/desktop/ms724290) in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Informationen.  
  
- `COleDateTime(``nYear`, `nMonth`, `nDay`, `nHour`, `nMin`, `nSec` **)** Erstellt ein `COleDateTime` Objekt aus den angegebenen numerischen Werten.  
  
- `COleDateTime(``wDosDate`, `wDosTime` **)** Erstellt ein `COleDateTime` Objekt aus den angegebenen Werten von MS-DOS-Datum und Uhrzeit.  
  
 Weitere Informationen zu den `time_t` -Datentyp finden Sie unter der [Zeit](../../c-runtime-library/reference/time-time32-time64.md) -Funktion in der *Run-Time Library Reference*.  
  
 Weitere Informationen finden Sie unter der [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) und [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) Strukturen in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen über die Grenzen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Benutzeroberflächenautomatisierungs-Unterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
> [!NOTE]
>  Der Konstruktor mit **DBTIMESTAMP** Parameter ist nur verfügbar, wenn OLEDB.h enthalten ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#2;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_4.cpp)]  
  
##  <a name="a-nameformata--coledatetimeformat"></a><a name="format"></a>COleDateTime::Format  
 Erstellt eine formatierte Darstellung der Datum/Uhrzeit-Wert.  
  
```
CString Format(DWORD dwFlags = 0,  LCID lcid = LANG_USER_DEFAULT) const;
CString Format(LPCTSTR lpszFormat) const;
CString Format(UINT nFormatID) const;
```  
  
### <a name="parameters"></a>Parameter  
 `dwFlags`  
 Gibt an, um eine der folgenden Gebietsschemas:  
  
- `LOCALE_NOUSEROVERRIDE`Verwenden Sie anstelle von benutzerdefinierten Einstellungen der standardmäßige Gebietsschema des Systems.  
  
- `VAR_TIMEVALUEONLY`Ignorieren Sie den Datumsteil während der Analyse.  
  
- `VAR_DATEVALUEONLY`Der Zeitteil während der Analyse zu ignorieren.  
  
 `lcid`  
 Gibt die Gebietsschema-ID für die Konvertierung an. Weitere Informationen zu Sprachen-IDs finden Sie unter [Sprachbezeichner](http://msdn.microsoft.com/library/windows/desktop/dd318691).  
  
 `lpszFormat`  
 Eine Formatierungszeichenfolge ähnelt der `printf` Formatierungszeichenfolge. Jede Formatierung von Code, einen Prozentsatz vorangestellt ( `%`) anmelden, wird von der entsprechenden ersetzt `COleDateTime` Komponente. Andere Zeichen in der Formatierungszeichenfolge werden in der zurückgegebenen Zeichenfolge unverändert kopiert. Finden Sie die Laufzeitfunktion [Strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) Weitere Informationen. Der Wert und die Bedeutung der Formatierungscodes für `Format` sind:  
  
- `%H`Stunden in den aktuellen Tag  
  
- `%M`In der aktuellen Stunde Minuten  
  
- `%S`Sekunden in der aktuellen minute  
  
- `%%`Prozentzeichen  
  
 `nFormatID`  
 Die Ressourcen-ID für die Format-Zeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` , den formatierte Datum/Uhrzeit-Wert enthält.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Status dieser `COleDateTime` Objekt ist null, der Rückgabewert ist eine leere Zeichenfolge. Wenn der Status ungültig ist, wird die zurückgegebene Zeichenfolge durch die Zeichenfolgenressource angegeben `ATL_IDS_DATETIME_INVALID`.  
  
 Eine kurze Beschreibung der drei Formen für diese Funktion folgt:  
  
 `Format`( `dwFlags`, `lcid`)  
 Dieses Formular formatiert den Wert für Datum und Uhrzeit mit den Sprachspezifikationen (Gebietsschema-IDs). Mit den Standardparametern, wird das Datum und die Uhrzeit, Drucken des Formulars, wenn der Zeitteil 0 (Mitternacht ist), in diesem Fall nur das Datum drucken wird oder der Datumsteil 0 (30. Dezember 1899 ist) in diesem Fall nur die Zeit angezeigt wird. Wenn der Datum/Uhrzeit-Wert 0 (am 30. Dezember 1899 Mitternacht) ist, wird dieses Formular mit den Standardparametern Mitternacht gedruckt.  
  
 `Format`( `lpszFormat`)  
 Dieses Formular formatiert den Wert mit der Formatzeichenfolge mit speziellen Formatcodes, die ein Prozentzeichen (%) vorangestellt werden, wie in `printf`. Die Formatierungszeichenfolge wird als Parameter an die Funktion übergeben. Weitere Informationen zu den Formatierungscodes, finden Sie unter [Strftime Wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) in der Run-Time Library Reference.  
  
 `Format`( `nFormatID`)  
 Dieses Formular formatiert den Wert mit der Formatzeichenfolge mit speziellen Formatcodes, die ein Prozentzeichen (%) vorangestellt werden, wie in `printf`. Die Formatierungszeichenfolge ist eine Ressource. Die ID dieser Zeichenfolgenressource wird als Parameter übergeben. Weitere Informationen zu den Formatierungscodes, finden Sie unter [Strftime Wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) in der *Run-Time Library Reference*.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&3;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_5.cpp)]  
  
##  <a name="a-namegetasdbtimestampa--coledatetimegetasdbtimestamp"></a><a name="getasdbtimestamp"></a>COleDateTime::GetAsDBTIMESTAMP  
 Rufen Sie diese Methode zum Abrufen der Uhrzeit in der `COleDateTime` -Objekt als ein **DBTIMESTAMP** Datenstruktur.  
  
```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `dbts`  
 Ein Verweis auf eine [DBTimeStamp](https://msdn.microsoft.com/library/system.data.oledb.oledbtype) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Speichert die resultierende Uhrzeit in der referenzierten `dbts`-Struktur. Die **DBTIMESTAMP** -Datenstruktur, die von dieser Funktion initialisiert haben die **Bruch** Member auf&0; (null) festgelegt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&4;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_6.cpp)]  
  
##  <a name="a-namegetassystemtimea--coledatetimegetassystemtime"></a><a name="getassystemtime"></a>COleDateTime::GetAsSystemTime  
 Rufen Sie diese Methode zum Abrufen der Uhrzeit in der `COleDateTime` -Objekt als ein `SYSTEMTIME` -Datenstruktur.  
  
```
bool GetAsSystemTime(SYSTEMTIME& sysTime) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 *sysTime*  
 Ein Verweis auf eine [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Struktur zum Empfangen der konvertierte Datums-/Uhrzeitwert aus der `COleDateTime` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** bei Erfolg; **false** , wenn die Konvertierung fehlschlägt oder die `COleDateTime` Objekt **NULL** oder ist ungültig.  
  
### <a name="remarks"></a>Hinweise  
 `GetAsSystemTime`Speichert die resultierende Zeit in der referenzierten *SysTime* Objekt. Die `SYSTEMTIME` -Datenstruktur, die von dieser Funktion initialisiert haben die **wMilliseconds** Element auf&0; (null) gesetzt.  
  
 Finden Sie unter [GetStatus](#getstatus) für Weitere Informationen auf den Statusinformationen im gehalten ein `COleDateTime` Objekt.  
  
##  <a name="a-namegetasudatea--coledatetimegetasudate"></a><a name="getasudate"></a>COleDateTime::GetAsUDATE  
 Rufen Sie diese Methode zum Abrufen der Uhrzeit in der `COleDateTime` -Objekt als ein **Update** Datenstruktur.  
  
```
bool GetAsUDATE(UDATE& udate) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 `udate`  
 Ein Verweis auf eine **Update** Struktur zum Empfangen der konvertierte Datums-/Uhrzeitwert aus der `COleDateTime` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** bei Erfolg; **false** , wenn die Konvertierung fehlschlägt oder die `COleDateTime` Objekt **NULL** oder ist ungültig.  
  
### <a name="remarks"></a>Hinweise  
 Ein **Update** Struktur ein "lose" Datum darstellt.  
  
##  <a name="a-namegetcurrenttimea--coledatetimegetcurrenttime"></a><a name="getcurrenttime"></a>COleDateTime::GetCurrentTime  
 Rufen Sie diese statischen Member-Funktion, um das aktuelle Datum/Uhrzeit-Wert zurück.  
  
```
static COleDateTime WINAPI GetCurrentTime() throw();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&5;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_7.cpp)]  
  
##  <a name="a-namegetdaya--coledatetimegetday"></a><a name="getday"></a>COleDateTime::GetDay  
 Ruft den Tag des Monats, dargestellt durch diesen Datums-und Uhrzeitwert.  
  
```
int GetDay() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Tag des Monats, dargestellt durch den Wert dieses `COleDateTime` Objekt oder `COleDateTime::error` , wenn der Tag nicht abgerufen werden konnte.  
  
### <a name="remarks"></a>Hinweise  
 Gültige Rückgabewerte Bereich zwischen 1 und 31.  
  
 Informationen zu anderen Memberfunktionen, die den Wert dieser Abfragen `COleDateTime` Objekt, das die folgenden Memberfunktionen:  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&6;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_8.cpp)]  
  
##  <a name="a-namegetdayofweeka--coledatetimegetdayofweek"></a><a name="getdayofweek"></a>COleDateTime::GetDayOfWeek  
 Ruft den Tag des Monats, dargestellt durch diesen Datums-und Uhrzeitwert.  
  
```
int GetDayOfWeek() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Tag des Wochentags, dargestellt durch den Wert dieses `COleDateTime` Objekt oder `COleDateTime::error` , wenn der Tag der Woche konnte nicht abgerufen werden.  
  
### <a name="remarks"></a>Hinweise  
 Gültige Rückgabe Werte liegen zwischen 1 und 7, wobei 1 = Sonntag 2 = Montag und so weiter.  
  
 Informationen zu anderen Memberfunktionen, die den Wert dieser Abfragen `COleDateTime` Objekt, das die folgenden Memberfunktionen:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#7;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_9.cpp)]  
  
##  <a name="a-namegetdayofyeara--coledatetimegetdayofyear"></a><a name="getdayofyear"></a>COleDateTime::GetDayOfYear  
 Ruft den Tag des Jahres durch diesen Wert für Datum und Uhrzeit dargestellt.  
  
```
int GetDayOfYear() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Tag des Jahres den Wert dieses `COleDateTime` Objekt oder `COleDateTime::error` , wenn der Tag des Jahres konnte nicht abgerufen werden.  
  
### <a name="remarks"></a>Hinweise  
 Gültige Rückgabe Werte liegen im Bereich zwischen 1 und 366, 1. Januar = 1.  
  
 Informationen zu anderen Memberfunktionen, die den Wert dieser Abfragen `COleDateTime` Objekt, das die folgenden Memberfunktionen:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#8;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_10.cpp)]  
  
##  <a name="a-namegethoura--coledatetimegethour"></a><a name="gethour"></a>COleDateTime::GetHour  
 Ruft ab, der durch diesen Wert für Datum und Uhrzeit dargestellte Stunde angezeigt.  
  
```
int GetHour() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Stunde, dargestellt durch den Wert dieses `COleDateTime` Objekt oder `COleDateTime::error` , wenn die Stunde konnte nicht abgerufen werden.  
  
### <a name="remarks"></a>Hinweise  
 Gültige Rückgabewerte Bereich zwischen 0 und 23.  
  
 Informationen zu anderen Memberfunktionen, die den Wert dieser Abfragen `COleDateTime` Objekt, das die folgenden Memberfunktionen:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#9;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_11.cpp)]  
  
##  <a name="a-namegetminutea--coledatetimegetminute"></a><a name="getminute"></a>COleDateTime::GetMinute  
 Ruft die Minute, die durch diesen Wert für Datum und Uhrzeit dargestellt.  
  
```
int GetMinute() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Minute, dargestellt durch den Wert dieses `COleDateTime` Objekt oder `COleDateTime::error` , wenn die Minute konnte nicht abgerufen werden.  
  
### <a name="remarks"></a>Hinweise  
 Gültige Rückgabewerte Bereich zwischen 0 und 59.  
  
 Informationen zu anderen Memberfunktionen, die den Wert dieser Abfragen `COleDateTime` Objekt, das die folgenden Memberfunktionen:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetHour](#gethour).  
  
##  <a name="a-namegetmontha--coledatetimegetmonth"></a><a name="getmonth"></a>COleDateTime::GetMonth  
 Ruft den Monat durch diesen Wert für Datum und Uhrzeit dargestellt.  
  
```
int GetMonth() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Monats, dargestellt durch den Wert dieses `COleDateTime` Objekt oder `COleDateTime::error` Wenn Monats nicht abgerufen werden konnte.  
  
### <a name="remarks"></a>Hinweise  
 Gültige Rückgabewerte Bereich zwischen 1 und 12.  
  
 Informationen zu anderen Memberfunktionen, die den Wert dieser Abfragen `COleDateTime` Objekt, das die folgenden Memberfunktionen:  
  
- [GetDay](#getday)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetDay](#getday).  
  
##  <a name="a-namegetseconda--coledatetimegetsecond"></a><a name="getsecond"></a>COleDateTime::GetSecond  
 Ruft das zweite durch diesen Wert für Datum und Uhrzeit dargestellt.  
  
```
int GetSecond() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die zweite, dargestellt durch den Wert dieses `COleDateTime` Objekt oder `COleDateTime::error` , wenn die zweite konnte nicht abgerufen werden.  
  
### <a name="remarks"></a>Hinweise  
 Gültige Rückgabewerte Bereich zwischen 0 und 59.  
  
> [!NOTE]
>  Die `COleDateTime` -Klasse Schaltsekunden nicht unterstützt.  
  
 Weitere Informationen zur Implementierung für `COleDateTime`, finden Sie im Artikel [Datum und Uhrzeit: Benutzeroberflächenautomatisierungs-Unterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
 Informationen zu anderen Memberfunktionen, die den Wert dieser Abfragen `COleDateTime` Objekt, das die folgenden Memberfunktionen:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetHour](#gethour).  
  
##  <a name="a-namegetstatusa--coledatetimegetstatus"></a><a name="getstatus"></a>COleDateTime::GetStatus  
 Ruft den Status (Gültigkeit) ab einer bestimmten `COleDateTime` Objekt.  
  
```
DateTimeStatus GetStatus() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Status dieses `COleDateTime` Wert. Wenn Sie aufrufen **GetStatus** auf ein `COleDateTime` Objekt erstellt, mit dem Standardwert, wird zurückgegeben, die gültig. Wenn Sie aufrufen **GetStatus** auf eine `COleDateTime` -Objekt mit dem Konstruktor auf null initialisiert **GetStatus** gibt null zurück. Finden Sie unter **Hinweise** Weitere Informationen.  
  
### <a name="remarks"></a>Hinweise  
 Der Rückgabewert wird definiert, indem die **DateTimeStatus** -Enumerationstyp definiert ist die `COleDateTime` Klasse.  
  
 `enum DateTimeStatus`  
  
 `{`  
  
 `error = -1,`  
  
 `valid = 0,`  
  
 `invalid = 1,    // Invalid date (out of range, etc.)`  
  
 `null = 2,       // Literally has no value`  
  
 `};`  
  
 Eine kurze Beschreibung dieser Status-Werte finden Sie in der folgenden Liste:  
  
- `COleDateTime::error`Gibt an, dass beim Versuch, die Teil der Datum/Uhrzeit-Wert zu erhalten, ist ein Fehler aufgetreten.  
  
- **COleDateTime::valid** gibt an, dass diese `COleDateTime` -Objekt gültig ist.  
  
- **COleDateTime::invalid** gibt an, dass diese `COleDateTime` Objekt ist ungültig; d. h. möglicherweise der Wert falsch.  
  
- **COleDateTime::null** gibt an, dass diese `COleDateTime` Objekt null ist, d. h., dass für dieses Objekt kein Wert angegeben wurde. (Dies ist "null", in dem Sinne Datenbank mit"kein Wert" im Gegensatz zu C++ **NULL**.)  
  
 Der Status einer `COleDateTime` Objekt ist ungültig, in den folgenden Fällen:  
  
-   Wenn der Wert, von gesetzt wird einer **VARIANT** oder `COleVariant` -Wert, der nicht in einen Datum/Uhrzeit-Wert konvertiert werden konnte.  
  
-   Wenn der Wert, von gesetzt wird einem `time_t`, `SYSTEMTIME`, oder `FILETIME` -Wert, der nicht in einen gültigen Datum/Zeit-Wert konvertiert werden konnte.  
  
-   Wenn der Wert, wird festgelegt ist `SetDateTime` mit ungültigen Parameterwerten.  
  
-   Wenn dieses Objekt einen Überlauf oder Unterlauf während eines Zuweisungsvorgangs arithmetische nämlich aufgetreten `+=` oder `-=`.  
  
-   Wenn ein ungültiger Wert für dieses Objekt zugewiesen wurde.  
  
-   Wenn der Status des Objekts explizit festgelegt wurde, um ungültige mit `SetStatus`.  
  
 Weitere Informationen zu den Vorgängen, die den Status ungültig, finden Sie unter den folgenden Memberfunktionen festgelegt werden können:  
  
- [COleDateTime](#coledatetime)  
  
- [SetDateTime](#setdatetime)  
  
- [Operator +, -](#operator_add_-)  
  
- [Operator +=, =](#operator_add_eq_-_eq)  
  
 Weitere Informationen über die Grenzen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Benutzeroberflächenautomatisierungs-Unterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#10;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_12.cpp)]  
  
##  <a name="a-namegetyeara--coledatetimegetyear"></a><a name="getyear"></a>COleDateTime::GetYear  
 Ruft das Jahr durch diesen Wert für Datum und Uhrzeit dargestellt.  
  
```
int GetYear() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert dieses Jahres `COleDateTime` Objekt oder `COleDateTime::error` , wenn das Jahr konnte nicht abgerufen werden.  
  
### <a name="remarks"></a>Hinweise  
 Gültige Rückgabewerte Bereich zwischen 100 und 9999, das Jahrhundert gehört.  
  
 Informationen zu anderen Memberfunktionen, die den Wert dieser Abfragen `COleDateTime` Objekt, das die folgenden Memberfunktionen:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 Weitere Informationen über die Grenzen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Benutzeroberflächenautomatisierungs-Unterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetDay](#getday).  
  
##  <a name="a-namemdta--coledatetimemdt"></a><a name="m_dt"></a>COleDateTime::m_dt  
 Die zugrunde liegende **Datum** Struktur für dieses `COleDateTime` Objekt.  
  
```
DATE m_dt;
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!CAUTION]
>  Ändern den Wert in der **Datum** Objekt Zugriff auf die von dieser Funktion zurückgegebenen Zeiger ändert sich den Wert dieses `COleDateTime` Objekt. Er ändert nicht den Status dieses `COleDateTime` Objekt.  
  
 Weitere Informationen zur Implementierung von der **Datum** Objekt, finden Sie im Artikel [Datum und Uhrzeit: Benutzeroberflächenautomatisierungs-Unterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="a-namemstatusa--coledatetimemstatus"></a><a name="m_status"></a>COleDateTime::m_status  
 Enthält den Status dieser `COleDateTime` Objekt.  
  
```
DateTimeStatus m_status;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ der Datenmember ist der Enumerationstyp **DateTimeStatus**, definiert in der `COleDateTime` Klasse. Finden Sie unter [COleDateTime::GetStatus](#getstatus) Details.  
  
> [!CAUTION]
>  Dieses Datenelement ist für die Erweiterte Programmierung Situationen. Verwenden Sie die Inline-Memberfunktionen [GetStatus](#getstatus) und [SetStatus](#setstatus). Finden Sie unter `SetStatus` Weitere Warnhinweise in Bezug auf dieses Datenelement explizit festlegen.  
  
##  <a name="a-nameoperatoreqa--coledatetimeoperator-"></a><a name="operator_eq"></a>COleDateTime:: Operator =  
 Kopiert einen `COleDateTime` Wert.  
  
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
 Diese überladenen Zuweisungsoperatoren Kopieren der Quelle Datums-/Uhrzeitwert in diesen `COleDateTime` Objekt. Eine kurze Beschreibung jeder dieser überladen Zuweisung Operatoren folgt:  
  
- **Operator = (** `dateSrc` **)** den Wert und den Status des Operanden werden in diese kopiert `COleDateTime` Objekt.  
  
- **Operator = (** *VarSrc* **)** Wenn die Konvertierung von der [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) Wert (oder [COleVariant](../../mfc/reference/colevariant-class.md) Objekt), einen Datums-/Uhrzeitwert ( `VT_DATE`) wird erfolgreich ist, wird der konvertierte Wert in diese kopiert `COleDateTime` Objekt und seinen Status zu gültigen festgelegt ist. Wenn die Konvertierung nicht erfolgreich ist, wird der Wert dieses Objekts auf 0 (null) (am 30. Dezember 1899 Mitternacht) festgelegt und dessen Status ungültig.  
  
- **Operator = (** `dtSrc` **)** der **Datum** Wert wird in diese kopiert `COleDateTime` Objekt und seinen Status zu gültigen festgelegt ist.  
  
- **Operator = (** `timeSrc` **)** der `time_t` oder **__time64_t** Wert konvertiert und in diese kopiert `COleDateTime` Objekt. Wenn die Konvertierung erfolgreich ist, wird der Status dieses Objekts auf gültig festgelegt; Falls dies nicht gelingt, festgelegt wird, ungültig.  
  
- **Operator = (** *SystimeSrc* **)** der [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) Wert konvertiert und in diese kopiert `COleDateTime` Objekt. Wenn die Konvertierung erfolgreich ist, wird der Status dieses Objekts auf gültig festgelegt; Falls dies nicht gelingt, festgelegt wird, ungültig.  
  
- **Operator = (** `udate` **)** der **Update** Wert konvertiert und in diese kopiert `COleDateTime` Objekt. Wenn die Konvertierung erfolgreich ist, wird der Status dieses Objekts auf gültig festgelegt; Falls dies nicht gelingt, festgelegt wird, ungültig. Ein **Update** Struktur ein "lose" Datum darstellt. Finden Sie unter [VarDateFromUdate](http://msdn.microsoft.com/en-us/1c924ac5-b896-49e1-9ccf-825ac7a030c8) Weitere Details.  
  
- **Operator = (** `filetimeSrc` **)** der [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) Wert konvertiert und in diese kopiert `COleDateTime` Objekt. Wenn die Konvertierung erfolgreich ist, wird der Status dieses Objekts auf gültig festgelegt; Andernfalls wird festgelegt, ungültig. `FILETIME`Koordinierte Weltzeit (UTC) verwendet, wenn Sie eine UTC-Zeit in der Struktur übergeben, die Ergebnisse von UTC-Zeit in die Ortszeit konvertiert und als variant Zeit gespeichert werden. Dieses Verhalten ist in Visual C++ 6.0 und Visual C++ .NET 2003 SP2 identisch. Finden Sie unter [Dateizeiten](http://msdn.microsoft.com/library/windows/desktop/ms724290) in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Weitere Informationen.  
  
 Weitere Informationen finden Sie unter der [VARIANT](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) Eintrag in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen zu den `time_t` -Datentyp finden Sie unter der [Zeit](../../c-runtime-library/reference/time-time32-time64.md) -Funktion in der *Run-Time Library Reference*.  
  
 Weitere Informationen finden Sie unter der [SYSTEMTIME](http://msdn.microsoft.com/library/windows/desktop/ms724950) und [FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284) Strukturen in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen über die Grenzen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Benutzeroberflächenautomatisierungs-Unterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="a-nameoperatoradd-a--coledatetimeoperator---"></a><a name="operator_add_-"></a>COleDateTime:: Operator +, -  
 Addieren und subtrahieren **ColeDateTime** Werte.  
  
```
COleDateTime operator+(COleDateTimeSpan dateSpan) const throw();
COleDateTime operator-(COleDateTimeSpan dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTime& date) const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 `COleDateTime`-Objekte stellen die absolute Zeiten dar. [COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md) Objekte repräsentieren die relative Häufigkeit. Die ersten beiden Operatoren können Sie von Addition und Subtraktion ein `COleDateTimeSpan` Wert aus einem `COleDateTime` Wert. Der dritte Operator können Sie eine subtrahieren `COleDateTime` Wert von einem anderen ergeben einen `COleDateTimeSpan` Wert.  
  
 Wenn einer der Operanden null ist, ist den Status der resultierenden `COleDateTime` Wert ist null.  
  
 Wenn die resultierende `COleDateTime` Wert liegt außerhalb des zulässigen Werte, der Status dieser `COleDateTime` -Wert ist ungültig.  
  
 Wenn die Operanden ist ungültig, und der andere nicht null ist Operand, den Status der resultierenden `COleDateTime` Wert ist ungültig.  
  
 Die ** + ** und ** - ** Operatoren überprüft, wenn die `COleDateTime` wird auf Null. Finden Sie unter [COleDateTime relationale Operatoren](#coledatetime_relational_operators) ein Beispiel.  
  
 Weitere Informationen zu den gültig, ungültig und null-Status-Werte, finden Sie unter der [M_status](#m_status) Membervariablen gespeichert.  
  
 Weitere Informationen über die Grenzen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Benutzeroberflächenautomatisierungs-Unterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#12;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_13.cpp)]  
  
##  <a name="a-nameoperatoraddeq-eqa--coledatetimeoperator---"></a><a name="operator_add_eq_-_eq"></a>COleDateTime:: Operator +=, =  
 Addition und Subtraktion ein **ColeDateTime** Wert aus diesem `COleDateTime` Objekt.  
  
```
COleDateTime& operator+=(COleDateTimeSpan dateSpan) throw();
COleDateTime& operator-=(COleDateTimeSpan dateSpan) throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Operatoren ermöglichen es Ihnen, Addition und Subtraktion ein `COleDateTimeSpan` Wert aus diesem `COleDateTime`. Wenn einer der Operanden null ist, ist den Status der resultierenden `COleDateTime` Wert ist null.  
  
 Wenn die resultierende `COleDateTime` Wert liegt außerhalb des zulässigen Werte, der den Status `COleDateTime` festgelegt ist, ungültig.  
  
 Wenn die Operanden ist ungültig und andere nicht null ist, den Status der resultierenden `COleDateTime` Wert ist ungültig.  
  
 Weitere Informationen zu den gültig, ungültig und null-Status-Werte, finden Sie unter der [M_status](#m_status) Membervariablen gespeichert.  
  
 Die ** += ** und ** -= ** Operatoren überprüft, wenn die `COleDateTime` wird auf Null. Finden Sie unter [COleDateTime relationale Operatoren](#coledatetime_relational_operators) ein Beispiel.  
  
 Weitere Informationen über die Grenzen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Benutzeroberflächenautomatisierungs-Unterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="a-nameoperatordatea--coledatetimeoperator-date"></a><a name="operator_date"></a>COleDateTime:: Operator Datum  
 Konvertiert eine **ColeDateTime** Wert in einem **Datum**.  
  
```
operator DATE() const throw();
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator gibt einen **Datum** Objekt, dessen Wert aus diesem kopiert `COleDateTime` Objekt. Weitere Informationen zur Implementierung von der **Datum** Objekt, finden Sie im Artikel [Datum und Uhrzeit: Benutzeroberflächenautomatisierungs-Unterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
 Die **Datum** Operator überprüft, wenn die `COleDateTime` wird auf Null. Finden Sie unter [COleDateTime relationale Operatoren](#coledatetime_relational_operators) ein Beispiel.  
  
##  <a name="a-nameparsedatetimea--coledatetimeparsedatetime"></a><a name="parsedatetime"></a>COleDateTime::ParseDateTime  
 Analysiert eine Zeichenfolge, um ein Datum/Uhrzeit-Wert zu lesen.  
  
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
 Gibt Flags für Gebietsschema und analysieren. Eine oder mehrere der folgenden Flags:  
  
- **LOCALE_NOUSEROVERRIDE** Gebietsschema Standardeinstellungen des Systems statt mit dem benutzerdefinierten Einstellungen verwenden.  
  
- **VAR_TIMEVALUEONLY** den Datumsteil während der Analyse ignoriert.  
  
- **VAR_DATEVALUEONLY** Uhrzeitteil während der Analyse ignoriert.  
  
 `lcid`  
 Gibt die Gebietsschema-ID für die Konvertierung an.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **true** wurde die Zeichenfolge erfolgreich andernfalls in einen Datums-/Uhrzeitwert konvertiert **false**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Zeichenfolge erfolgreich in einen Datums-/Uhrzeitwert konvertiert wurde Wert ist, wird den Wert dieses `COleDateTime` -Objekts auf dieses Werts und ihren Status auf gültig festgelegt wird.  
  
> [!NOTE]
>  Werte müssen zwischen 100 und 9999 liegen.  
  
 Die `lpszDate` Parameter kann eine Vielzahl von Formaten haben. Beispielsweise enthalten die folgenden Zeichenfolgen zulässige Datum/Uhrzeit-Formate:  
  
 `"25 January 1996"`  
  
 `"8:30:00"`  
  
 `"20:30:00"`  
  
 `"January 25, 1996 8:30:00"`  
  
 `"8:30:00 Jan. 25, 1996"`  
  
 `"1/25/1996 8:30:00"  // always specify the full year,`  
  
 `// even in a 'short date' format`  
  
 Beachten Sie, dass die Gebietsschema-ID auch beeinflussen, ob das Format für die Konvertierung in einen Datum/Uhrzeit-Wert zulässig ist.  
  
 Im Fall von **VAR_DATEVALUEONLY**, zu dem Wert Zeit 0 oder Mitternacht festgelegt ist. Im Fall von **VAR_TIMEVALUEONLY**das Datum, bis Datum 0, d. h. am 30. Dezember 1899 Wert festgelegt ist.  
  
 Wenn die Zeichenfolge nicht in einen Datum/Uhrzeit-Wert konvertiert werden kann oder ob es einem numerischen Überlauf, der den Status `COleDateTime` Objekt ist ungültig.  
  
 Weitere Informationen über die Grenzen und die Implementierung für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Benutzeroberflächenautomatisierungs-Unterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
##  <a name="a-namesetdatea--coledatetimesetdate"></a><a name="setdate"></a>COleDateTime::SetDate  
 Legt das Datum dieser `COleDateTime` Objekt.  
  
```
int SetDate(  
 int nYear,
 int nMonth,
 int nDay) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nYear`, `nMonth`, `nDay`  
 Geben Sie die Datumskomponenten in diese kopiert werden `COleDateTime` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 NULL, wenn der Wert dieses `COleDateTime` Objekt festgelegt wurde erfolgreich ist, andernfalls 1. Dieser Wert basiert auf der **DateTimeStatus** Enumerationstyps. Weitere Informationen finden Sie unter der [SetStatus](#setstatus) Member-Funktion.  
  
### <a name="remarks"></a>Hinweise  
 Das Datum wird auf die angegebenen Werte festgelegt. Die Zeit wird Zeit 0, Mitternacht festgelegt.  
  
 Finden Sie in der folgenden Tabelle für die Grenzen für die Parameterwerte:  
  
|Parameter|Grenzen|  
|---------------|------------|  
|`nYear`|100 – 9999|  
|`nMonth`|1 – 12|  
|`nDay`|0 – 31|  
  
 Wenn der Tag des Monats überläuft, wird es in den richtigen Tag des nächsten Monats und des Monats konvertiert und/oder Jahr entsprechend erhöht wird. Ein Tageswert&0; (null) gibt den letzten Tag des vorherigen Monats. Das Verhalten ist identisch mit `SystemTimeToVariantTime`.  
  
 Wenn der Date-Wert, der von den Parametern angegebenen nicht gültig ist, wird der Status dieses Objekts auf festgelegt **COleDateTime::invalid**. Verwenden Sie [GetStatus](#getstatus) zur Überprüfung die Gültigkeit von der **Datum** -Wert und sollten nicht davon ausgehen, die den Wert der [M_dt](#m_dt) bleiben unverändert.  
  
 Hier sind einige Beispiele von Datumswerten:  
  
|`nYear`|`nMonth`|`nDay`|Wert|  
|-------------|--------------|------------|-----------|  
|2000|2|29|29. Februar 2000|  
|1776|7|4|4 Juli 1776|  
|1925|4|35|35 April 1925 (ungültiges Datum)|  
|10000|1|1|1. Januar 10000 (ungültiges Datum)|  
  
 Zum Festlegen von Datum und Uhrzeit finden Sie unter [COleDateTime::SetDateTime](#setdatetime).  
  
 Informationen zum Member-Funktionen, die den Wert dieser Abfragen `COleDateTime` Objekt, das die folgenden Memberfunktionen:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 Weitere Informationen über die Grenzen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Benutzeroberflächenautomatisierungs-Unterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATLMFC_Utilities&#11;](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_14.cpp)]  
  
##  <a name="a-namesetdatetimea--coledatetimesetdatetime"></a><a name="setdatetime"></a>COleDateTime::SetDateTime  
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
 Angeben der Datums- und Uhrzeitkomponenten in diese kopiert werden `COleDateTime` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 NULL, wenn der Wert dieses `COleDateTime` Objekt festgelegt wurde erfolgreich ist, andernfalls 1. Dieser Wert basiert auf der **DateTimeStatus** Enumerationstyps. Weitere Informationen finden Sie unter der [SetStatus](#setstatus) Member-Funktion.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie in der folgenden Tabelle für die Grenzen für die Parameterwerte:  
  
|Parameter|Grenzen|  
|---------------|------------|  
|`nYear`|100 – 9999|  
|`nMonth`|1 – 12|  
|`nDay`|0 – 31|  
|`nHour`|0 – 23|  
|`nMin`|0 – 59|  
|`nSec`|0 – 59|  
  
 Wenn der Tag des Monats überläuft, wird es in den richtigen Tag des nächsten Monats und des Monats konvertiert und/oder Jahr entsprechend erhöht wird. Ein Tageswert&0; (null) gibt den letzten Tag des vorherigen Monats. Das Verhalten entspricht dem [SystemTimeToVariantTime](http://msdn.microsoft.com/en-us/d9d69521-9b33-4fc5-8a1c-929f216db450).  
  
 Wenn der Datums- oder Uhrzeitwert fest, die von den Parametern angegebenen ungültig ist, den Status des Objekts ungültig und der Wert des Objekts festgelegt ist, wird nicht geändert.  
  
 Hier sind einige Beispiele für Time-Werte:  
  
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
  
 Informationen zum Member-Funktionen, die den Wert dieser Abfragen `COleDateTime` Objekt, das die folgenden Memberfunktionen:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 Weitere Informationen über die Grenzen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Benutzeroberflächenautomatisierungs-Unterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetStatus](#getstatus).  
  
##  <a name="a-namesetstatusa--coledatetimesetstatus"></a><a name="setstatus"></a>COleDateTime::SetStatus  
 Legt den Status dieses `COleDateTime` Objekt.  
  
```
void SetStatus(DateTimeStatus status) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *status*  
 Der neue Statuswert für diesen `COleDateTime` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die *Status* Parameterwert wird definiert, indem die **DateTimeStatus** -Enumerationstyp definiert ist die `COleDateTime` Klasse. Finden Sie unter [COleDateTime::GetStatus](#getstatus) Details.  
  
> [!CAUTION]
>  Diese Funktion ist für die Erweiterte Programmierung Situationen. Diese Funktion werden die Daten in diesem Objekt nicht geändert. Dieser wird am häufigsten verwendet, legen Sie den Status auf `null` oder **ungültige**. Beachten Sie, dass der Zuweisungsoperator ( [Operator =](#eq)) und [SetDateTime](#setdatetime) sollten Sie den Status des Objekts basierend auf der Quelle Werte festlegen.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [GetStatus](#getstatus).  
  
##  <a name="a-namesettimea--coledatetimesettime"></a><a name="settime"></a>COleDateTime::SetTime  
 Legt das Zeitintervall dieses `COleDateTime` Objekt.  
  
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
 NULL, wenn der Wert dieses `COleDateTime` Objekt festgelegt wurde erfolgreich ist, andernfalls 1. Dieser Wert basiert auf der **DateTimeStatus** Enumerationstyps. Weitere Informationen finden Sie unter der [SetStatus](#setstatus) Member-Funktion.  
  
### <a name="remarks"></a>Hinweise  
 Die Zeit wird auf die angegebenen Werte festgelegt. Das Datum wird in Datum 0, d. h. am 30. Dezember 1899 festgelegt.  
  
 Finden Sie in der folgenden Tabelle für die Grenzen für die Parameterwerte:  
  
|Parameter|Grenzen|  
|---------------|------------|  
|`nHour`|0 – 23|  
|`nMin`|0 – 59|  
|`nSec`|0 – 59|  
  
 Wenn die Zeit, die durch den Parameter angegebene Wert nicht gültig ist, wird der Status des Objekts ungültig und der Wert dieses Objekts festgelegt ist, wird nicht geändert.  
  
 Hier sind einige Beispiele für Time-Werte:  
  
|`nHour`|`nMin`|`nSec`|Wert|  
|-------------|------------|------------|-----------|  
|1|3|3|01:03:03|  
|23|45|0|23:45:00|  
|25|30|0|Ungültig|  
|9|60|0|Ungültig|  
  
 Zum Festlegen von Datum und Uhrzeit finden Sie unter [COleDateTime::SetDateTime](#setdatetime).  
  
 Informationen zum Member-Funktionen, die den Wert dieser Abfragen `COleDateTime` Objekt, das die folgenden Memberfunktionen:  
  
- [GetDay](#getday)  
  
- [GetMonth](#getmonth)  
  
- [GetYear](#getyear)  
  
- [GetHour](#gethour)  
  
- [GetMinute](#getminute)  
  
- [GetSecond](#getsecond)  
  
- [GetDayOfWeek](#getdayofweek)  
  
- [GetDayOfYear](#getdayofyear)  
  
 Weitere Informationen über die Grenzen für `COleDateTime` Werte finden Sie im Artikel [Datum und Uhrzeit: Benutzeroberflächenautomatisierungs-Unterstützung](../../atl-mfc-shared/date-and-time-automation-support.md).  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [SetDate](#setdate).  
  
## <a name="see-also"></a>Siehe auch  
 [COleVariant-Klasse](../../mfc/reference/colevariant-class.md)   
 [CTime-Klasse](../../atl-mfc-shared/reference/ctime-class.md)   
 [CTimeSpan-Klasse](../../atl-mfc-shared/reference/ctimespan-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [ATL/MFC-freigegeben Klassen](../../atl-mfc-shared/atl-mfc-shared-classes.md)




