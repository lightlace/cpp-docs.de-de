---
title: Compilerwarnung (Stufe 1) C4364
ms.date: 11/04/2016
f1_keywords:
- C4364
helpviewer_keywords:
- C4364
ms.assetid: 1477634c-d60f-4570-ad16-1aaeae24ac7f
ms.openlocfilehash: db2774b6a73a989b4e9250719f99122826b486fe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643598"
---
# <a name="compiler-warning-level-1-c4364"></a>Compilerwarnung (Stufe 1) C4364

\##using für Assembly "File" zuvor gesehen: location(line_number) ohne As_friend-Attribut. as_friend wurde nicht angewendet

Ein `#using` Richtlinie wurde wiederholt bei einer angegebenen Metadaten-Datei, aber die `as_friend` Qualifizierer wurde aus der ersten Instanz nicht verwendet; der Compiler ignoriert die zweite `as_friend`.

Weitere Informationen finden Sie unter [Friend-Assemblys (C++)](../../dotnet/friend-assemblies-cpp.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine Komponente erstellt:

```
// C4364.cpp
// compile with: /clr /LD
ref class A {};
```

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C4364 generiert.

```
// C4364_b.cpp
// compile with: /clr /W1 /c
#using " C4364.dll"
#using " C4364.dll" as_friend   // C4364
```