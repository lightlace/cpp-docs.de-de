---
title: setlocale, _wsetlocale | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wsetlocale
- setlocale
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wsetlocale
- _tsetlocale
- setlocale
dev_langs:
- C++
helpviewer_keywords:
- wsetlocale function
- setlocale function
- tsetlocale function
- locales, defining
- _tsetlocale function
- defining locales
- _wsetlocale function
ms.assetid: 3ffb684e-5990-4202-9553-b5339af9520d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 666cb9954569d4c5bd232f387d63e320af52818a
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2018
ms.locfileid: "34451835"
---
# <a name="setlocale-wsetlocale"></a>setlocale, _wsetlocale

Legt das Laufzeitgebietsschema fest oder ruft es ab.

## <a name="syntax"></a>Syntax

```C
char *setlocale(
   int category,
   const char *locale
);
wchar_t *_wsetlocale(
   int category,
   const wchar_t *locale
);
```

### <a name="parameters"></a>Parameter

*category*<br/>
Vom Gebietsschema betroffene Kategorie.

*locale*<br/>
Gebietsschemaspezifizierer.

## <a name="return-value"></a>Rückgabewert

Wenn Sie eine gültige *Gebietsschema* und *Kategorie* angegeben sind, gibt einen Zeiger auf die Zeichenfolge, die mit dem angegebenen verknüpften *Gebietsschema* und *Kategorie*. Wenn die *Gebietsschema* oder *Kategorie* ist nicht gültig ist, wird ein null-Zeiger und die aktuellen gebietsschemaeinstellungen des Programms werden nicht geändert.

Beispiel: Der Aufruf

```C
setlocale( LC_ALL, "en-US" );
```

legt alle Kategorien fest und gibt nur folgende Zeichenfolge zurück

```Output
en-US
```

Sie können die zurückgegebene Zeichenfolge kopieren **Setlocale** um diesen Teil der Gebietsschemainformation des Programms wiederherzustellen. Global oder Thread lokaler Speicher wird verwendet, für die zurückgegebene Zeichenfolge **Setlocale**. Spätere Aufrufe von **Setlocale** überschreiben die Zeichenfolge, die von früheren aufrufen zurückgegebenen Zeichenfolgenzeiger erklärt.

## <a name="remarks"></a>Hinweise

Verwenden der **Setlocale** Funktion festlegen, ändern oder abzufragen, einige oder alle Gebietsschemainformationen des aktuellen Programms gemäß *Gebietsschema* und *Kategorie*. *Gebietsschema* verweist auf den Ort (Land/Region und Sprache), für die Sie bestimmte Aspekte des Programms anpassen können. Vom Gebietsschema abhängig sind u. a. Datumsformat und Währungsformat. Wenn Sie festlegen, *Gebietsschema* um die Standardzeichenfolge für eine Sprache, die mehrere Formulare, die auf Ihrem Computer unterstützt, sollten Sie überprüfen die **Setlocale** Rückgabewert, um festzustellen, welche Sprache wirksam ist. Wenn Sie festlegen, z. B. *Gebietsschema* auf "Chinesisch" konnte der Rückgabewert entweder "Chinesisch-vereinfacht" oder "Chinesisch-traditionell" sein.

**_wsetlocale** ist eine Breitzeichen-Version von **Setlocale**; das *Gebietsschema* Argument- und Rückgabetypen Wert **_wsetlocale** sind Zeichenfolgen mit Breitzeichen. **_wsetlocale** und **Setlocale** Verhalten sich andernfalls identisch.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsetlocale**|**setlocale**|**setlocale**|**_wsetlocale**|

Die *Kategorie* -Argument gibt die Teile der Gebietsschemainformationen eines Programms, die betroffen sind. Die Makros, die zum *Kategorie* und die Teile des Programms sind wie folgt:

