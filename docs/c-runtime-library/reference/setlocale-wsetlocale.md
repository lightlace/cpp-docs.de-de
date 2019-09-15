---
title: setlocale, _wsetlocale
ms.date: 11/04/2016
api_name:
- _wsetlocale
- setlocale
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wsetlocale
- _tsetlocale
- setlocale
helpviewer_keywords:
- wsetlocale function
- setlocale function
- tsetlocale function
- locales, defining
- _tsetlocale function
- defining locales
- _wsetlocale function
ms.assetid: 3ffb684e-5990-4202-9553-b5339af9520d
ms.openlocfilehash: 375b1de82f72447d7e41b051c2aa1307716fb0dd
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948243"
---
# <a name="setlocale-_wsetlocale"></a>setlocale, _wsetlocale

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

Wenn ein gültiges Gebiets Schema und eine gültige *Kategorie* angegeben werden, gibt einen Zeiger auf die Zeichenfolge zurück, die *dem angegebenen Gebiets* *Schema und der* angegebenen *Kategorie*zugeordnet ist Wenn das Gebiets *Schema oder die* *Kategorie* ungültig ist, wird ein NULL-Zeiger zurückgegeben, und die aktuellen Gebiets Schema Einstellungen des Programms werden nicht geändert.

Beispiel: Der Aufruf

```C
setlocale( LC_ALL, "en-US" );
```

legt alle Kategorien fest und gibt nur folgende Zeichenfolge zurück

```Output
en-US
```

Sie können die von **setlocale** zurückgegebene Zeichenfolge kopieren, um diesen Teil der Gebiets Schema Informationen des Programms wiederherzustellen. Globaler oder lokaler Thread Speicher wird für die von **setlocale**zurückgegebene Zeichenfolge verwendet. Spätere Aufrufe von **setlocale** überschreiben die Zeichenfolge, wodurch die von früheren Aufrufen zurückgegebenen Zeichen folgen Zeiger ungültig werden.

## <a name="remarks"></a>Hinweise

Verwenden Sie die **setlocale** -Funktion, um einige oder alle der aktuellen Programm Gebiets Schema Informationen festzulegen, zu ändern oder abzufragen, die durch Gebiets Schema und *Kategorie* *angegeben werden.* *locale* bezieht sich auf den Ort (Land/Region und Sprache), für den Sie bestimmte Aspekte des Programms anpassen können. Vom Gebietsschema abhängig sind u. a. Datumsformat und Währungsformat. Wenn Sie das Gebiets Schema auf die Standard Zeichenfolge für eine Sprache festlegen, die mehrere Formulare auf dem Computer unterstützt, sollten Sie den Rückgabewert **setlocale** überprüfen, *um festzustellen* , welche Sprache wirksam ist. Wenn Sie z. b. *locale* auf "Chinesisch" festlegen, kann der Rückgabewert entweder "Chinesisch-vereinfacht" oder "Chinesisch (traditionell)" lauten.

**_wsetlocale** ist eine breit Zeichen Version von **setlocale**; Das Gebiets Schema Argument *und der Rückgabe* Wert von **_wsetlocale** sind Zeichen folgen mit breit Zeichen. **_wsetlocale** und **setlocale** Verhalten sich andernfalls identisch.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsetlocale**|**setlocale**|**setlocale**|**_wsetlocale**|

Das *Category* -Argument gibt die Teile der Gebiets Schema Informationen eines Programms an, die betroffen sind. Die für die *Kategorie* verwendeten Makros und die betroffenen Teile des Programms lauten wie folgt:

