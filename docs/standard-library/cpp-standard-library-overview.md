---
title: Übersicht über die C++-Standardbibliothek| Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- headers, C++ library
- C++ Standard Library
- libraries, Standard C++
- C++ Standard Library, headers
ms.assetid: 7acb83a4-da73-4ad3-bc30-a71289db7f60
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 79ec0f582ace9431a1d3a4f8eb0b474cb0d588d6
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="c-standard-library-overview"></a>Übersicht über die C++-Standardbibliothek

Alle C++-Bibliotheken werden in Standardheadern deklariert oder definiert. Diese Implementierung beinhaltet zwei zusätzliche Header \<Hash_map > und \<Hash_set >, vom C++-Standard nicht erforderlich sind. Eine vollständige Liste der Header, die diese Implementierung unterstützt, finden Sie unter [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md).

Eine freistehende Implementierung der C++-Bibliothek enthält nur eine Teilmenge dieser Header:

|||
|-|-|
|[\<cstddef>](../standard-library/cstddef.md)|[\<cstdlib>](../standard-library/cstdlib.md) (deklariert werden mindestens die Funktionen `abort`, `atexit` und `exit`)|
|[\<exception>](../standard-library/exception.md)|[\<limits>](../standard-library/limits.md)|
|[\<new>](../standard-library/new.md)|[\<cstdarg>](../standard-library/cstdarg.md)|

Die C++-Bibliothek-Header umfassen zwei größere Teilbereiche:

- [iostreams](../standard-library/iostreams-conventions.md)-Konventionen

- Konventionen der [C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)

Dieser Artikel enthält folgende Abschnitte:

- [Verwenden von C++-Bibliotheksheadern](../standard-library/using-cpp-library-headers.md)

- [C++-Bibliothekskonventionen](../standard-library/cpp-library-conventions.md)

- [iostreams-Konventionen](../standard-library/iostreams-conventions.md)

- [Starten und Beenden eines C++-Programms](../standard-library/cpp-program-startup-and-termination.md)

- [Sichere Bibliotheken: C++-Standardbibliothek](../standard-library/safe-libraries-cpp-standard-library.md)

- [Checked Iterators (Überprüfte Iteratoren)](../standard-library/checked-iterators.md)

- [Unterstützung für Iteratordebugging](../standard-library/debug-iterator-support.md)

- [C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)

- [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)

- [stdext Namespace (stdext-Namespace)](../standard-library/stdext-namespace.md)

- [Reguläre Ausdrücke (C++)](../standard-library/regular-expressions-cpp.md)

Weitere Informationen zu Visual C++-Laufzeitbibliotheken finden Sie unter [CRT-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Siehe auch

[C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)<br/>
