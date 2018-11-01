---
title: Compilerwarnung (Stufe 4) C4295
ms.date: 1/09/2018
f1_keywords:
- C4295
helpviewer_keywords:
- C4295
ms.assetid: 20dbff85-9f62-4ca3-8fe9-079d4512006d
ms.openlocfilehash: ed31ea19f9c36a9c6fab7452a4bfc3843a151059
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472188"
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
