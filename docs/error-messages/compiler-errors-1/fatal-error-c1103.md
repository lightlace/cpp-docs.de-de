---
title: Schwerwiegender Fehler C1103 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1103
dev_langs:
- C++
helpviewer_keywords:
- C1103
ms.assetid: 9d276939-9c47-4235-9d20-76b8434f9731
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d9e48d827c58ebf41ce3cf3862cbfbeaa494cf76
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055948"
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