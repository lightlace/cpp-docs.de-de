---
title: C++Header Dateien der Standardbibliothek
ms.date: 07/12/2019
helpviewer_keywords:
- header files, C++ Standard Library
- C++ Standard Library, header files
ms.assetid: e7bf497a-0f63-48d0-9b54-cb0eef4073c4
ms.openlocfilehash: dc337ef078108d86849aa7b7452512dfb69e6e18
ms.sourcegitcommit: 0867d648e0955ebad7260b5fbebfd6cd4d58f3c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/19/2019
ms.locfileid: "68341126"
---
# <a name="c-standard-library-header-files"></a>C++Header Dateien der Standardbibliothek

Header Dateien für die C++ Standardbibliothek und die Erweiterungen nach Kategorie.

## <a name="headers-by-category"></a>Header nach Kategorie

::: moniker range=">=vs-2017"

| Kategorie | Header |
| - | - |
| [Algorithmen](../cpp/algorithms-modern-cpp.md) | Algorithmus>, [ \<cstdlib >](cstdlib.md), [ \<numerische >](numeric.md) [ \<](algorithm.md) |
| Atomarische Vorgänge |  atomarische ><sup>11</sup> [ \<](atomic.md) |
| Wrapper für die C-Bibliothek | [ \<](cctype.md) [ \<](cerrno.md) [ \<](cfenv.md)<sup></sup> [ \<](ccomplex.md)<sup></sup>cassert >, ccomplex > 11 a b, cctype >, cerrno >, cfenv > 11, [ \<](cassert.md) [ \<cFloat->](cfloat.md), [ \<cinttypes >](cinttypes.md)<sup>11</sup>, [ \<ciso646 >](ciso646.md)<sup>b</sup>, [ \<climits >](climits.md), [ \<clocale >](clocale.md), [ \<cmath->](cmath.md), [ \<csetjmp >](csetjmp.md), [ \<cSignal >](csignal.md), [ \<cstdalign >](cstdalign.md)<sup>11 a b</sup>, [ \<cstdarg >](cstdarg.md), [ \<cstdbool >](cstdbool.md)<sup>11 a b</sup>, [ \<cstddef >](cstddef.md), [ \<cstdint >](cstdint.md)<sup>11</sup>, [ \<cstdio >](cstdio.md), [ \<cstdlib >](cstdlib.md), [ \<CString >](cstring.md) [ ,\<ctgmath >](ctgmath.md)<sup>11 a b</sup>, [ \<ctime >](ctime.md), [ \<Cuchar >](cuchar.md)<sup>11</sup>, [ \<cwchar >](cwchar.md), [ \<cwctype->](cwctype.md) |
| Konzepte | \<Konzepte ><sup>20</sup> |
| [Container](../cpp/containers-modern-cpp.md) | |
| Sequenz Container | <sup></sup><sup></sup> [ array\<>](array.md)11, [ Doppel>,Forward_list>11,Listen>,Vektor>\<](deque.md) [ \<](forward-list.md) [ \<](list.md) [ \<](vector.md) |
| Geordnete assoziative Container| [\<map>](map.md), [\<set>](set.md) |
| Ungeordnete assoziative Container | unordered_map ><sup>11</sup>, [ unordered_set>\<](unordered-set.md)<sup>11</sup> [ \<](unordered-map.md) |
| Container Adapter | [\<queue>](queue.md), [\<stack>](stack.md) |
| Container Sichten | \<span ><sup>20</sup> |
| [Fehler-und Ausnahmebehandlung](../cpp/errors-and-exception-handling-modern-cpp.md) | [ \<](exception.md)<sup></sup> [ \<](system-error.md) [ \<cassert](stdexcept.md)->, Ausnahme >, stdexcept >, System_Error > 11 [ \<](cassert.md) |
| Allgemeine Hilfsprogramme | \<Alle ><sup>17</sup>, [ \<Bitset >](bitset.md), \<chartv ><sup>17</sup>, [ \<cstdlib >](cstdlib.md), \<Execution ><sup>17</sup>, [ \<funktionale >](functional.md), [ Arbeits\<Speicher >](memory.md) \<, memory_resource<sup>> 17</sup>, \<optional ><sup>17</sup>, [ \<Verhältnis >](ratio.md)<sup>11</sup>, [ \<scoped_allocator > ](scoped-allocator.md) <sup>11</sup><sup></sup>,<sup></sup><sup></sup> [ \<Tupel](utility.md)> 11, [ \<type_traits >](type-traits.md)11, [ \<typeingangs >](typeindex.md)11, Hilfsprogramm>, [ \<](tuple.md) \<Variant ><sup>17</sup> |
| [E/a und Formatierung](../cpp/string-and-i-o-formatting-modern-cpp.md) | [ \<](fstream.md)<sup></sup><sup></sup> [ \<](filesystem.md) [ \<](cstdio.md) [ \<](iomanip.md) [ cinttypes>11,cstdio>,FileSystem>17,f->,\<](cinttypes.md)iomanip >, [ IOS\<->](ios.md), [ \<iosswd >](iosfwd.md), [ \<iostream >](iostream.md), [ \<IStream >](istream.md), [ \<ostream >](ostream.md), [ \<sstream >](sstream.md) \< [ ,\<streambuf >](streambuf.md), [ \<](strstream.md)"strincstream" ><sup>c</sup>, SyncStream ><sup>20</sup> |
| Iterators | [\<iterator>](iterator.md) |
| Sprachenunterstützung | \< \< \<<sup></sup><sup></sup> [ \<](climits.md)<sup></sup> [ \<](codecvt.md) [cFloat->, climits >, Codecvt > 11 a, Vergleich > 20, Vertrag > 20, \<](cfloat.md) Coroutine ><sup>20</sup>, [ \<csetjmp >](csetjmp.md), [ \<cSignal >](csignal.md), [ \<cstdarg >](cstdarg.md), [ \<cstddef >](cstddef.md), [ \<cstdint > ](cstdint.md) <sup>11</sup><sup></sup>, [ \<](exception.md) [ \<](initializer-list.md) [ \<cstdlib](limits.md)>, Exception >, initializer_list > 11, Limits > [ \<](cstdlib.md) [ \< neue >](new.md) \<, [ \<TypInfo >](typeinfo.md), Version ><sup>20</sup> |
| Lokalisierung | [ \<](locale.md) <sup></sup> [ \<](cvt-wbuffer.md) [ clocale\<>, Codecvt >](codecvt.md)11 a, CVT/wbuffer >, [ \<CVT/wstring >](cvt-wstring.md), locale > [ \<](clocale.md) |
| Math und Numerics | \<Bit ><sup>20</sup>, [ \<cfenv >](cfenv.md)<sup>11</sup>, [ \<cmath >](cmath.md), [ \<Complex >](complex.md), [ \<cstdlib >](cstdlib.md), [ \<Limits >](limits.md) [ \<numerischer >](numeric.md) [ ,\<Random >](random.md)<sup>11</sup>, [ \<Verhältnis >](ratio.md)<sup>11</sup>, [ \<Valarray >](valarray.md) |
| [Speicherverwaltung](../cpp/smart-pointers-modern-cpp.md) | \< [ \<](new.md) [ \<](scoped-allocator.md)<sup></sup><sup></sup> [ Zuweisungen\<>](allocators-header.md), [ Arbeitsspeicher>,memory_resource>17,\<](memory.md)neue >, scoped_allocator > 11 |
| Multithreading | <sup></sup><sup></sup><sup></sup><sup></sup> [ Atomic\<>](atomic.md)11, [ CONDITION_VARIABLE>11,Future>11,Mutex>11,\<](condition-variable.md) [ \<](future.md) [ \<](mutex.md) [ \< shared_mutex >](shared-mutex.md)<sup>14</sup>, [ \<Thread >](thread.md)<sup>11</sup> |
| Bereiche | \<Bereiche ><sup>20</sup> |
| Reguläre Ausdrücke | Regex ><sup>11</sup> [ \<](regex.md) |
| Zeichen folgen und Zeichendaten | [ \<](cstring.md)<sup></sup> [ \<](cuchar.md) [ \<](cwchar.md) [ cctype\<>, cstdlib >](cstdlib.md), CString >, Cuchar > 11, cwchar >, [ \<](cctype.md) [ \<cwctype >](cwctype.md) [ ,\<Regex >](regex.md)<sup>11</sup>, [ \<Zeichenfolge >](string.md), [ \<string_view >](string-view.md)<sup>17</sup> |
| Uhrzeit | Chrono ><sup>11</sup>, [ \<ctime >](ctime.md) [ \<](chrono.md) |

