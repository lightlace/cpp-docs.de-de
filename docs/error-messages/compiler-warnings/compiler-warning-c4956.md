---
title: Compilerwarnung C4956 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4956
dev_langs:
- C++
helpviewer_keywords:
- C4956
ms.assetid: 9154f2d1-d49f-4e07-90d2-0e9bc028011a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: be92eb948e31a0a5367f92f5c2ed59baac2bd39b
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34703703"
---
# <a name="compiler-warning-c4956"></a>Compilerwarnung C4956

> "*Typ*': Dieser Typ ist nicht überprüfbar

## <a name="remarks"></a>Hinweise

Diese Warnung wird generiert, wenn [/clr:safe](../../build/reference/clr-common-language-runtime-compilation.md) angegeben ist und Ihr Code einen Typ enthält, der nicht überprüfbar ist. Die **/CLR: safe** -Compileroption in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt wird.

Weitere Informationen finden Sie unter [reiner und überprüfbarer Code (C + c++ / CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

Diese Warnung wird als Fehler ausgegeben. Sie kann mithilfe des [warning](../../preprocessor/warning.md) -Pragmas oder der Compileroption [/wd](../../build/reference/compiler-option-warning-level.md) deaktiviert werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4956 generiert:

```cpp
// C4956.cpp
// compile with: /clr:safe
int* p;   // C4956
```