|*kategorieflag*|Betrifft|
|-|-|
| **LC_ALL** | Alle unten aufgeführten Kategorien. |
| **LC_COLLATE** | Die Funktionen "", "_stricoll", " **wcscoll**", " **_wcsicoll** **", "** **", "** **_strncoll**", " **_strnicoll**", " **_wcsncoll**", " **_wcsnicoll**" und " **wcsxfrm** |
| **LC_CTYPE** | Die Funktionen zur Zeichen Behandlung (außer **IsDigit**, **isxdigit**, **mbstowcs**und **mbtowc**, die nicht betroffen sind). |
| **LC_MONETARY** | Informationen zur monetären Formatierung, die von der **localeconv** -Funktion zurückgegeben werden. |
| **LC_NUMERIC** | Ein Dezimaltrennzeichen für die formatierten Ausgaberoutinen (z. **b. printf**), für die Daten Konvertierungs Routinen und für die nicht monetären Formatierungsinformationen, die von **localeconv**zurückgegeben werden. Neben dem Dezimaltrennzeichen legt **LC_NUMERIC** das Tausender Trennzeichen und die Zeichenfolge für die Gruppierungs Steuerung fest, die von [localeconv](localeconv.md)zurückgegeben wurde. |
| **LC_TIME** | Die Funktionen " **Strauch Zeit** " und " **WCSF Time** ". |

Diese Funktion überprüft den Kategorienparameter. Wenn es sich bei dem Kategorienparameter um keinen der Werte handelt, die in der vorherigen Tabelle angegeben sind, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, legt die Funktion **errno** auf **EINVAL** fest und gibt **null**zurück.

Das *locale* -Argument ist ein Zeiger auf eine Zeichenfolge, die das Gebiets Schema angibt. Weitere Informationen zum *Format des Gebiets Schema Arguments finden* Sie unter Gebiets Schema [Namen, Sprachen und Länder-](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)/regionszeichenfolgen. Wenn *locale* auf eine leere Zeichenfolge zeigt, ist das Gebietsschema die durch die Implementierung definierte native Umgebung. Der Wert **C** gibt die minimale ANSI-konforme Umgebung für die C-Übersetzung an. Das **C** -Gebiets Schema geht davon aus, dass alle **char** -Datentypen 1 Byte sind und ihr Wert immer kleiner als 256 ist.

Zum Programmstart wird die Entsprechung der folgenden Anweisung ausgeführt:

`setlocale( LC_ALL, "C" );`

Das *locale* -Argument kann einen Gebiets Schema Namen, eine Sprachen Zeichenfolge, eine Sprachen Zeichenfolge und Länder-/Regionscode, eine Codepage oder eine Sprachen Zeichenfolge, einen Länder-/Regionscode und eine Codepage annehmen. Der Satz verfügbarer Gebietsschemanamen, Sprachen, Länder-/Regionscodes und Codepages umfasst alle diejenigen, die von der Windows NLS API unterstützt werden, ausgenommen Codepages, die mehr als zwei Bytes pro Zeichen benötigen, wie z. B. UTF-7 und UTF-8. Wenn Sie den Codepage-Wert UTF-7 oder UTF-8 bereitstellen, schlägt **setlocale** fehl und gibt **null**zurück. Der von **setlocale** unterstützte Satz von Gebiets Schema Namen wird in Gebiets Schema [Namen, Sprachen und Zeichen folgen für Länder/Regionen](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)beschrieben. Die von **setlocale** unterstützten sprach-und Länder-/regionszeichenfolgen werden in [sprach](../../c-runtime-library/language-strings.md) Zeichenfolgen und Zeichen folgen für [Länder/Regionen](../../c-runtime-library/country-region-strings.md)aufgeführt. Wie empfehlen die Gebietsschema-Namensform aus Gründen der Leistung und leichteren Verwaltung von Gebietsschema-Zeichenfolgen, die in Code eingebettet sind oder für den Speicher serialisiert sind. Es ist weniger wahrscheinlich, dass Gebietsschema-Zeichenfolgen durch eine Betriebssystemaktualisierung geändert werden, als dies bei der Namensform für Sprache und Land/Region der Fall ist.

