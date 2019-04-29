---
title: Compilerfehler C2393
ms.date: 11/04/2016
f1_keywords:
- C2393
helpviewer_keywords:
- C2393
ms.assetid: 4bd95728-e813-4ce8-844a-c6ebe235ca82
ms.openlocfilehash: 39ca693aed3f08e7b2df3d687f94d93384393f23
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302396"
---
# <a name="compiler-error-c2393"></a>Compilerfehler C2393

> "*Symbol*': anwendungsdomänenspezifisches Symbol kann nicht in Segment zugeordnet werden kann '*Segment*"

## <a name="remarks"></a>Hinweise

Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

Die Verwendung von [Appdomain](../../cpp/appdomain.md) -Variablen setzt voraus, dass Sie Kompilieren mit **/CLR: pure** oder **/CLR: safe**, und ein safe oder pure-Image darf keine Datensegmente enthalten.

Finden Sie unter [/CLR (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md) für Weitere Informationen.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2393 generiert. Um dieses Problem zu beheben, erstellen Sie ein Datensegment nicht.

```cpp
// C2393.cpp
// compile with: /clr:pure /c
#pragma data_seg("myseg")
int n = 0;   // C2393
```