|*Kategorie* Flag|Betrifft|
|-|-|
**LC_ALL**|Alle unten aufgeführten Kategorien.
**LC_COLLATE**|Die **Strcoll**, **_stricoll**, **Wcscoll**, **_wcsicoll**, **Strxfrm**, **_ Strncoll**, **_strnicoll**, **_wcsncoll**, **_wcsnicoll**, und **Wcsxfrm** Funktionen.
**LC_CTYPE**|Die Funktionen zur Verarbeitung von Zeichen (mit Ausnahme von **Isdigit**, **Isxdigit**, **Mbstowcs**, und **Mbtowc**, die nicht betroffen sind).
**LC_MONETARY**|Währungsformatierung Informationen zurückgegeben werden, indem Sie die **Localeconv** Funktion.
**LC_NUMERIC**|Dezimaltrennzeichen für die formatierten ausgaberoutinen (wie z. B. **Printf**), für die datenkonvertierungsroutinen und für die nicht monetären Formatierungsinformationen zurückgegebenes **Localeconv**. Neben dem Dezimaltrennzeichen **LC_NUMERIC** legt das Tausendertrennzeichen und die Steuerung von zurückgegebene Zeichenfolge [Localeconv](localeconv.md).
**LC_TIME**|Die **Strftime** und **Wcsftime** Funktionen.

Diese Funktion überprüft den Kategorienparameter. Wenn es sich bei dem Kategorienparameter um keinen der Werte handelt, die in der vorherigen Tabelle angegeben sind, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, setzt der Funktion **Errno** auf **EINVAL** und gibt **NULL**.

Die *Gebietsschema* Argument ist ein Zeiger auf eine Zeichenfolge, die das Gebietsschema angibt. Informationen zum Format von der *Gebietsschema* Argument, finden Sie unter [Gebietsschemanamen, Sprachen und Zeichenfolgen für Länder/Regionen](../../c-runtime-library/locale-names-languages-and-country-region-strings.md). Wenn *locale* auf eine leere Zeichenfolge zeigt, ist das Gebietsschema die durch die Implementierung definierte native Umgebung. Der Wert **C** gibt die minimale Umgebung ANSI-Konformität für die C-Übersetzung an. Die **C** -Gebietsschema geht davon aus, die alle **Char** -Datentypen 1 Byte und werden, die der Wert ist immer kleiner als 256.

Zum Programmstart wird die Entsprechung der folgenden Anweisung ausgeführt:

`setlocale( LC_ALL, "C" );`

Die *Gebietsschema* Argument kann einen Gebietsschemanamen, eine Sprachenzeichenfolge, eine Sprachenzeichenfolge und Länder-/Regionscode, eine Codepage oder eine Sprachenzeichenfolge, Länder-/Regionscode und Codepage zu verwenden. Der Satz verfügbarer Gebietsschemanamen, Sprachen, Länder-/Regionscodes und Codepages umfasst alle diejenigen, die von der Windows NLS API unterstützt werden, ausgenommen Codepages, die mehr als zwei Bytes pro Zeichen benötigen, wie z. B. UTF-7 und UTF-8. Wenn Sie eine Codepage-Wert eines UTF-7 oder UTF-8 bereitstellen **Setlocale** schlägt fehl, Zurückgeben von **NULL**. Die Anzahl von unterstützten Gebietsschemanamen **Setlocale** in beschriebenen [Gebietsschemanamen, Sprachen und Zeichenfolgen für Länder/Regionen](../../c-runtime-library/locale-names-languages-and-country-region-strings.md). Der Satz von Sprache und Land/Region-Zeichenfolgen, die von unterstützt **Setlocale** in aufgelisteten [Sprachenzeichenfolgen](../../c-runtime-library/language-strings.md) und [Länder-/Regionszeichenfolgen](../../c-runtime-library/country-region-strings.md). Wie empfehlen die Gebietsschema-Namensform aus Gründen der Leistung und leichteren Verwaltung von Gebietsschema-Zeichenfolgen, die in Code eingebettet sind oder für den Speicher serialisiert sind. Es ist weniger wahrscheinlich, dass Gebietsschema-Zeichenfolgen durch eine Betriebssystemaktualisierung geändert werden, als dies bei der Namensform für Sprache und Land/Region der Fall ist.

