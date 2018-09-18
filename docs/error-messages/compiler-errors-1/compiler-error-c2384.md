---
title: Compilerfehler C2384 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2384
dev_langs:
- C++
helpviewer_keywords:
- C2384
ms.assetid: 8145f7ad-31b1-406d-ac43-0d557feab635
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f3aa9ec8a6a94f53123c443a1149df7cdbc95c83
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020458"
---
# <a name="compiler-error-c2384"></a>Compilerfehler C2384

„Member“ : __declspec(thread) kann nicht auf einen Member einer managed- oder WinRT-Klasse angewendet werden.

Die [Thread](../../cpp/thread.md) `__declspec` Modifizierer kann nicht auf ein Member eines verwalteten oder Windows-Runtime-Klasse verwendet werden.

Der statische threadlokale Speicher kann im verwalteten Code nur für statisch geladene DLLs verwendet werden; die DLL muss bei Prozessstart statisch geladen sein. Windows-Runtime unterstützt keinen lokalen Threadspeicher.

Mit der folgenden Zeile wird C2384 generiert und gezeigt, wie dieser Fehler im C++-/CLI-Code behoben werden kann:

```
// C2384.cpp
// compile with: /clr /c
public ref class B {
public:
   __declspec( thread ) static int tls_i = 1;   // C2384

   // OK - declare with attribute instead
   [System::ThreadStaticAttribute]
   static int tls_j;
};
```