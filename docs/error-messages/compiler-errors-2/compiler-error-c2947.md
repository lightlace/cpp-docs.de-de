---
title: Compilerfehler C2947 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2947
dev_langs:
- C++
helpviewer_keywords:
- C2947
ms.assetid: 6c056f62-ec90-4883-8a67-aeeb6ec13546
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 508c2ae29b0290332cc7c2b49aac0a1ecb10528f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054518"
---
# <a name="compiler-error-c2947"></a>Compilerfehler C2947

erwartet ' >' gefunden. zum Beenden Konstrukt "Syntax"

Eine generische oder Vorlagenklasse Argumentliste wurde möglicherweise nicht ordnungsgemäß beendet.

C2947 kann auch durch Syntaxfehler generiert werden.

Im folgende Beispiel wird die C2947 generiert:

```
// C2947.cpp
// compile with: /c
template <typename T>=   // C2947
// try the following line instead
// template <typename T>
struct A {};
```