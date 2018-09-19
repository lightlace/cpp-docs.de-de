---
title: Compilerfehler C3292 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3292
dev_langs:
- C++
helpviewer_keywords:
- C3292
ms.assetid: ead485cc-5471-4e10-b361-300589ff5b70
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8fc5f89978a7ecaff526fa05ca7a47494aada987
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46112459"
---
# <a name="compiler-error-c3292"></a>Compilerfehler C3292

Der cli-Namespace kann nicht erneut geöffnet werden.

Der cli-Namespace kann nicht in Ihrem Code deklariert werden.  Weitere Informationen finden Sie unter [Platform-, Default- und Cli-Namespaces](../../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3292 generiert:

```
// C3292.cpp
// compile with: /clr /c
namespace cli {};   // C3292
```