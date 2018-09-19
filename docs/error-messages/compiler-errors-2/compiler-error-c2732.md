---
title: Compilerfehler C2732 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2732
dev_langs:
- C++
helpviewer_keywords:
- C2732
ms.assetid: 01b7ad2c-93cf-456f-a4c0-c5f2fdc7c07c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 040fd73bcb69ef032d5c6150bb157337f34a2088
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46079660"
---
# <a name="compiler-error-c2732"></a>Compilerfehler C2732

Bindungsangaben widersprechen vorheriger Angabe für 'function'

Die Funktion wurde bereits mit einem anderen Bindungsspezifizierer deklariert.

Dieser Fehler kann durch das Einbeziehen von Dateien mit unterschiedlichen Bindungsspezifizierern verursacht werden.

Um diesen Fehler zu beheben, ändern Sie die `extern`-Anweisungen, sodass die Bindungen übereinstimmen. Brechen Sie im Besonderen `#include`-Direktive nicht in `extern "C"`-Blöcke um.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2732 generiert:

```
// C2732.cpp
extern void func( void );   // implicit C++ linkage
extern "C" void func( void );   // C2732
```