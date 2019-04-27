---
title: Schwerwiegender Fehler C1190
ms.date: 11/04/2016
f1_keywords:
- C1190
helpviewer_keywords:
- C1190
ms.assetid: dee2266d-6c40-4f6e-91db-f01e65f8d2bc
ms.openlocfilehash: 8bd0332770dd0771ac7a02574185a506cf6fd416
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62228903"
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