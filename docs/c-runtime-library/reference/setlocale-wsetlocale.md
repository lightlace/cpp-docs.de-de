---
title: setlocale, _wsetlocale | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 04a391a99f673d02f01d35681b1d375f5db09384
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="setlocale-wsetlocale"></a>setlocale, _wsetlocale
Legt das Laufzeitgebietsschema fest oder ruft es ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
char *setlocale(  
   int category,  
   const char *locale   
);  
wchar_t *_wsetlocale(  
   int category,  
   const wchar_t *locale   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `category`  
 Vom Gebietsschema betroffene Kategorie.  
  
 `locale`  
 Gebietsschemaspezifizierer.  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn `locale` und `category` gültig sind, wird ein Zeiger auf die Zeichenfolge zurückgegeben, die den angegebenen Werten für `locale` und `category` zugeordnet ist. Wenn `locale` oder `category` ungültig ist, wird ein NULL-Zeiger zurückgegeben und die aktuellen Gebietsschemaeinstellungen des Programms werden nicht geändert.  
  
 Beispiel: Der Aufruf  
  
 `setlocale( LC_ALL, "en-US" );`  
  
 legt alle Kategorien fest und gibt nur folgende Zeichenfolge zurück  
  
 `en-US`  
  
 Sie können die von `setlocale` zurückgegebene Zeichenfolge kopieren, um diesen Teil der Gebietsschemainformation des Programms wiederherzustellen. Lokaler globaler Speicher oder lokaler Threadspeicher wird für die von `setlocale` zurückgegebene Zeichenfolge verwendet. Spätere Aufrufe von `setlocale` überschreiben die Zeichenfolge, sodass die von früheren Aufrufen zurückgegebenen Zeichenfolgenzeiger nicht mehr gültig sind.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie die Funktion `setlocale`, um einige oder alle Gebietsschemainformationen des aktuellen Programms festzulegen, zu ändern oder abzufragen, die von `locale` und `category` angegeben sind. `locale` verweist auf den Ort (Land/Region und Sprache), für den Sie bestimmte Aspekte des Programms anpassen können. Vom Gebietsschema abhängig sind u. a. Datumsformat und Währungsformat. Wenn Sie `locale` auf die Standardzeichenfolge für eine Sprache festlegen, zu der auf dem Computer mehrere Formen unterstützt werden, sollten Sie den `setlocale`-Rückgabewert überprüfen, um festzustellen, welche Sprache wirksam ist. Wenn Sie beispielsweise `locale` auf „Chinesisch“ festlegen, kann der Rückgabewert entweder „Chinesisch-vereinfacht“ oder „Chinesisch-traditionell“ sein.  
  
 `_wsetlocale` ist eine Breitzeichenversion von `setlocale`. Das Argument `locale` und der Rückgabewert von `_wsetlocale` sind Zeichenfolgen mit Breitzeichen. `_wsetlocale` und `setlocale` verhalten sich andernfalls identisch.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tsetlocale`|`setlocale`|`setlocale`|`_wsetlocale`|  
  
 Das `category`-Argument gibt die Teile der Gebietsschemainformationen eines Programms an, die betroffen sind. Die für `category` verwendeten Makros und die betroffenen Teile des Programms sind die folgenden:  
  
 `LC_ALL`  
 Alle Kategorien in der folgenden Liste:  
  
 `LC_COLLATE`  
 Die Funktionen `strcoll`, `_stricoll`, `wcscoll`, `_wcsicoll`, `strxfrm`, `_strncoll`, `_strnicoll`, `_wcsncoll`, `_wcsnicoll` und `wcsxfrm`.  
  
 `LC_CTYPE`  
 Die Funktionen zur Zeichenbehandlung (außer `isdigit`, `isxdigit`, `mbstowcs` und `mbtowc`, die nicht betroffen sind).  
  
 `LC_MONETARY`  
 Durch die `localeconv`-Funktion zurückgegebene Informationen zur Währungsformatierung.  
  
 `LC_NUMERIC`  
 Dezimaltrennzeichen für die formatierten Ausgaberoutinen (wie `printf`), für die Datenkonvertierungsroutinen und für die nicht monetären Formatierungsinformationen, die von `localeconv` zurückgegeben werden. Neben dem Dezimaltrennzeichen legt `LC_NUMERIC` auch das Tausendertrennzeichen und die Zeichenfolge für gruppierte Steuerelemente fest, die von [localeconv](../../c-runtime-library/reference/localeconv.md) zurückgegeben werden.  
  
 `LC_TIME`  
 Die Funktionen `strftime` und `wcsftime`.  
  
 Diese Funktion überprüft den Kategorienparameter. Wenn es sich bei dem Kategorienparameter um keinen der Werte handelt, die in der vorherigen Tabelle angegeben sind, wird der Handler für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, legt die Funktion `errno` auf `EINVAL` fest und gibt `NULL` zurück.  
  
 Das `locale`-Argument ist ein Zeiger auf eine Zeichenfolge, die das Gebietsschema angibt. Informationen über das Format des `locale`-Arguments finden Sie unter [Gebietsschema-Namen, Sprachen und Zeichenfolgen für Länder und Regionen](../../c-runtime-library/locale-names-languages-and-country-region-strings.md). Wenn `locale` auf eine leere Zeichenfolge zeigt, ist das Gebietsschema die durch die Implementierung definierte systemeigene Umgebung. Ein Wert von `C` gibt die Umgebung mit minimaler ANSI-Konformität für die C-Übersetzung an. Das `C`-Gebietsschema setzt als gegeben voraus, dass alle `char`-Datentypen 1 Byte groß sind und ihr Wert immer kleiner als 256 ist.  
  
 Zum Programmstart wird die Entsprechung der folgenden Anweisung ausgeführt:  
  
 `setlocale( LC_ALL, "C" );`  
  
 Das `locale`-Argument kann einen Gebietsschemanamen annehmen, eine Sprachenzeichenfolge, eine Sprachenzeichenfolge und eine Landeskennzahl, eine Codepage oder eine Sprachenzeichenfolge, eine Landeskennzahl eine und Codepage. Der Satz verfügbarer Gebietsschemanamen, Sprachen, Länder-/Regionscodes und Codepages umfasst alle diejenigen, die von der Windows NLS API unterstützt werden, ausgenommen Codepages, die mehr als zwei Bytes pro Zeichen benötigen, wie z. B. UTF-7 und UTF-8. Wenn Sie eine Codepage-Wert wie UTF-7 oder UTF-8 bereitstellen, schlägt `setlocale` fehl und gibt NULL zurück. Die Gebietsschemanamen, die von `setlocale` unterstützt werden, wird unter[Gebietsschema-Namen, Sprachen und Zeichenfolgen für Länder/Regionen](../../c-runtime-library/locale-names-languages-and-country-region-strings.md) beschrieben. Der von `setlocale` unterstützte Satz von Sprach- und Länder-/Regionszeichenfolgen ist in [Sprachzeichenfolgen](../../c-runtime-library/language-strings.md) und [Länder-/Regionszeichenfolgen](../../c-runtime-library/country-region-strings.md) aufgeführt. Wie empfehlen die Gebietsschema-Namensform aus Gründen der Leistung und leichteren Verwaltung von Gebietsschema-Zeichenfolgen, die in Code eingebettet sind oder für den Speicher serialisiert sind. Es ist weniger wahrscheinlich, dass Gebietsschema-Zeichenfolgen durch eine Betriebssystemaktualisierung geändert werden, als dies bei der Namensform für Sprache und Land/Region der Fall ist.  
  
 Eine als das `locale`-Argument übergebener NULL-Zeiger teilt `setlocale` mit, die internationale Umgebung abzufragen, anstatt sie festzulegen. Wenn das `locale`-Argument ein NULL-Zeiger ist, wird die aktuelle Gebietsschemaeinstellung des Programms nicht geändert. Stattdessen gibt `setlocale` ein Zeiger zur Zeichenfolge zurück, die der `category` des aktuellen Gebietsschemas des Threads zugeordnet ist. Wenn das `category`-Argument `LC_ALL` ist, gibt die Funktion eine Zeichenfolge zurück, die durch Semikolons getrennt die aktuelle Einstellung der einzelnen Kategorien angibt. Beispiel: Die Reihenfolge der Aufrufe  
  
 `// Set all categories and return "en-US"`  
  
 `setlocale(LC_ALL, "en-US");`  
  
 `// Set only the LC_MONETARY category and return "fr-FR"`  
  
 `setlocale(LC_MONETARY, "fr-FR");`  
  
 `printf("%s\n", setlocale(LC_ALL, NULL));`  
  
 gibt  
  
 `LC_COLLATE=en-US;LC_CTYPE=en-US;LC_MONETARY=fr-FR;LC_NUMERIC=en-US;LC_TIME=en-US`  
  
 zurück, welches die Zeichenfolge ist, die der Kategorie `LC_ALL` zugeordnet ist.  
  
 Die folgenden Beispiele gehören zur `LC_ALL`-Kategorie. Jede der Zeichenfolgen „.OCP" und „.ACP" kann anstelle einer Codepageseitenzahl verwendet werden, um jeweils die voreingestellte OEM-Benutzercodepage und die voreingestellte ANSI-Benutzercodepage anzugeben.  
  
 `setlocale( LC_ALL, "" );`  
 Legt das Gebietsschema auf den Standardwert fest, der die vom Betriebssystem abgerufene voreingestellte ANSI-Benutzercodepage ist.  
  
 `setlocale( LC_ALL, ".OCP" );`  
 Legt das Gebietsschema explizit auf die aktuelle vom Betriebssystem abgerufene voreingestellte OEM-Benutzercodepage fest.  
  
 `setlocale( LC_ALL, ".ACP" );`  
 Legt das Gebietsschema auf die vom Betriebssystem abgerufene voreingestellte ANSI-Benutzercodepage fest.  
  
 `setlocale( LC_ALL, "<localename>" );`  
 Legt das Gebietsschema auf den Gebietsschemanamen fest, der durch *\<Gebietsschemaname>* angegeben wird.  
  
 `setlocale( LC_ALL, "<language>_<country>" );`  
 Legt das Gebietsschema auf die Sprache und das Land/die Region fest, die durch *\<Sprache>* und *\<Land>* angegeben sind, und zwar zusammen mit der vom Hostbetriebssystem abgerufene Standardcodepage.  
  
 `setlocale( LC_ALL, "<language>_<country>.<code_page>" );`  
 Legt das Gebietsschema auf die Sprache, das Land/die Region und die Codepage fest, die bzw. das durch die Zeichenfolgen *\<Sprache>*, *\<Land>* und *<Codepage>* angegeben ist. Sie können verschiedene Kombinationen von Sprache, Land/Region und Codepage verwenden. Bei diesem Aufruf wird beispielsweise das Gebetsschema auf Französisch (Kanada) festgelegt, mit der Codepage 1252:  
  
 `setlocale( LC_ALL, "French_Canada.1252" );`  
  
 Bei diesem Aufruf wird das Gebietsschema auf Französisch (Kanada) mit der voreingestellten ANSI-Codepage festgelegt:  
  
 `setlocale( LC_ALL, "French_Canada.ACP" );`  
  
 Bei diesem Aufruf wird das Gebietsschema auf Französisch (Kanada) mit der voreingestellten OEM-Codepage festgelegt:  
  
 `setlocale( LC_ALL, "French_Canada.OCP" );`  
  
 `setlocale( LC_ALL, "<language>" );`  
 Legt das Gebietsschema auf die Sprache fest, die von *\<Sprache>* angegeben wird, und verwendet das Standardland bzw. die Standardregion für die angegebene Sprache sowie die vom Hostbetriebssystem abgerufene voreingestellte ANSI-Benutzercodepage für das Land/die Region. Beispiel: Die folgenden Aufrufe von `setlocale` sind funktional äquivalent:  
  
 `setlocale( LC_ALL, "en-US" );`  
  
 `setlocale( LC_ALL, "English" );`  
  
 `setlocale( LC_ALL, "English_United States.1252" );`  
  
 Aus Leistungsgründen und wegen der Wartbarkeit wird die erste Form empfohlen.  
  
 `setlocale( LC_ALL, ".<code_page>" );`  
 Legt die Codepage auf den Wert fest, der durch *<Codepage>* angegeben ist, wobei zugleich das Standardland bzw. die Standardregion und Sprache (gemäß der Definition vom Hostbetriebssystem) für die angegebene Codepage verwendet wird.  
  
 Die Kategorie muss entweder `LC_ALL` oder `LC_CTYPE` sein, um eine Codepageänderung zu bewirken. Wenn z. B. das Standardland bzw. die Standardregion und die Sprache des Hostbetriebssystems "USA" und "Englisch" sind, sind die folgenden beiden Aufrufe von `setlocale` funktional äquivalent:  
  
 `setlocale( LC_ALL, ".1252" );`  
  
 `setlocale( LC_ALL, "English_United States.1252");`  
  
 Weitere Informationen finden Sie unter [setlocale](../../preprocessor/setlocale.md)-Pragmadirektive in der [C/C++-Präprozessorreferenz](../../preprocessor/c-cpp-preprocessor-reference.md).  
  
 Mit der Funktion [_configthreadlocale](../../c-runtime-library/reference/configthreadlocale.md) wird gesteuert, ob `setlocale` das Gebietsschema aller Threads in einem Programm betrifft oder nur das Gebietsschema des aufrufenden Threads.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`setlocale`|\<locale.h>|  
|`_wsetlocale`|\<locale.h> oder \<wchar.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
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
 [Gebietsschema-Namen, Sprachen und Zeichenfolgen für Länder und Regionen](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [_configthreadlocale](../../c-runtime-library/reference/configthreadlocale.md)   
 [_create_locale, _wcreate_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [Gebietsschema](../../c-runtime-library/locale.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](../../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)   
 [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [strcoll-Funktionen](../../c-runtime-library/strcoll-functions.md)   
 [strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)   
 [strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)