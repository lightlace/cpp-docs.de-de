---
title: Compilerfehler C2873 | Microsoft Docs
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
ms.openlocfilehash: 94a04d650729bdda949754c5070a6c307d390929
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33244377"
---
# <a name="compiler-error-c2873"></a>Compilerfehler C2873
'Symbol': Symbol kann nicht in einer using-Deklaration verwendet werden  
  
 Ein `using` -Direktive fehlt eine [Namespace](../../cpp/namespaces-cpp.md) Schlüsselwort. Dies bewirkt, dass den Compiler den Code als fälschlicherweise eine [using-Deklaration](../../cpp/using-declaration.md) anstelle eines [using-Direktive](../../cpp/namespaces-cpp.md#using_directives).