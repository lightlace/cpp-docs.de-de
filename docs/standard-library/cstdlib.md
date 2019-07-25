---
title: '&lt;cstdlib&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cstdlib>
helpviewer_keywords:
- cstdlib header
ms.assetid: 0a6aaebf-84e9-4b60-ae90-17e11981cf54
ms.openlocfilehash: 298d6a512b2863a326bda0670f33fe8f1bda0688
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449408"
---
# <a name="ltcstdlibgt"></a>&lt;cstdlib&gt;

Schließt den C-Standard Bibliotheks \<Header STDLIB. h > ein und fügt die verknüpften `std` Namen zum-Namespace hinzu. Durch einschließen dieses Headers wird sichergestellt, dass die mit externer Verknüpfung im C-Standard Bibliotheks Header deklarierten `std` Namen im-Namespace deklariert werden.

> [!NOTE]
> \<STDLIB. h > enthält nicht den Typ **wchar_t**.

## <a name="requirements"></a>Anforderungen

**Header**: \<cstdlib >

**Namespace:** std

## <a name="namespace-and-macros"></a>Namespace und Makros

```cpp
namespace std {
    using size_t = see definition;
    using div_t = see definition;
    using ldiv_t = see definition;
    using lldiv_t = see definition;
}

#define NULL
#define EXIT_FAILURE
#define EXIT_SUCCESS
#define RAND_MAX
#define MB_CUR_MAX
```

## <a name="exposition-only-functions"></a>Funktionen nur für die Ausstellung

```cpp
extern "C" using c-atexit-handler = void();
extern "C++" using atexit-handler = void();
extern "C" using c-compare-pred = int(const void*, const void*);
extern "C++" using compare-pred = int(const void*, const void*);
```

## <a name="start-and-termination-functions"></a>Start-und Beendigungs Funktionen

