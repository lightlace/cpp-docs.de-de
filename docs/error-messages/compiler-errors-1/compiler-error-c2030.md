---
title: Compilerfehler C2030 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2030
dev_langs:
- C++
helpviewer_keywords:
- C2030
ms.assetid: 5806cead-64df-4eff-92de-52c9a3f5ee62
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b0c5849c372cc4c7ebf27dbe010e65d406ad1ab1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032892"
---
# <a name="compiler-error-c2030"></a>Compilerfehler C2030

ein Destruktor mit "protected private"-Zugriffsmöglichkeiten kann kein Member einer Klasse sein, die als "sealed" deklariert wurde

Eine Windows-Runtime-Klasse, die als `sealed` deklariert wird, kann nicht über einen geschützten privaten Destruktor verfügen. Nur öffentliche virtuelle und private nicht virtuelle Destruktoren sind für versiegelte Typen zulässig. Weitere Informationen finden Sie unter [Verweisklassen und Strukturen](../../cppcx/ref-classes-and-structs-c-cx.md).

Um diesen Fehler zu beheben, ändern Sie den Zugriff auf den Destruktor.