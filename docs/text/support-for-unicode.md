---
title: Unterstützung für Unicode
ms.date: 1/09/2018
helpviewer_keywords:
- globalization [C++], character sets
- portable data types [MFC]
- Unicode [C++]
- wide characters [C++], about wide characters
- character sets [C++], Unicode
- localization [C++], character sets
- Unicode [C++], installing support
ms.openlocfilehash: fea49bff2a4563b8617e19636e27afbae1c55811
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62410550"
---
# <a name="support-for-unicode"></a>Unterstützung für Unicode

Unicode ist eine Spezifikation für die Unterstützung sämtlicher Zeichensätze, einschließlich derer, die nicht dargestellt werden kann nur einem Byte (d. h. die meisten von ihnen). Wenn Sie für einen internationalen Markt programmieren, sollten Sie Unicode verwenden oder ein [multibyte-Zeichensatz](../text/support-for-multibyte-character-sets-mbcss.md) (MBCS), oder ein Programm zu codieren, damit Sie es entweder eines Schalters erstellen können.

Ein Breitzeichen ist ein mehrsprachiger 2-Byte-Zeichencode. Zehntausenden von Zeichen, die mit nahezu alle Zeichen in der modernen Computerwelt, einschließlich technischer Symbole und spezieller veröffentlichungszeichen, dargestellt werden können, nach der Unicode-Spezifikation als eine einzelne Vielzahl Zeichen codiert werden, indem Sie Verwenden UTF-16. Zeichen, die in nur einem Breitzeichen dargestellt werden, können nicht können in einem Unicode-Paar mithilfe der Unicode-ersatzzeichenfunktion-Paar dargestellt werden. Da nahezu jedes Zeichen in die häufige Verwendung in einer einzelnen 16-Bit-Breitzeichen in UTF-16 dargestellt wird, vereinfacht die Verwendung von Breitzeichen die Programmierung mit internationalen Zeichensätzen. Breitzeichen, die mit UTF-16LE (bei einer little-Endian) codiert sind, das native Zeichen-Format für Windows.

Eine Breitzeichenzeichenfolge wird als `wchar_t[]`-Array dargestellt, auf das mit einem `wchar_t*`-Zeiger gezeigt wird. Jedes ASCII-Zeichen kann als Breitzeichen dargestellt werden, indem der Buchstabe L dem Zeichen vorangestellt wird. L '\0' ist beispielsweise das abschließende Nullzeichen von Wide (16-Bit). Auf ähnliche Weise kann jedes ASCII-Zeichenfolgenliteral als Breitzeichen-Zeichenfolgenliteral dargestellt werden, indem der Buchstabe L dem ASCII-Literal vorangestellt wird (L"Hello").

Im Allgemeinen benötigen Breitzeichen mehr Platz im Arbeitsspeicher als Multibytezeichen, werden aber schneller verarbeitet. Darüber hinaus wird nur ein Gebietsschema zu einem Zeitpunkt in einer multibyte-Codierung dargestellt werden kann, während alle Zeichensätze der Welt gleichzeitig durch die Unicode-Darstellung dargestellt werden.

Das MFC-Framework ist komplett Unicode-fähig, und MFC erreicht die Unicode-Fähigkeit durch die Verwendung von portablen Makros, die in der folgenden Tabelle gezeigt sind.

## <a name="portable-data-types-in-mfc"></a>Portable Datentypen in MFC

|Nicht portable Datendatentypen|Ersetzt durch dieses Makro|
|-----------------------------|----------------------------|
|`char`, `wchar_t`|`_TCHAR`|
|`char*`, `LPSTR` (Win32-Datentyp) `LPWSTR`|`LPTSTR`|
|`const char*`, `LPCSTR` (Win32-Datentyp) `LPCWSTR`|`LPCTSTR`|

Klasse `CString` verwendet `_TCHAR` als Basis und stellt Konstruktoren und Operatoren für einfache Konvertierungen bereit. Die meisten Zeichenfolgenvorgänge für Unicode können durch dieselbe Logik geschrieben werden, die für die Verarbeitung des Windows-ANSI-Zeichensatzes verwendet wird, mit der Ausnahme, dass die grundlegende Einheit für Vorgänge ein 16-Bit-Zeichen anstelle eines 8-Bit-Zeichens ist. Im Gegensatz zur Arbeit mit Multibytezeichensätzen müssen (und sollten) Sie ein Unicode-Zeichen nicht behandeln, als bestünde es aus zwei unterschiedlichen Bytes. Sie haben jedoch die Möglichkeit, ein einzelnes Zeichen dargestellt, die von einem Ersatzzeichenpaar von Breitzeichen behandeln. Schreiben Sie in der Regel keinen Code, der wird davon, dass die Länge einer Zeichenfolge, die die Anzahl der Zeichen identisch ist, ob schmalen oder breiten ausgegangen, enthält.

## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?

- [Verwenden von MFC-Unicode- und Multibyte-Zeichensatz (MBCS)-Unterstützung](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)

- [Unicode im Programm aktivieren](../text/international-enabling.md)

- [Unicode und MBCS im Programm aktivieren](../text/internationalization-strategies.md)

- [Verwenden von Unicode zum Erstellen eines internationalen Programms](../text/unicode-programming-summary.md)

- [Informationen Sie zu den Vorteilen von Unicode](../text/benefits-of-character-set-portability.md)

- [Verwenden von Wmain ich Breitzeichen-Argumente an ein Programm zu übergeben](../text/support-for-using-wmain.md)

- [Eine Zusammenfassung der Unicode-Programmierung](../text/unicode-programming-summary.md)

- [Erfahren Sie mehr über die Zuordnungen für generischen Text für die Byte-breiter Portabilität](../text/generic-text-mappings-in-tchar-h.md)

## <a name="see-also"></a>Siehe auch

[Text und Zeichenfolgen](../text/text-and-strings-in-visual-cpp.md)<br/>
[Unterstützung für die Verwendung von wmain](../text/support-for-using-wmain.md)