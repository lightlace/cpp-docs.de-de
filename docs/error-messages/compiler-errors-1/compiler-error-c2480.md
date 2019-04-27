---
title: Compilerfehler C2480
ms.date: 11/04/2016
f1_keywords:
- C2480
helpviewer_keywords:
- C2480
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
ms.openlocfilehash: 90016b65d4ddd58da3fb3c5ab6d81322dc0ef394
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187597"
---
# <a name="compiler-error-c2480"></a>Compilerfehler C2480

'Bezeichner': "Thread" ist nur für statische Daten gültig

Sie können keine der `thread` Attribut mit einer automatischen Variablen, die nicht statische Datenmember, die Funktionsparameter oder in Funktionsdeklarationen oder-Definitionen.

Verwenden der `thread` -Attribut für die globalen Variablen, statische Datenmember und nur lokale statische Variablen.

Im folgende Beispiel wird die C2480 generiert:

```
// C2480.cpp
// compile with: /c
__declspec( thread ) void func();   // C2480
__declspec( thread ) static int i;   // OK
```