---
title: Schwerwiegender Fehler C1103
ms.date: 11/04/2016
f1_keywords:
- C1103
helpviewer_keywords:
- C1103
ms.assetid: 9d276939-9c47-4235-9d20-76b8434f9731
ms.openlocfilehash: f037d1acb281b5997e3486a542784abc4b4b7542
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74747383"
---
# <a name="fatal-error-c1103"></a>Schwerwiegender Fehler C1103

Schwerwiegender Fehler beim Importieren der ProgID: "Meldung"

Der Compiler hat beim Importieren einer Typbibliothek ein Problem festgestellt.  Sie können beispielsweise keine Typbibliothek mit "progid" angeben und gleichzeitig `no_registry`festlegen.

Weitere Informationen finden Sie unter [#Import-Direktive](../../preprocessor/hash-import-directive-cpp.md).

Im folgenden Beispiel wird C1103 generiert:

```cpp
// C1103.cpp
#import "progid:a.b.id.1.5" no_registry auto_search   // C1103
```
