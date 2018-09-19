---
title: Compilerfehler C3156 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3156
dev_langs:
- C++
helpviewer_keywords:
- C3156
ms.assetid: 1876da78-b94e-4af7-9795-28f72b209b3e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cfb52ad730df486ee804bcf958505512fadc0150
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116699"
---
# <a name="compiler-error-c3156"></a>Compilerfehler C3156

'class': Sie können nicht über eine lokale Definition eines verwalteten oder WinRT-Typs verfügen

Eine Funktion kann weder die Definition noch die Deklaration einer verwalteten oder WinRT-Klasse, -Struktur oder -Oberfläche enthalten.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C3156 generiert:

```
// C3156.cpp
// compile with: /clr /c
void f() {
   ref class X {};   // C3156
   ref class Y;   // C3156
}
```
