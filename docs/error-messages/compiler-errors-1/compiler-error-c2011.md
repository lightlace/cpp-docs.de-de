---
title: Compilerfehler C2011 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2011
dev_langs:
- C++
helpviewer_keywords:
- C2011
ms.assetid: 992c9d51-e850-4d53-b86b-02e73b38249c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 09946a6a3e974293e65a582c735e3de42503f0c3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115036"
---
# <a name="compiler-error-c2011"></a>Compilerfehler C2011

"Bezeichner": "Typ" Typneudefinition

Der Bezeichner wurde bereits als `type` definiert. Überprüfen Sie, ob Neudefinitionen des Bezeichners vorliegen.

Beim Import tritt möglicherweise auch der Fehler C2011 auf, wenn Sie eine Headerdatei oder Typbibliothek mehrfach in dieselbe Datei importieren. #Include-Schutz um mehrfache einbindungen von in einer Headerdatei definierten Typen zu verhindern, verwenden oder ein `#pragma` [nach](../../preprocessor/once.md) -Direktive in der Headerdatei.

Wenn Sie die ursprüngliche Deklaration eines neu definierten Typs suchen müssen, können Sie mithilfe der [/p](../../build/reference/p-preprocess-to-a-file.md) Compilerflag die vorverarbeitete Ausgabe zu generieren, die an den Compiler übergeben. Mit Textsuchtools können Sie nach Instanzen der neu definierten Bezeichner in der Ausgabedatei suchen.

Im folgenden Beispiel wird C2011 generiert und eine Möglichkeit gezeigt, wie Sie diesen Fehler beheben:

```
// C2011.cpp
// compile with: /c
struct S;
union S;   // C2011
union S2;   // OK
```