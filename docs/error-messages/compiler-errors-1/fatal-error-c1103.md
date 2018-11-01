---
title: Schwerwiegender Fehler C1103
ms.date: 11/04/2016
f1_keywords:
- C1103
helpviewer_keywords:
- C1103
ms.assetid: 9d276939-9c47-4235-9d20-76b8434f9731
ms.openlocfilehash: b6253af9fcf400321fb58d4d8a6d7aacf461b926
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50577644"
---
# <a name="fatal-error-c1103"></a>Schwerwiegender Fehler C1103

Schwerwiegender Fehler beim Importieren der ProgID: "Meldung"

Der Compiler hat beim Importieren einer Typbibliothek ein Problem festgestellt.  Sie können beispielsweise keine Typbibliothek mit "progid" angeben und gleichzeitig `no_registry`festlegen.

Weitere Informationen finden Sie unter [#import-Anweisung](../../preprocessor/hash-import-directive-cpp.md).

Im folgenden Beispiel wird C1103 generiert:

```
// C1103.cpp
#import "progid:a.b.id.1.5" no_registry auto_search   // C1103
```