Ein als Gebiets *Schema Argument* übergebener NULL-Zeiger weist **setlocale** an, die internationale Umgebung abzufragen, anstatt sie festzulegen. Wenn das *locale* -Argument ein NULL-Zeiger ist, wird die aktuelle Gebiets Schema Einstellung des Programms nicht geändert. Stattdessen gibt **setlocale** einen Zeiger auf die Zeichenfolge zurück, die der *Kategorie* des aktuellen Gebiets Schemas des Threads zugeordnet ist. Wenn das *Category* -Argument **LC_ALL**ist, gibt die Funktion eine Zeichenfolge zurück, die die aktuelle Einstellung der einzelnen Kategorien durch Semikolons trennt. Beispiel: Die Reihenfolge der Aufrufe

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

Dabei handelt es sich um die Zeichenfolge, die der Kategorie **LC_ALL** zugeordnet ist.

Die folgenden Beispiele beziehen sich auf die Kategorie **LC_ALL** . Jede der Zeichenfolgen „.OCP" und „.ACP" kann anstelle einer Codepageseitenzahl verwendet werden, um jeweils die voreingestellte OEM-Benutzercodepage und die voreingestellte ANSI-Benutzercodepage anzugeben.

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

   Legt das Gebiets Schema auf die Sprache, das Land/die Region und die Codepage fest, die vom  *\<sprach >* ,  *\<Land >* und  *\<der >* Zeichen folgen "Codepage" angegeben werden. Sie können verschiedene Kombinationen von Sprache, Land/Region und Codepage verwenden. Bei diesem Aufruf wird beispielsweise das Gebetsschema auf Französisch (Kanada) festgelegt, mit der Codepage 1252:

   `setlocale( LC_ALL, "French_Canada.1252" );`

   Bei diesem Aufruf wird das Gebietsschema auf Französisch (Kanada) mit der voreingestellten ANSI-Codepage festgelegt:

   `setlocale( LC_ALL, "French_Canada.ACP" );`

   Bei diesem Aufruf wird das Gebietsschema auf Französisch (Kanada) mit der voreingestellten OEM-Codepage festgelegt:

   `setlocale( LC_ALL, "French_Canada.OCP" );`

- `setlocale( LC_ALL, "<language>" );`

   Legt das Gebietsschema auf die Sprache fest, die von *\<Sprache>* angegeben wird, und verwendet das Standardland bzw. die Standardregion für die angegebene Sprache sowie die vom Hostbetriebssystem abgerufene voreingestellte ANSI-Benutzercodepage für das Land/die Region. Beispielsweise sind die folgenden Aufrufe von **setlocale** funktional äquivalent:

   `setlocale( LC_ALL, "en-US" );`

   `setlocale( LC_ALL, "English" );`

   `setlocale( LC_ALL, "English_United States.1252" );`

   Aus Leistungsgründen und wegen der Wartbarkeit wird die erste Form empfohlen.

- `setlocale( LC_ALL, ".<code_page>" );`

   Legt die Codepage auf den Wert fest, der durch *<Codepage>* angegeben ist, wobei zugleich das Standardland bzw. die Standardregion und Sprache (gemäß der Definition vom Hostbetriebssystem) für die angegebene Codepage verwendet wird.

Die Kategorie muss entweder **LC_ALL** oder **LC_CTYPE** sein, damit eine Änderung der Codepage wirksam wird. Wenn z. b. das Standardland bzw. die Standard Region und die Sprache des Host Betriebssystems "USA" und "Englisch" sind, sind die folgenden beiden Aufrufe von **setlocale** funktional äquivalent:

`setlocale( LC_ALL, ".1252" );`

`setlocale( LC_ALL, "English_United States.1252");`

Weitere Informationen finden Sie unter [setlocale](../../preprocessor/setlocale.md)-Pragmadirektive in der [C/C++-Präprozessorreferenz](../../preprocessor/c-cpp-preprocessor-reference.md).

Die Funktion [_configthreadlocale](configthreadlocale.md) wird verwendet, um zu steuern, ob **setlocale** das Gebiets Schema aller Threads in einem Programm oder nur das Gebiets Schema des aufrufenden Threads beeinflusst.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
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

    // Enable per-thread locale causes all subsequent locale
    // setting changes in this thread to only affect this thread.
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

[Gebietsschema-Namen, Sprachen und Zeichenfolgen für Länder und Regionen](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
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
