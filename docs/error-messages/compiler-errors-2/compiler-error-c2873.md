---
title: Compilerfehler C2873
ms.date: 11/04/2016
f1_keywords:
- C2873
helpviewer_keywords:
- C2873
ms.assetid: 7a10036b-400e-4364-bd2f-dcd7370c5e28
ms.openlocfilehash: 69be18e5f3e06392d4f2fa11c6343a07298b84bb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62164930"
---
# <a name="compiler-error-c2873"></a>Compilerfehler C2873

'Symbol': Symbol kann nicht in eine using-Deklaration verwendet werden

Ein `using` -Direktive fehlt ein [Namespace](../../cpp/namespaces-cpp.md) Schlüsselwort. Dies bewirkt, dass den Compiler fälschlicherweise den Code als ein [using-Deklaration](../../cpp/using-declaration.md) anstelle eines [using-Direktive](../../cpp/namespaces-cpp.md#using_directives).