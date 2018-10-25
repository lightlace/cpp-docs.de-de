---
title: Compilerwarnung (Stufe 4) C4295 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 1/09/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4295
dev_langs:
- C++
helpviewer_keywords:
- C4295
ms.assetid: 20dbff85-9f62-4ca3-8fe9-079d4512006d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 63c7a6b640039f6e3008cab924c9d58dfcb1fcc8
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50080610"
---
# <a name="compiler-warning-level-4-c4295"></a>Compilerwarnung (Stufe 4) C4295

> "*Array*": Array ist zu klein, um ein abschließendes Nullzeichen einzuschließen

Das letzte Zeichen im Array wird es sich nicht um ein NULL-Wert, sondern ein Array initialisiert wurde. Zugreifen auf das Array als eine Zeichenfolge kann zu unerwarteten Ergebnissen führen.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C4295 generiert. Um dieses Problem zu beheben, Sie deklarieren die Array-Größe größer ist, zum Speichern ein abschließendes Nullzeichen aus der Initialisierer-Zeichenfolge, oder Sie können eine Initialisiererliste Array verwenden, um die beabsichtigte löschen, die sich dies ein Array von `char`, keine Null-terminierte Zeichenfolge.

```C
// C4295.c
// compile with: /W4

int main() {
   char a[3] = "abc";           // C4295
   char b[3] = {'d', 'e', 'f'}; // No warning
   a[0] = b[2];
}
```
