---
title: Compilerfehler C2873 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2873
dev_langs:
- C++
helpviewer_keywords:
- C2873
ms.assetid: 7a10036b-400e-4364-bd2f-dcd7370c5e28
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bf0cc5663d81d6c1e7ad6a9f1a5f7ca167f12909
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049903"
---
# <a name="compiler-error-c2873"></a>Compilerfehler C2873

'Symbol': Symbol kann nicht in eine using-Deklaration verwendet werden

Ein `using` -Direktive fehlt ein [Namespace](../../cpp/namespaces-cpp.md) Schlüsselwort. Dies bewirkt, dass den Compiler fälschlicherweise den Code als ein [using-Deklaration](../../cpp/using-declaration.md) anstelle eines [using-Direktive](../../cpp/namespaces-cpp.md#using_directives).