Ein null-Zeiger, die als übergeben der *Gebietsschema* -Argument teilt **Setlocale** anstelle von Abfragen, die internationale Umgebung festlegen. Wenn die *Gebietsschema* Argument ist ein null-Zeiger, die aktuelle gebietsschemaeinstellung des Programms wird nicht geändert. Stattdessen **Setlocale** gibt einen Zeiger auf die Zeichenfolge, die mit zugeordnetem der *Kategorie* des aktuellen threadgebietsschemas. Wenn die *Kategorie* Argument ist **LC_ALL**, die Funktion gibt eine Zeichenfolge, die die aktuelle Einstellung der einzelnen Kategorien, die durch Semikolons getrennte angibt. Beispiel: Die Reihenfolge der Aufrufe

```C
// Set all categories and return "en-US"
setlocale(LC_ALL, "en-US");
// Set only the LC_MONETARY category and return "fr-FR"
setlocale(LC_MONETARY, "fr-FR");
printf("%s\n", setlocale(LC_ALL, NULL));
```

gibt

```Output
LC_COLLATE=en-US;LC_CTYPE=en-US;LC_MONETARY=fr-FR;LC_NUMERIC=en-US;LC_TIME=en-US
```

Dies ist die Zeichenfolge, die mit zugeordnetem der **LC_ALL** Kategorie.

Die folgenden Beispiele beziehen sich auf die **LC_ALL** Kategorie. Jede der Zeichenfolgen „.OCP" und „.ACP" kann anstelle einer Codepageseitenzahl verwendet werden, um jeweils die voreingestellte OEM-Benutzercodepage und die voreingestellte ANSI-Benutzercodepage anzugeben.

- `setlocale( LC_ALL, "" );`

   Legt das Gebietsschema auf den Standardwert fest, der die vom Betriebssystem abgerufene voreingestellte ANSI-Benutzercodepage ist.

- `setlocale( LC_ALL, ".OCP" );`

   Legt das Gebietsschema explizit auf die aktuelle vom Betriebssystem abgerufene voreingestellte OEM-Benutzercodepage fest.

- `setlocale( LC_ALL, ".ACP" );`

   Legt das Gebietsschema auf die vom Betriebssystem abgerufene voreingestellte ANSI-Benutzercodepage fest.

- `setlocale( LC_ALL, "<localename>" );`

   Legt das Gebietsschema auf den Gebietsschemanamen fest, der durch *\<Gebietsschemaname>* angegeben wird.

- `setlocale( LC_ALL, "<language>_<country>" );`

   Legt das Gebietsschema auf die Sprache und das Land/die Region fest, die durch *\<Sprache>* und *\<Land>* angegeben sind, und zwar zusammen mit der vom Hostbetriebssystem abgerufene Standardcodepage.

- `setlocale( LC_ALL, "<language>_<country>.<code_page>" );`

   Legt das Gebietsschema auf Sprache, Land/Region und Codepage angegeben wird, durch die  *\<Sprache >*,  *\<Land >*, und  *\<Codepage >* Zeichenfolgen. Sie können verschiedene Kombinationen von Sprache, Land/Region und Codepage verwenden. Bei diesem Aufruf wird beispielsweise das Gebetsschema auf Französisch (Kanada) festgelegt, mit der Codepage 1252:

   `setlocale( LC_ALL, "French_Canada.1252" );`

   Bei diesem Aufruf wird das Gebietsschema auf Französisch (Kanada) mit der voreingestellten ANSI-Codepage festgelegt:

   `setlocale( LC_ALL, "French_Canada.ACP" );`

   Bei diesem Aufruf wird das Gebietsschema auf Französisch (Kanada) mit der voreingestellten OEM-Codepage festgelegt:

   `setlocale( LC_ALL, "French_Canada.OCP" );`

- `setlocale( LC_ALL, "<language>" );`

   Legt das Gebietsschema auf die Sprache fest, die von *\<Sprache>* angegeben wird, und verwendet das Standardland bzw. die Standardregion für die angegebene Sprache sowie die vom Hostbetriebssystem abgerufene voreingestellte ANSI-Benutzercodepage für das Land/die Region. Z. B. die folgenden Aufrufe von **Setlocale** sind funktional äquivalent:

   `setlocale( LC_ALL, "en-US" );`

   `setlocale( LC_ALL, "English" );`

   `setlocale( LC_ALL, "English_United States.1252" );`

   Aus Leistungsgründen und wegen der Wartbarkeit wird die erste Form empfohlen.

