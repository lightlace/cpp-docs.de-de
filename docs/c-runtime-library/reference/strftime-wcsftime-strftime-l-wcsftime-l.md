---
title: strftime, wcsftime, _strftime_l, _wcsftime_l
ms.date: 03/22/2018
apiname:
- strftime
- _wcsftime_l
- _strftime_l
- wcsftime
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tcsftime
- strftime
- wcsftime
- _strftime_l
- _wcsftime_l
helpviewer_keywords:
- _strftime_l function
- strftime function
- tcsftime function
- _wcsftime_l function
- wcsftime function
- _tcsftime function
- time strings
ms.assetid: 6330ff20-4729-4c4a-82af-932915d893ea
ms.openlocfilehash: 932a7827ef61a5e111f86f8bc44291827843b76e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353838"
---
# <a name="strftime-wcsftime-strftimel-wcsftimel"></a>strftime, wcsftime, _strftime_l, _wcsftime_l

Formatieren einer Zeitzeichenfolge

## <a name="syntax"></a>Syntax

```C
size_t strftime(
   char *strDest,
   size_t maxsize,
   const char *format,
   const struct tm *timeptr
);
size_t _strftime_l(
   char *strDest,
   size_t maxsize,
   const char *format,
   const struct tm *timeptr,
   _locale_t locale
);
size_t wcsftime(
   wchar_t *strDest,
   size_t maxsize,
   const wchar_t *format,
   const struct tm *timeptr
);
size_t _wcsftime_l(
   wchar_t *strDest,
   size_t maxsize,
   const wchar_t *format,
   const struct tm *timeptr,
   _locale_t locale
);
```

### <a name="parameters"></a>Parameter

*strDest*<br/>
Ausgabezeichenfolge.

*maxsize*<br/>
Größe der *StrDest* -Puffers in Zeichen (**Char** oder **"wchar_t"**).

*format*<br/>
Formatsteuerzeichenfolge.

*timeptr*<br/>
**TM** Datenstruktur.

*locale*<br/>
Das zu verwendende Gebietsschema.

## <a name="return-value"></a>Rückgabewert

**Strftime** gibt die Anzahl der Zeichen in platziert *StrDest* und **Wcsftime** gibt Sie die entsprechende Anzahl von Breitzeichen zurück.

Wenn die Gesamtanzahl von Zeichen, einschließlich abschließende Null ist mehr als *Maxsize*, beide **Strftime** und **Wcsftime** 0 zurück, und den Inhalt der  *StrDest* sind unbestimmt.

Die Anzahl der Zeichen in *StrDest* ist gleich der Anzahl von Literalzeichen in *Format* sowie aller Zeichen, die hinzugefügt werden, möglicherweise *Format* über Formatierungscodes. Das abschließende NULL-Zeichen einer Zeichenfolge wird nicht im Rückgabewert berücksichtigt.

## <a name="remarks"></a>Hinweise

Die **Strftime** und **Wcsftime** Formatieren der **tm** -Zeitwert in *Timeptr* gemäß der bereitgestellten  *Format* -Argument und speichern das Ergebnis im Puffer *StrDest*. Höchstens *Maxsize* Zeichen befinden sich in der Zeichenfolge. Eine Beschreibung der Felder in der *Timeptr* Struktur, siehe [Asctime](asctime-wasctime.md). **Wcsftime** entspricht der Breitzeichen- **Strftime**; die Zeichenfolgenargument zeigt auf eine Zeichenfolge mit Breitzeichen. Anderenfalls verhalten sich diese Funktionen identisch.

Diese Funktion überprüft ihre Parameter. Wenn *StrDest*, *Format*, oder *Timeptr* ein null-Zeiger ist oder wenn die **tm** Datenstruktur adressiert werden, indem *Timeptr* ist ungültig (z. B., wenn er aus der Werte für Uhrzeit oder Datum enthält), oder wenn die *Format* Zeichenfolge enthält einen ungültigen Formatierungscode, Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, die Funktion gibt 0 zurück und legt **Errno** zu **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsftime**|**strftime**|**strftime**|**wcsftime**|

Die *Format* -Argument besteht aus, der einen oder mehrere Codes; wie in **Printf**, vorangestellt Formatierungscodes ein Prozentzeichen (**%**). Zeichen, die nicht mit beginnen **%** beim Übertragungsvorgang kopiert werden unverändert in *StrDest*. Die **LC_TIME** -Kategorie des aktuellen Gebietsschemas wirkt sich auf die ausgabeformatierung von **Strftime**. (Weitere Informationen zu **LC_TIME**, finden Sie unter [Setlocale](setlocale-wsetlocale.md).) Die **Strftime** und **Wcsftime** Funktionen verwenden, das derzeit festgelegte Gebietsschema. Die **_strftime_l** und **_wcsftime_l** Versionen dieser Funktionen sind nahezu identisch, außer dass sie das Gebietsschema als Parameter übernehmen und, anstatt des aktuellen verwenden Gebietsschemas. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

Die **Strftime** Funktionen unterstützen diese Formatierungscodes:

|||
|-|-|
|Code|Ersetzungszeichenfolge|
|**%a**|Abgekürzten Wochentagsnamen im Gebietsschema|
|**%A**|Vollen Wochentagsnamen im Gebietsschema|
|**%b**|Abgekürzte monatsbezeichnung im Gebietsschema|
|**%B**|Vollständigen Monatsnamen in das Gebietsschema|
|**%c**|Für das Gebietsschema geeignete Darstellung von Datum und Uhrzeit|
|**%C**|Das Jahr durch 100 dividiert, und klicken Sie auf eine ganze Zahl gekürzt wird, als Dezimalzahl (00−99)|
|**%d**|Tag des Monats als Dezimalzahl (01-31)|
|**%D**|Äquivalent zu **%m/%d/%y**|
|**%e**|Tag des Monats als Dezimalzahl (1-31), in denen einzelne Ziffern durch ein Leerzeichen vorangestellt ist|
|**%F**|Äquivalent zu **%Y-%m-%d.**|
|**%g**|Die letzten 2 Ziffern des ISO 8601-Woche-basierte Jahres als Dezimalzahl (00 - 99)|
|**%G**|Das ISO 8601-Woche-basierte Jahr als Dezimalzahl|
|**%h**|Abgekürzte Name des Monats (Äquivalent zu **%b**)|
|**%H**|Stunde im 24-Stunden-Format (00 - 23)|
|**%I**|Stunde im 12-Stunden-Format (01-12)|
|**%j**|Tag des Jahres als Dezimalzahl (001-366)|
|**%m**|Monat als Dezimalzahl (01-12)|
|**%M**|Minute als Dezimalzahl (00 - 59)|
|**%n**|Ein neue Zeilenumbruchzeichen (**\n**)|
|**%p**|A.M./P.M.-Kennung des Gebietsschemas Indikator für 12-Stunden-Uhr|
|**%r**|Zeit für das Gebietsschema des 12-Stunden-Format|
|**%R**|Äquivalent zu **% H: %M**|
|**%S**|Sekundenangabe als Dezimalzahl (00 - 59)|
|**%t**|Ein horizontales Tabstoppzeichen (**\t**)|
|**%T**|Äquivalent zu **%hh: %mm: %ss**, das ISO 8601-Zeitformat|
|**%u**|ISO 8601-Wochentags als Dezimalzahl (1-7. Montag ist 1)|
|**%U**|Anzahl der Woche des Jahres als Dezimalzahl (00: 53), wobei die erste Sonntag der erste Tag der Woche 1 ist|
|**%V**|Nummer der ISO 8601-Woche als Dezimalzahl (00: 53)|
|**%w**|Wochentag als Dezimalzahl (0 - 6; Sonntag ist 0)|
|**%W**|Anzahl der Woche des Jahres als Dezimalzahl (00: 53), wobei die erste Montag der erste Tag der Woche 1 ist|
|**%x**|Datumsdarstellung für das Gebietsschema|
|**%X**|Uhrzeitdarstellung für das Gebietsschema|
|**%y**|Jahresangabe ohne Jahrhundert als Dezimalzahl (00 - 99)|
|**%Y**|Jahresangabe mit Jahrhundert als Dezimalzahl|
|**%z**|Der Offset von UTC im ISO 8601-Format; keine Zeichen, wenn Zeitzone unbekannt ist|
|**%Z**|Des Gebietsschemas des dreibuchstabiger Zeitzonenname oder Abkürzung der Zeitzone, abhängig von den registrierungseinstellungen; keine Zeichen, wenn Zeitzone unbekannt ist|
|**%%**|Prozentzeichen (%)|

Wie in der **Printf** -Funktion, die **#** Flag möglicherweise Formatierungscode vorangestellt. In diesem Fall wird die Bedeutung des Formatcodes wie folgt geändert.

|Formatcode|Bedeutung|
|-----------------|-------------|
|**%#a**, **%#A**, **%#b**, **%#B**, **%#g**, **%#G**, **%#h**, **%#n**, **%#p**, **%#t**, **%#u**, **%#w**, **%#X**, **%#z**, **%#Z**, **%#%**|**#** Flag wird ignoriert.|
|**%#c**|Lange Datums- / Darstellung, für das Gebietsschema geeignet. Zum Beispiel: "Tuesday, March 14, 1995, 12:41:29".|
|**%#x**|Langes Datumsformat für das Gebietsschema geeignete Darstellung. Zum Beispiel: "Dienstag, 14. März 1995 an".|
|**%#d**, **%#D**, **%#e**, **%#F**, **%#H**, **% #ich**, **%#j**, **%#m**, **%#M**, **%#r**, **%#R**, **%#S**, **%#T** , **%#U**, **%#V**, **%#W**, **%#y**, **%#Y**|Entfernen Sie führende Nullen oder Leerzeichen (sofern vorhanden).|

Das ISO 8601-Woche und das Jahr Woche basierende erzeugten **%V**, **%g**, und **%G**, verwendet eine Woche, die am Montag beginnt, auf dem Woche 1 Woche, an dem 4. Januar, enthält die erste die Woche, die mindestens vier Tage des Jahres enthält. Beim erste Montag des Jahres das 2. ist, sind 3. und 4., die vorherigen Tagen Teil der letzten Woche des vorherigen Jahres. Für diese Tage **%V** wird ersetzt durch 53 und beide **%g** und **%G** ersetzt werden, durch die Ziffern des vorherigen Jahres.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**strftime**|\<time.h>|
|**wcsftime**|\<time.h> oder \<wchar.h>|
|**_strftime_l**|\<time.h>|
|**_wcsftime_l**|\<time.h> oder \<wchar.h>|

Die **_strftime_l** und **_wcsftime_l** Funktionen sind Microsoft-spezifisch. Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Ein Beispiel hierfür finden Sie unter [time](time-time32-time64.md).

## <a name="see-also"></a>Siehe auch

[Locale](../../c-runtime-library/locale.md) <br/>
[Uhrzeitverwaltung](../../c-runtime-library/time-management.md) <br/>
[Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md) <br/>
[localeconv](localeconv.md) <br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md) <br/>
[strcoll-Funktionen](../../c-runtime-library/strcoll-functions.md) <br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
