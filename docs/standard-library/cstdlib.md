---
title: '&lt;cstdlib&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cstdlib>
helpviewer_keywords:
- cstdlib header
ms.assetid: 0a6aaebf-84e9-4b60-ae90-17e11981cf54
ms.openlocfilehash: 70e05ad734fa49ba8cb96e4bf83bc05b99c5f55c
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246526"
---
# <a name="ltcstdlibgt"></a>&lt;cstdlib&gt;

Schließt den Standard C-bibliotheksheader \<stdlib.h > und fügt die verknüpften Namen zum die `std` Namespace. Einschließen dieses Headers wird sichergestellt, dass die Namen deklariert, mit externer Bindung im standard C-bibliotheksheader, in deklariert werden der `std` Namespace.

> [!NOTE]
> \<STDLIB.h > Schließen Sie den Typ nicht **"wchar_t"** .

## <a name="requirements"></a>Anforderungen

**Header**: \<Cstdlib >

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

## <a name="exposition-only-functions"></a>Darstellung nur Funktionen

```cpp
extern "C" using c-atexit-handler = void();
extern "C++" using atexit-handler = void();
extern "C" using c-compare-pred = int(const void*, const void*);
extern "C++" using compare-pred = int(const void*, const void*);
```

## <a name="start-and-termination-functions"></a>Starten und Beenden von Funktionen