<sup>11</sup> wurde im c++ 11-Standard hinzugefügt. \
<sup>14</sup> hinzugefügt im c++ 14-Standard. \
<sup>17</sup> wurde im c++ 17-Standard hinzugefügt. \
<sup>20</sup> in Draft c++ 20 Standard. \
<sup>ein</sup> , der im c++ 17-Standard veraltet ist. \
<sup>b</sup> entfernt im Entwurf c++ 20 Standard. \
<sup>c</sup> veraltet im Standard c++ 98.

::: moniker-end

::: moniker range="vs-2015"

|Kategorie|Header|
|-|-|
|[Algorithmen](../cpp/algorithms-modern-cpp.md)|[\<algorithm>](algorithm.md)|
|Wrapper für die C-Bibliothek|[\<cassert>](cassert.md), [\<cctype>](cctype.md), [\<cerrno>](cerrno.md), [\<cfenv>](cfenv.md), [\<cfloat>](cfloat.md), [\<cinttypes>](cinttypes.md), [\<ciso646>](ciso646.md), [\<climits>](climits.md), [\<clocale>](clocale.md), [\<cmath>](cmath.md), [\<csetjmp>](csetjmp.md), [\<csignal>](csignal.md), [\<cstdarg>](cstdarg.md), [\<cstdbool>](cstdbool.md), [\<cstddef>](cstddef.md), [\<cstdint>](cstdint.md), [\<cstdio>](cstdio.md), [\<cstdlib>](cstdlib.md), [\<cstring>](cstring.md), [\<ctgmath>](ctgmath.md), [\<ctime>](ctime.md), [\<cwchar>](cwchar.md), [\<cwctype>](cwctype.md)|
|[Container](../cpp/containers-modern-cpp.md)||
|Sequenz Container|[ array\<>](array.md), [ Doppel\<>](deque.md) [, Forward_list\<>](forward-list.md) [, Listen\<>](list.md) [, Vektor\<>](vector.md)|
|Geordnete assoziative Container| [\<map>](map.md), [\<set>](set.md)|
|Ungeordnete assoziative Container|unordered_map >, [ \<](unordered-map.md) [ unordered_set>\<](unordered-set.md)|
|Adaptor Container|[\<queue>](queue.md), [\<stack>](stack.md)|
|[Fehler-und Ausnahmebehandlung](../cpp/errors-and-exception-handling-modern-cpp.md)|[ \<Ausnahme >](system-error.md) , [ \<stdexcept >](stdexcept.md), System_Error > [ \<](exception.md)|
|[E/a und Formatierung](../cpp/string-and-i-o-formatting-modern-cpp.md)|[\<filesystem>](filesystem.md), [\<fstream>](fstream.md), [\<iomanip>](iomanip.md), [\<ios>](ios.md), [\<iosfwd>](iosfwd.md), [\<iostream>](iostream.md), [\<istream>](istream.md), [\<ostream>](ostream.md), [\<sstream>](sstream.md), [\<streambuf>](streambuf.md), [\<strstream>](strstream.md)|
|Iterators|[\<iterator>](iterator.md)|
|Lokalisierung|[\<codecvt>](codecvt.md), [\<cvt/wbuffer>](cvt-wbuffer.md), [\<cvt/wstring>](cvt-wstring.md), [\<locale>](locale.md)|
|Math und Numerics|[\<complex>](complex.md), [\<limits>](limits.md), [\<numeric>](numeric.md), [\<random>](random.md), [\<ratio>](ratio.md), [\<valarray>](valarray.md)|
|[Speicherverwaltung](../cpp/smart-pointers-modern-cpp.md)|Zuweisungen > [, Arbeits\<Speicher >](memory.md), [ \<neue >](new.md), [ \<scoped_allocator >](scoped-allocator.md) [ \<](allocators-header.md)|
|Multithreading|[ \<](shared-mutex.md) [ \<](condition-variable.md) [ \<](future.md)atomarische >, CONDITION_VARIABLE >, zukünftiger > [ ,\<Mutex >](mutex.md), shared_mutex >, Thread [ \<](atomic.md) [ \< >](thread.md)|
|Andere Hilfsprogramme|[ \<](initializer-list.md) [ \<](functional.md) [ \<](tuple.md) [ Bitset\<>, Chrono >](chrono.md), funktionale >, initializer_list >, Tupel >, type_traits [ \<](bitset.md) [ \< >](type-traits.md) [ ,\<typeingangs Info >](typeinfo.md), [ \<Typeingabe->](typeindex.md), [ \<-Hilfsprogramm >](utility.md)|
|Zeichen folgen und Zeichendaten|[\<regex>](regex.md), [\<string>](string.md), [\<string_view>](string-view.md)

::: moniker-end

## <a name="see-also"></a>Siehe auch

[Verwenden C++ von Bibliotheks Headern](using-cpp-library-headers.md)\
[C++Standardbibliothek](cpp-standard-library-reference.md)
