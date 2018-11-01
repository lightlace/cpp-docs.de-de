---
title: Compilerfehler C3385
ms.date: 11/04/2016
f1_keywords:
- C3385
helpviewer_keywords:
- C3385
ms.assetid: 5f1838c1-986e-47db-8dbc-e06976b83cf3
ms.openlocfilehash: 0cf8f75588339420c688db6e808a62a9fb0ac15c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50571209"
---
# <a name="compiler-error-c3385"></a>Compilerfehler C3385

'Klasse::Funktion': Eine Funktion, die ein benutzerdefiniertes DllImport-Attribut hat, kann keine Instanz einer Klasse zurückgeben.

Eine Funktion, die als Teil einer DLL-Datei definiert wird, die mit dem `DllImport` -Attribut angegeben wurde, kann keine Instanz einer Klasse zurückgeben.

Im folgenden Beispiel wird C3385 generiert:

```
// C3385.cpp
// compile with: /clr /c
using namespace System;
using namespace System::Runtime::InteropServices;

struct SomeStruct1 {};

public ref struct Wrap {
   [ DllImport("somedll.dll", CharSet=CharSet::Unicode) ]
   static SomeStruct1 f1([In, Out] SomeStruct1 *pS);   // C3385
};
```
