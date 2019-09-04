---
title: Makros und C++
ms.date: 08/29/2019
helpviewer_keywords:
- macros, C++
- macros
ms.assetid: 83a344c1-73c9-4ace-8b93-cccfb62c6133
ms.openlocfilehash: 8a86fb81544af91d4e844fb08b7948a589976e04
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220800"
---
# <a name="macros-and-c"></a>Makros und C++

C++bietet neue Funktionen, von denen einige die vom ANSI C-Präprozessor angebotenen bereitstellen. Diese neuen Funktionen erweitern die Typsicherheit und die Voraussagbarkeit der Sprache:

- In C++können Objekte, die als Konstanten deklariert werden, in konstanten Ausdrücken verwendet werden. Sie ermöglicht es Programmen, Konstanten zu deklarieren, die über Typ-und Wert Informationen verfügen. Sie können Enumerationen deklarieren, die mit dem Debugger symbolisch angezeigt werden können. Wenn Sie die Präprozessordirektive `#define` zum Definieren von Konstanten verwenden, ist Sie nicht so präzise und nicht typsicher. Für ein konstantenobjekt wird kein Speicher zugeordnet, es sei denn, das Programm enthält einen Ausdruck, der seine Adresse annimmt.

- Funktionstypmakros werden von der C++-Inlinefunktion abgelöst. Im Vergleich zu Makros haben Inlinefunktionen folgende Vorteile:

  - Typsicherheit. Inlinefunktionen unterliegen derselben Typüberprüfung wie normale Funktionen. Makros sind nicht typsicher.

  - Korrekte Behandlung von Argumenten, die Nebeneffekte haben. Inline Funktionen Werten die Ausdrücke aus, die als Argumente bereitgestellt werden, bevor der Funktions Text eingegeben wird. Daher besteht keine Möglichkeit, dass ein Ausdruck mit Nebeneffekten unsicher ist.

Weitere Informationen zu Inline Funktionen finden Sie unter [Inline, __inline, \__forceinline](../cpp/inline-functions-cpp.md).

Aus Gründen der Abwärtskompatibilität werden alle Präprozessorfunktionen, die in ANSI C und in früheren C++-Spezifikationen vorhanden sind, für Microsoft C++ beibehalten.

## <a name="see-also"></a>Siehe auch

[Vordefinierte Makros](../preprocessor/predefined-macros.md)\
[Makros (C/C++)](../preprocessor/macros-c-cpp.md)
