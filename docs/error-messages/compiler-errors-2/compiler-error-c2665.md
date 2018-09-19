---
title: Compilerfehler C2665 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2665
dev_langs:
- C++
helpviewer_keywords:
- C2665
ms.assetid: a7f99b61-2eae-4f2b-ba75-ea68fd1e8312
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b442e1de0481ef3d00742ed201575526332decff
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109144"
---
# <a name="compiler-error-c2665"></a>Compilerfehler C2665

'Funktion': kann keine der Überladungen "number1" Parameter "number2" vom Typ 'Typ' konvertieren

Ein Parameter der überladenen Funktion kann nicht in den erforderlichen Typ konvertiert werden.  Mögliche Lösungen:

- Geben Sie einen Konvertierungsoperator.

- Verwenden Sie die explizite Konvertierung.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C2665 generiert.

```
// C2665.cpp
void func(short, char*){}
void func(char*, char*){}

int main() {
   func(0, 1);   // C2665
   func((short)0, (char*)1);   // OK
}
```