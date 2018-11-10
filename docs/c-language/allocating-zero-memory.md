---
title: Nullspeicherbelegung
ms.date: 11/04/2016
helpviewer_keywords:
- memory allocation, zero memory
- zero memory
ms.assetid: 768f2ab9-83a1-4887-8eb5-c094c18489a8
ms.openlocfilehash: c7d5f307a38fff938c94cf2e1660cec99262a10a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447306"
---
# <a name="allocating-zero-memory"></a>Nullspeicherbelegung

**ANSI 4.10.3** Das Verhalten der `calloc`-, `malloc`- oder `realloc`-Funktion, wenn die angeforderte Größe Null ist

Die `calloc`-, `malloc`- und `realloc`-Funktionen akzeptieren Null als Argument. Es wird kein physischer Arbeitsspeicher belegt, jedoch wird ein gültiger Zeiger zurückgegeben, und der Speicherblock kann später durch "realloc" geändert werden.

## <a name="see-also"></a>Siehe auch

[Bibliotheksfunktionen](../c-language/library-functions.md)