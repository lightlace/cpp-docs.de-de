---
title: Compilerfehler C3550 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3550
dev_langs:
- C++
helpviewer_keywords:
- C3550
ms.assetid: 9f2d5ffc-e429-41a1-89e3-7acc4fd47e14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 08c22d7e371fda7a229b541f78d4385f2943ee54
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46047784"
---
# <a name="compiler-error-c3550"></a>Compilerfehler C3550

In diesem Kontext ist nur ein einfaches "decltype(auto)" zulässig.

Wenn `decltype(auto)` als Platzhalter für den Rückgabetyp einer Funktion dient, muss dieses allein verwendet werden. Es kann nicht als Teil der Zeigerdeklaration (`decltype(auto*)`), einer Verweisdeklaration (`decltype(auto&)`) oder einer anderen Qualifizierung dieser Art verwendet werden.

## <a name="see-also"></a>Siehe auch

[auto](../../cpp/auto-cpp.md)