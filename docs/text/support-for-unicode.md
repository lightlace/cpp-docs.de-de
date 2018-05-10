---
title: Unterstützung für Unicode | Microsoft Docs
ms.custom: ''
ms.date: 1/09/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- globalization [C++], character sets
- portable data types [MFC]
- Unicode [C++]
- wide characters [C++], about wide characters
- character sets [C++], Unicode
- localization [C++], character sets
- Unicode [C++], installing support
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b9d5a435339e366d70749d64e5aae9264fe12b1f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="support-for-unicode"></a>Unterstützung für Unicode

Unicode ist eine Spezifikation zur Unterstützung sämtlicher Zeichensätze, einschließlich derer, die dargestellt werden kann nur einem Byte (d. h. die meisten von ihnen). Wenn Sie für einen internationalen Markt programmieren, es wird empfohlen, dass Sie entweder Unicode verwenden oder eine [Mehrbyte-Zeichensatz](../text/support-for-multibyte-character-sets-mbcss.md) (MBCS), oder das Programm-Codes, können Sie es entweder eines Schalters erstellen.

Ein Breitzeichen ist ein mehrsprachiger 2-Byte-Zeichencode. Zehntausenden von Zeichen, die mit fast allen verwendeten Zeichen in der modernen Computerwelt, einschließlich technischer Symbole und spezieller veröffentlichungszeichen, anhand der Unicode-Spezifikation als eine einzelne Breitzeichen dargestellt werden Zeichen codiert Verwenden UTF-16. Zeichen, die in nur einem Breitzeichen dargestellt werden können können in einem Unicode-Paar mithilfe der Unicode-Paar ersatzzeichenfunktion dargestellt werden. Da nahezu jedes Zeichen in häufige Verwendung in UTF-16 in ein einzelnes 16-Bit-Breitzeichen dargestellt wird, vereinfacht die Verwendung von Breitzeichen die Programmierung mit internationalen Zeichensätzen. Breitzeichen mit UTF-16LE (für little-Endian) verschlüsselt sind, das systemeigene Zeichenformat für Windows.

Eine Breitzeichenzeichenfolge wird als `wchar_t[]`-Array dargestellt, auf das mit einem `wchar_t*`-Zeiger gezeigt wird. Jedes ASCII-Zeichen kann als Breitzeichen dargestellt werden, indem der Buchstabe L dem Zeichen vorangestellt wird. L'\0' ist beispielsweise das abschließende (16-Bit) **NULL**-Breitzeichen. Auf ähnliche Weise kann jedes ASCII-Zeichenfolgenliteral als Breitzeichen-Zeichenfolgenliteral dargestellt werden, indem der Buchstabe L dem ASCII-Literal vorangestellt wird (L"Hello").

Im Allgemeinen benötigen Breitzeichen mehr Platz im Arbeitsspeicher als Multibytezeichen, werden aber schneller verarbeitet. Darüber hinaus wird nur ein Gebietsschema zu einem Zeitpunkt in eine multibytecodierung dargestellt werden kann, während alle Zeichensätze der Welt gleichzeitig von der Unicode-Darstellung dargestellt werden.

Das MFC-Framework ist komplett Unicode-fähig, und MFC erreicht die Unicode-Fähigkeit durch die Verwendung von portablen Makros, die in der folgenden Tabelle gezeigt sind.

## <a name="portable-data-types-in-mfc"></a>Portable Datentypen in MFC

|Nicht portable Datendatentypen|Ersetzt durch dieses Makro|
|-----------------------------|----------------------------|
|`char`, `wchar_t`|`_TCHAR`|
|`char*`, `LPSTR` (Win32-Datentyp) `LPWSTR`|`LPTSTR`|
|`const char*`, `LPCSTR` (Win32-Datentyp) `LPCWSTR`|`LPCTSTR`|

Klasse `CString` verwendet `_TCHAR` als Basis und stellt Konstruktoren und Operatoren für einfache Konvertierungen bereit. Die meisten Zeichenfolgenvorgänge für Unicode können durch dieselbe Logik geschrieben werden, die für die Verarbeitung des Windows-ANSI-Zeichensatzes verwendet wird, mit der Ausnahme, dass die grundlegende Einheit für Vorgänge ein 16-Bit-Zeichen anstelle eines 8-Bit-Zeichens ist. Im Gegensatz zur Arbeit mit Multibytezeichensätzen müssen (und sollten) Sie ein Unicode-Zeichen nicht behandeln, als bestünde es aus zwei unterschiedlichen Bytes. Sie müssen jedoch die Möglichkeit, dass ein einzelnes Zeichen, die von einem Ersatzzeichenpaar von Breitzeichen dargestellt zu verarbeiten. Im Allgemeinen schreiben Sie Code, der voraussetzt, dass die Länge einer Zeichenfolge, die die Anzahl der Zeichen, d. h. identisch ist, ob schmalen oder Breiten, enthält nicht.

## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?

- [Verwenden von MFC Unicode- und Multibyte-Zeichensatz (MBCS)-Unterstützung](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)

- [Unicode im Programm aktivieren](../text/international-enabling.md)

- [Sowohl Unicode-als auch MBCS im Programm aktivieren](../text/internationalization-strategies.md)

- [Verwenden von Unicode zum Erstellen eines internationalen Programms](../text/unicode-programming-summary.md)

- [Lernen Sie die Vorteile von Unicode](../text/benefits-of-character-set-portability.md)

- [Verwenden von Wmain Breitzeichen-Argumente an ein Programm übergeben von breitzeichenargumenten](../text/support-for-using-wmain.md)

- [Finden Sie eine Zusammenfassung der Unicode-Programmierung](../text/unicode-programming-summary.md)

- [Erfahren Sie mehr über Zuordnungen für generischen Text für Byte-breiter Portabilität](../text/generic-text-mappings-in-tchar-h.md)

## <a name="see-also"></a>Siehe auch

[Text und Zeichenfolgen](../text/text-and-strings-in-visual-cpp.md)  
[Unterstützung für die Verwendung von wmain](../text/support-for-using-wmain.md)  
