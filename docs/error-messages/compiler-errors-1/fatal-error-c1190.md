---
title: Schwerwiegender Fehler C1190
ms.date: 11/04/2016
f1_keywords:
- C1190
helpviewer_keywords:
- C1190
ms.assetid: dee2266d-6c40-4f6e-91db-f01e65f8d2bc
ms.openlocfilehash: 8bd0332770dd0771ac7a02574185a506cf6fd416
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621337"
---
# <a name="fatal-error-c1190"></a>Schwerwiegender Fehler C1190

Für verwalteten Zielcode ist eine /clr-Option erforderlich.

Sie verwenden CLR-Konstrukte, aber Sie haben keine **/clr**angegeben.

Weitere Informationen finden Sie unter [/clr (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md).

Im folgenden Beispiel wird C1190 generiert:

```
// C1190.cpp
// compile with: /c
__gc class A {};   // C1190
ref class A {};
```