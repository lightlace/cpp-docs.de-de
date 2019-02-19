---
title: Nullspeicherbelegung
ms.date: 11/04/2016
helpviewer_keywords:
- memory allocation, zero memory
- zero memory
ms.assetid: 768f2ab9-83a1-4887-8eb5-c094c18489a8
ms.openlocfilehash: 40f21c0fa9a2a4068cb2592c49ccefed82176a35
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2019
ms.locfileid: "56147463"
---
# <a name="allocating-zero-memory"></a>Nullspeicherbelegung

**ANSI 4.10.3** Das Verhalten der `calloc`-, `malloc`- oder `realloc`-Funktion, wenn die angeforderte Größe Null ist

Die `calloc`-, `malloc`- und `realloc`-Funktionen akzeptieren Null als Argument. Es wird kein physischer Arbeitsspeicher belegt, jedoch wird ein gültiger Zeiger zurückgegeben, und der Speicherblock kann später durch "realloc" geändert werden.

## <a name="see-also"></a>Siehe auch

[Bibliotheksfunktionen](../c-language/library-functions.md)