- `setlocale( LC_ALL, ".<code_page>" );`

   Legt die Codepage auf den Wert fest, der durch *<Codepage>* angegeben ist, wobei zugleich das Standardland bzw. die Standardregion und Sprache (gemäß der Definition vom Hostbetriebssystem) für die angegebene Codepage verwendet wird.

Die Kategorie muss entweder **LC_ALL** oder **LC_CTYPE** auf eine Änderung der Codepage wirksam. Beispielsweise, wenn die standardmäßige Land/Region und Sprache des Host-Betriebssystem "USA" und "Englisch" sind, die folgenden beiden Aufrufe von **Setlocale** sind funktional äquivalent:

`setlocale( LC_ALL, ".1252" );`

`setlocale( LC_ALL, "English_United States.1252");`

Weitere Informationen finden Sie unter [setlocale](../../preprocessor/setlocale.md)-Pragmadirektive in der [C/C++-Präprozessorreferenz](../../preprocessor/c-cpp-preprocessor-reference.md).

Die Funktion [_configthreadlocale](configthreadlocale.md) wird verwendet, um zu steuern, ob **Setlocale** wirkt sich auf das Gebietsschema aller Threads in einem Programm oder nur das Gebietsschema des aufrufenden Threads.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**setlocale**|\<locale.h>|
|**_wsetlocale**|\<locale.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

```C
// crt_setlocale.c
//
// This program demonstrates the use of setlocale when
// using two independent threads.
//

#include <locale.h>
#include <process.h>
#include <windows.h>
#include <stdio.h>
#include <time.h>

#define BUFF_SIZE 100

// Retrieve the date in the current
// locale's format.
int get_date(unsigned char* str)
{
    __time64_t ltime;
    struct tm  thetime;

    // Retrieve the current time
    _time64(&ltime);
    _gmtime64_s(&thetime, &ltime);

    // Format the current time structure into a string
    // "%#x" is the long date representation in the
    // current locale
    if (!strftime((char *)str, BUFF_SIZE, "%#x",
                  (const struct tm *)&thetime))
    {
        printf("strftime failed!\n");
        return -1;
    }
    return 0;
}

// This thread sets its locale to the argument
// and prints the date.
uintptr_t __stdcall SecondThreadFunc( void* pArguments )
{
    unsigned char str[BUFF_SIZE];
    char * locale = (char *)pArguments;

    // Set the thread locale
    printf("The thread locale is now set to %s.\n",
           setlocale(LC_ALL, locale));

    // Retrieve the date string from the helper function
    if (get_date(str) == 0)
    {
        printf("The date in %s locale is: '%s'\n", locale, str);
    }

    _endthreadex( 0 );
    return 0;
}

// The main thread sets the locale to English
// and then spawns a second thread (above) and prints the date.
int main()
{
    HANDLE          hThread;
    unsigned        threadID;
    unsigned char   str[BUFF_SIZE];

    // Configure per-thread locale to cause all subsequently created
    // threads to have their own locale.
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);

    // Set the locale of the main thread to US English.
    printf("The thread locale is now set to %s.\n",
           setlocale(LC_ALL, "en-US"));

    // Create the second thread with a German locale.
    // Our thread function takes an argument of the locale to use.
    hThread = (HANDLE)_beginthreadex( NULL, 0, &SecondThreadFunc,
                                      "de-DE", 0, &threadID );

    if (get_date(str) == 0)
    {
        // Retrieve the date string from the helper function
        printf("The date in en-US locale is: '%s'\n\n", str);
    }

    // Wait for the created thread to finish.
    WaitForSingleObject( hThread, INFINITE );

    // Destroy the thread object.
    CloseHandle( hThread );
}
```

```Output
The thread locale is now set to en-US.
The time in en-US locale is: 'Wednesday, May 12, 2004'

The thread locale is now set to de-DE.
The time in de-DE locale is: 'Mittwoch, 12. Mai 2004'
```

## <a name="see-also"></a>Siehe auch

[Gebietsschemanamen, Sprachen und Zeichenfolgen für Länder/Regionen](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[_configthreadlocale](configthreadlocale.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
[Locale](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[strcoll-Funktionen](../../c-runtime-library/strcoll-functions.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
