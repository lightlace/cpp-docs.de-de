---
title: Compilerfehler C2393 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2393
dev_langs:
- C++
helpviewer_keywords:
- C2393
ms.assetid: 4bd95728-e813-4ce8-844a-c6ebe235ca82
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 057537c8efcf6e827d9ac9aaf36c0eace6d24156
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704029"
---
# <a name="compiler-error-c2393"></a>Compilerfehler C2393

> "*Symbol*": anwendungsdomänenspezifisches Symbol kann nicht zugeordnet werden, in dem Segment "*Segment*"

## <a name="remarks"></a>Hinweise

Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

Die Verwendung von [Appdomain](../../cpp/appdomain.md) Variablen impliziert, dass Sie mit Kompilieren **/CLR: pure** oder **/CLR: safe**, und ein safe oder pure-Image darf keine Datensegmente enthalten.

Finden Sie unter [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md) für Weitere Informationen.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C2393 generiert. Um dieses Problem zu beheben, erstellen Sie ein Datensegment nicht.

```cpp
// C2393.cpp
// compile with: /clr:pure /c
#pragma data_seg("myseg")
int n = 0;   // C2393
```