|Funktion|Beschreibung|
|-|-|
|[_Exit](#_exit)|Beendet das Programm, ohne debugtoren oder registrierte Funktionen zu verwenden.|
|[abort](#abort)|Beendet das Programm ohne deerdeerdeverwendung.|
|[atexit](#atexit)|Registriert die Funktion für die Programm Beendigung.|
|[exit](#exit)|Zerstört Objekte mit Thread-und statischem Speicher und gibt dann die Steuerung zurück.|
|[at_quick_exit](#at_quick_exit)|Registriert die Funktion ohne Argumente für die Programm Beendigung.|
|[quick_exit](#quick_exit)|Registriert die Funktion mit beibehaltenen Objekten für die Programm Beendigung.|
|[getenv](#getenv)|Siehe C-Standard Bibliotheks Referenz.|
|[system](#system)|Siehe C-Standard Bibliotheks Referenz.|

### <a name="_exit"></a>_Exit

```cpp
[[noreturn]] void _Exit(int status) noexcept;
```

#### <a name="remarks"></a>Hinweise

Das Programm wird beendet, ohne dass Dekonstruktoren für Objekte der automatischen, Thread-oder statischen Speicherdauer ausgeführt werden und keine `atexit()`Funktionen aufgerufen werden, die an übermittelt werden. Die Funktion `_Exit` ist Signal sicher.

### <a name="abort"></a>Abbruch

```cpp
[[noreturn]] void abort() noexcept;
```

#### <a name="remarks"></a>Hinweise

Das Programm wird beendet, ohne dass Dekonstruktoren für Objekte der automatischen, Thread-oder statischen Speicherdauer ausgeführt werden und keine `atexit()`Funktionen aufgerufen werden, die an übermittelt werden. Die Funktion `abort` ist Signal sicher.

### <a name="at_quick_exit"></a>at_quick_exit

```cpp
int at_quick_exit(c-atexit-handler * func) noexcept;
int at_quick_exit(atexit-handler * func) noexcept;
```

#### <a name="return-value"></a>Rückgabewert

0 (null), wenn die Registrierung erfolgreich ist, andernfalls ungleich 0 (null).

#### <a name="remarks"></a>Hinweise

Die `at_quick_exit()` Funktionen registrieren die Funktion, auf die *Func* verweist, wenn `quick_exit` aufgerufen wird, ohne Argumente aufzurufen. Es ist nicht angegeben, ob ein Aufruf `at_quick_exit()` von, der nicht vor allen Aufrufen `quick_exit` von erfolgt, erfolgreich `at_quick_exit()` ausgeführt werden kann, und die Funktionen stellen kein Daten Rennen dar. Die Reihenfolge der Registrierung ist möglicherweise unbestimmt, wenn `at_quick_exit` von mehr als einem Thread aufgerufen wurde `at_quick_exit` und Registrierungen sich `atexit` von den Registrierungen unterscheiden, müssen Anwendungen möglicherweise beide Registrierungsfunktionen mit dem dasselbe Argument. Die-Implementierung unterstützt die Registrierung von mindestens 32-Funktionen.

### <a name="atexit"></a>atexit

```cpp
int atexit(c-atexit-handler * func) noexcept;
int atexit(atexit-handler * func) noexcept;
```

#### <a name="remarks"></a>Hinweise

Die `atexit()` Funktionen registrieren die Funktion, auf die von *Func* verwiesen wird, um beim normalen Programmabbruch ohne Argumente aufgerufen zu werden. Es ist nicht angegeben, ob ein `atexit()` -Befehl, der nicht vor einem- `exit()` Aufrufvorgang erfolgt, erfolgreich ausgeführt werden kann, und die `atexit()` -Funktionen stellen kein Daten Rennen dar. Die-Implementierung unterstützt die Registrierung von mindestens 32-Funktionen.

#### <a name="return-value"></a>Rückgabewert

Gibt 0 (null) zurück, wenn die Registrierung erfolgreich ist, wenn ein Fehler auftritt.

### <a name="exit"></a>Abstiegs

```cpp
[[noreturn]] void exit(int status);
```

#### <a name="remarks"></a>Hinweise

Zuerst werden Objekte mit Thread Speicherdauer, die dem aktuellen Thread zugeordnet sind, zerstört.

Als nächstes werden Objekte mit statischer Speicherdauer zerstört, und Funktionen, `atexit` die durch Aufrufen von registriert werden, werden aufgerufen. Automatische Objekte werden nicht zerstört, weil aufgerufen `exit()`wird. Wenn das Steuerelement eine registrierte, von `exit` aufgerufene Funktion verlässt, weil die Funktion keinen Handler für eine `std::terminate()` ausgelöste Ausnahme bereitstellt, muss aufgerufen werden. Eine Funktion wird für jedes Mal aufgerufen, wenn Sie registriert wird. Objekte mit automatischer Speicherdauer werden in einem Programm zerstört, dessen Hauptfunktion keine automatischen Objekte enthält, `exit()`und führt den-Befehl aus. Das Steuerelement kann direkt zu einer solchen Hauptfunktion übertragen werden, indem eine Ausnahme ausgelöst wird, die in Main abgefangen wird.

Im nächsten Schritt werden alle Open c-Streams (wie von den in <cstdio>deklarierten Funktions Signaturen) mit nicht geschriebenen gepufferten Daten geleert, alle geöffneten c-Streams werden geschlossen, und alle durch Aufrufen `tmpfile()` von erstellten Dateien werden entfernt.

Schließlich wird die Steuerung an die Host Umgebung zurückgegeben. Wenn "Status" den Wert "0" oder "EXIT_SUCCESS" aufweist, wird eine von der Implementierung definierte Form der erfolgreichen Beendigung zurückgegeben. Wenn der Status "EXIT_FAILURE" ist, wird eine von der Implementierung definierte Form des Status "nicht erfolgreich beendet" zurückgegeben. Andernfalls ist der zurückgegebene Status Implementierungs definiert.

### <a name="getenv"></a>getenv

```cpp
char* getenv(const char* name);
```

### <a name="quick_exit"></a>quick_exit

```cpp
[[noreturn]] void quick_exit(int status) noexcept;
```

#### <a name="remarks"></a>Hinweise

Funktionen, die durch Aufrufe `at_quick_exit` von registriert werden, werden in umgekehrter Reihenfolge ihrer Registrierung aufgerufen, mit dem Unterschied, dass eine Funktion nach allen zuvor registrierten Funktionen aufgerufen werden muss, die bereits zum Zeitpunkt der Registrierung aufgerufen wurden. Objekte dürfen nicht zerstört werden, weil aufgerufen `quick_exit`wird. Wenn das Steuerelement eine registrierte, von `quick_exit` aufgerufene Funktion verlässt, weil die Funktion keinen Handler für eine `std::terminate()` ausgelöste Ausnahme bereitstellt, muss aufgerufen werden. Eine Funktion, die `at_quick_exit` über registriert wird, wird von dem `quick_exit`Thread aufgerufen, der aufruft, wobei es sich um einen anderen Thread als den handelt, der Sie registriert hat. Daher sollten registrierte Funktionen nicht auf die Identität von Objekten mit Thread Speicherdauer zurückgreifen. Nachdem registrierte Funktionen aufgerufen wurden `quick_exit` , wird `_Exit(status)`von aufgerufen. Die Standarddatei Puffer werden nicht geleert. Die- `quick_exit` Funktion ist Signal sicher, wenn die mit `at_quick_exit` registrierten Funktionen sind.

### <a name="system"></a>Anlage

```cpp
int system(const char* string);
```

## <a name="memory-allocation-functions"></a>Speicher Belegungs Funktionen

```cpp
void* aligned_alloc(size_t alignment, size_t size);
void* calloc(size_t nmemb, size_t size);
void free(void* ptr);
void* malloc(size_t size);
void* realloc(void* ptr, size_t size);
double atof(const char* nptr);
int atoi(const char* nptr);
long int atol(const char* nptr);
long long int atoll(const char* nptr);
double strtod(const char* nptr, char** endptr);
float strtof(const char* nptr, char** endptr);
long double strtold(const char* nptr, char** endptr);
long int strtol(const char* nptr, char** endptr, int base);
long long int strtoll(const char* nptr, char** endptr, int base);
unsigned long int strtoul(const char* nptr, char** endptr, int base);
unsigned long long int strtoull(const char* nptr, char** endptr, int base);
```

#### <a name="remarks"></a>Hinweise

Diese Funktionen verfügen über die Semantik, die in der C-Standardbibliothek angegeben ist.

##  <a name="multibyte--wide-string-and-character-conversion-functions"></a>Multibyte/weite Zeichen folgen-und Zeichen Konvertierungs Funktionen

```cpp
int mblen(const char* s, size_t n);
int mbtowc(wchar_t* pwc, const char* s, size_t n);
int wctomb(char* s, wchar_t wchar);
size_t mbstowcs(wchar_t* pwcs, const char* s, size_t n);
size_t wcstombs(char* s, const wchar_t* pwcs, size_t n);
```

### <a name="remarks"></a>Hinweise

Diese Funktionen verfügen über die Semantik, die in der C-Standardbibliothek angegeben ist.

## <a name="algorithm-functions"></a>Algorithmusfunktionen

```cpp
void* bsearch(const void* key, const void* base, size_t nmemb, size_t size, c-compare-pred * compar);
void* bsearch(const void* key, const void* base, size_t nmemb, size_t size, compare-pred * compar);
void qsort(void* base, size_t nmemb, size_t size, c-compare-pred * compar);
void qsort(void* base, size_t nmemb, size_t size, compare-pred * compar);
```

### <a name="remarks"></a>Hinweise

Diese Funktionen verfügen über die Semantik, die in der C-Standardbibliothek angegeben ist.

## <a name="low-quality-random-number-generation-functions"></a>Funktionen der Zufallszahlengenerierung mit niedriger Qualität

```cpp
int rand();
void srand(unsigned int seed);
```

### <a name="remarks"></a>Hinweise

Diese Funktionen verfügen über die Semantik, die in der C-Standardbibliothek angegeben ist.

## <a name="absolute-values"></a>Absolute Werte

```cpp
int abs(int j);
long int abs(long int j);
long long int abs(long long int j);
float abs(float j);
double abs(double j);
long double abs(long double j);
long int labs(long int j);
long long int llabs(long long int j);
div_t div(int numer, int denom);
ldiv_t div(long int numer, long int denom);
lldiv_t div(long long int numer, long long int denom);
ldiv_t ldiv(long int numer, long int denom);
lldiv_t lldiv(long long int numer, long long int denom);
```

### <a name="remarks"></a>Hinweise

Diese Funktionen verfügen über die Semantik, die in der C-Standardbibliothek angegeben ist.

## <a name="functions"></a>Funktionen

```cpp
void* bsearch(const void* key, const void* base, size_t nmemb, size_t size,
c-compare-pred * compar);
void* bsearch(const void* key, const void* base, size_t nmemb, size_t size,
compare-pred * compar);
void qsort(void* base, size_t nmemb, size_t size, c-compare-pred * compar);
void qsort(void* base, size_t nmemb, size_t size, compare-pred * compar);
```

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[Übersicht über die C++-Standardbibliothek](../standard-library/cpp-standard-library-overview.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)
