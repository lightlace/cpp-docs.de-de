---
title: Compilerfehler C2482 | Microsoft Docs
ms.custom: ''
ms.date: 09/15/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2482
dev_langs:
- C++
helpviewer_keywords:
- C2482
ms.assetid: 98c87da2-625c-4cc2-9bf7-78d15921e779
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f2c4725dd357854db504272e5b8b9d88641b143d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2482"></a>Compilerfehler C2482

>"*Bezeichner*": der dynamischen Initialisierung von "Thread" Daten nicht zulässig

Diese Fehlermeldung wird in Visual Studio 2015 und höher veraltet. In früheren Versionen Variablen deklariert, indem die `thread` Attribut kann nicht initialisiert werden, mit einem Ausdruck, der zur Laufzeit Auswertung erfordert. Ein statischer Ausdruck ist erforderlich, um initialisieren `thread` Daten.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C2482 generiert in Visual Studio 2013 und früheren Versionen generiert:

```cpp
// C2482.cpp
// compile with: /c
#define Thread __declspec( thread )
Thread int tls_i = tls_i;   // C2482

int j = j;   // OK in C++; C error
Thread int tls_i = sizeof( tls_i );   // Okay in C and C++
```