|Funktion|Beschreibung|
|-|-|
|[_Exit](#_exit)|Beendet die Anwendung ohne mit Destruktoren oder registrierten Funktionen.|
|[abort](#abort)|Beendet die Anwendung ohne Verwenden von Destruktoren.|
|[atexit](#atexit)|Register-Funktion für die Beendigung des Programms.|
|[exit](#exit)|Zerstört Objekte mit Threads und der statischen Speicher, dann gibt die Steuerung an.|
|[at_quick_exit](#at_quick_exit)|Register-Funktion ohne Argumente für die Beendigung des Programms.|
|[quick_exit](#quick_exit)|Register-Funktion mit beibehaltenen Objekten für die Beendigung des Programms.|
|[getenv](#getenv)|Finden Sie unter C-standard-Bibliothek-Referenz.|
|[system](#system)|Finden Sie unter C-standard-Bibliothek-Referenz.|

### <a name="_exit"></a> _Exit

```cpp
[[noreturn]] void _Exit(int status) noexcept;
```

#### <a name="remarks"></a>Hinweise

Das Programm wird beendet, ohne dass die Destruktoren für automatische Objekte, Thread oder statischer Speicherdauer ausgeführt und ohne Aufrufen von Funktionen, die an `atexit()`. Die Funktion `_Exit` Signal-sicher ist.

### <a name="abort"></a> Abbrechen

```cpp
[[noreturn]] void abort() noexcept;
```

#### <a name="remarks"></a>Hinweise

Das Programm wird beendet, ohne dass die Destruktoren für automatische Objekte, Thread oder statischer Speicherdauer ausgeführt und ohne Aufrufen von Funktionen, die an `atexit()`. Die Funktion `abort` Signal-sicher ist.

### <a name="at_quick_exit"></a> at_quick_exit

```cpp
int at_quick_exit(c-atexit-handler * func) noexcept;
int at_quick_exit(atexit-handler * func) noexcept;
```

#### <a name="return-value"></a>Rückgabewert

0 (null), wenn die Registrierung erfolgreich ist, die ungleich NULL, wenn schlägt fehl.

#### <a name="remarks"></a>Hinweise

Die `at_quick_exit()` Funktionen registrieren die Funktion verweist *Func* ohne Argumente aufgerufen werden beim `quick_exit` aufgerufen wird. Es wurde ein nicht angegeben, ob ein Aufruf zum `at_quick_exit()` dies nicht der Fall vor allen Aufrufen von `quick_exit` wird erfolgreich ausgeführt und die `at_quick_exit()` Funktionen führen ein Datenrace. Möglicherweise ist die Reihenfolge der Registrierung unbestimmt Wenn `at_quick_exit` hieß aus mehr als einem Thread und seit `at_quick_exit` Registrierungen unterscheiden sich von der `atexit` Registrierungen, Anwendungen müssen möglicherweise beide Registrierungsfunktionen mit Aufrufen der dasselbe Argument. Die Implementierung muss die Registrierung von mindestens 32 Funktionen unterstützen.

### <a name="atexit"></a> von "atexit"

```cpp
int atexit(c-atexit-handler * func) noexcept;
int atexit(atexit-handler * func) noexcept;
```

#### <a name="remarks"></a>Hinweise

Die `atexit()` Funktionen registrieren die Funktion verweist *Func* ohne Argumente auf normale programmbeendigung aufgerufen werden. Es wurde ein nicht angegeben, ob ein Aufruf zum `atexit()` dies nicht der Fall vor einem Aufruf von `exit()` wird erfolgreich ausgeführt und die `atexit()` Funktionen führen ein Datenrace. Die Implementierung muss die Registrierung von mindestens 32 Funktionen unterstützen.

#### <a name="return-value"></a>Rückgabewert

Wenn die Registrierung erfolgreich, ungleich NULL ist, wenn ein Fehler auftritt, gibt NULL zurück.

### <a name="exit"></a> Beenden

```cpp
[[noreturn]] void exit(int status);
```

#### <a name="remarks"></a>Hinweise

Zunächst mit threadspeicherdauer Objekte und verknüpft Sie mit dem aktuellen Thread zerstört werden.

Als Nächstes mit statischer Speicherdauer-Objekte werden zerstört, und Funktionen registriert, indem `atexit` aufgerufen werden. Automatische Objekte werden nicht als Ergebnis eines Aufrufs zerstört `exit()`. Wenn Steuerelement eine registrierte Funktion erfolgt azurenode lässt `exit` , da die Funktion einen Handler für eine ausgelöste Ausnahme, bieten nicht `std::terminate()` aufgerufen werden soll. Jedes Mal, wenn er registriert ist, wird für eine Funktion aufgerufen. Objekte mit automatischer Speicherdauer werden alle in einem Programm, deren "main"-Funktion enthält keine automatische Objekte und führt den Aufruf von, zerstört `exit()`. Steuerelement kann direkt an diese eine Hauptfunktion durch Auslösen einer Ausnahme, die abgefangen wird in Main übertragen werden.

Als Nächstes alle C-Streams zu öffnen (wie durch die Funktionssignaturen im deklarierten vermittelt <cstdio>) mit ungeschriebene gepufferten Daten werden geleert, werden alle offenen C-Streams werden geschlossen, und alle Dateien erstellt durch Aufrufen von `tmpfile()` werden entfernt.

Schließlich wird die Steuerung an die hostumgebung zurückgegeben. Wenn Status 0 (null) oder EXIT_SUCCESS ist, wird eine Form Implementierung definiert, der die erfolgreiche Beendigung von Status zurückgegeben. Wenn Status EXIT_FAILURE lautet, wird eine Form Implementierung definiert, der den Status nicht erfolgreichen Beendigung zurückgegeben. Andernfalls ist der zurückgegebene Status Implementierung definiert.

### <a name="getenv"></a> getenv

```cpp
char* getenv(const char* name);
```

### <a name="quick_exit"></a> quick_exit

```cpp
[[noreturn]] void quick_exit(int status) noexcept;
```

#### <a name="remarks"></a>Hinweise

Funktionen, die durch Aufrufe registriert `at_quick_exit` werden in ihre Registrierung in umgekehrter Reihenfolge aufgerufen, mit dem Unterschied, dass eine Funktion aufgerufen werden soll, nachdem alle zuvor registrierten Funktionen an, die bereits zum Zeitpunkt aufgerufen worden er registriert wurde. Objekte sind nicht als Ergebnis eines Aufrufs zerstört `quick_exit`. Wenn Steuerelement eine registrierte Funktion erfolgt azurenode lässt `quick_exit` , da die Funktion einen Handler für eine ausgelöste Ausnahme, bieten nicht `std::terminate()` aufgerufen werden soll. Eine Funktion, die über registriert `at_quick_exit` wird aufgerufen, indem der aufrufende Thread `quick_exit`, die auf einem anderen Thread sein kann, als diejenige, die es registriert registriert daher die Funktionen sollten nicht abhängig von der Identität von Objekten mit threadspeicherdauer. Nach dem Aufruf von registrierten Funktionen `quick_exit` aufrufen sollte `_Exit(status)`. Es sind nicht die Standarddatei Puffer geleert. Die Funktion `quick_exit` Signal-sicher ist, beim Registrieren von Funktionen in `at_quick_exit` sind.

### <a name="system"></a> System

```cpp
int system(const char* string);
```

## <a name="memory-allocation-functions"></a>Speicherverwaltungsfunktionen

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

Diese Funktionen haben die Semantik, die in der C++-Standardbibliothek angegeben.

##  <a name="multibyte--wide-string-and-character-conversion-functions"></a>Zeichenfolge von Multibytezeichen / Breite und Zeichen-Konvertierungsfunktionen

```cpp
int mblen(const char* s, size_t n);
int mbtowc(wchar_t* pwc, const char* s, size_t n);
int wctomb(char* s, wchar_t wchar);
size_t mbstowcs(wchar_t* pwcs, const char* s, size_t n);
size_t wcstombs(char* s, const wchar_t* pwcs, size_t n);
```

### <a name="remarks"></a>Hinweise

Diese Funktionen haben die Semantik, die in der C++-Standardbibliothek angegeben.

## <a name="algorithm-functions"></a>Algorithmusfunktionen

```cpp
void* bsearch(const void* key, const void* base, size_t nmemb, size_t size, c-compare-pred * compar);
void* bsearch(const void* key, const void* base, size_t nmemb, size_t size, compare-pred * compar);
void qsort(void* base, size_t nmemb, size_t size, c-compare-pred * compar);
void qsort(void* base, size_t nmemb, size_t size, compare-pred * compar);
```

### <a name="remarks"></a>Hinweise

Diese Funktionen haben die Semantik, die in der C++-Standardbibliothek angegeben.

## <a name="low-quality-random-number-generation-functions"></a>Geringer Qualität random Number Generation-Funktionen

```cpp
int rand();
void srand(unsigned int seed);
```

### <a name="remarks"></a>Hinweise

Diese Funktionen haben die Semantik, die in der C++-Standardbibliothek angegeben.

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

Diese Funktionen haben die Semantik, die in der C++-Standardbibliothek angegeben.

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

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[Überblick über die C++-Standardbibliothek](../standard-library/cpp-standard-library-overview.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
