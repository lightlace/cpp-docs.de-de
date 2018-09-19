---
title: Compilerwarnung (Stufe 1) C4364 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4364
dev_langs:
- C++
helpviewer_keywords:
- C4364
ms.assetid: 1477634c-d60f-4570-ad16-1aaeae24ac7f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e37c7f37e1b51296bd5c3ae2cbdb85a93326f027
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087252"
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