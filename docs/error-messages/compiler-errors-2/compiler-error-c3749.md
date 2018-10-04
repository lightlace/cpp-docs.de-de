---
title: Compilerfehler C3749 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3749
dev_langs:
- C++
helpviewer_keywords:
- C3749
ms.assetid: 3d26b468-4757-41b8-b5a2-78022a5295fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7ac866d742734f5b6126315a0b79020c9ec7fb74
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788395"
---
# <a name="compiler-error-c3749"></a>Compilerfehler C3749

'Attribut': ein benutzerdefiniertes Attribut kann nicht innerhalb einer Funktion verwendet werden

Ein benutzerdefiniertes Attribut kann nicht innerhalb einer Funktion verwendet werden. Weitere Informationen zu benutzerdefinierten Attributen finden Sie im Thema [Attribut](../../windows/attributes/attribute.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3749 generiert:

```
// C3749a.cpp
// compile with: /clr /c
using namespace System;

[AttributeUsage(AttributeTargets::All)]
public ref struct ABC : public Attribute {
   ABC() {}
};

void f1() { [ABC]; };  // C3749
```
