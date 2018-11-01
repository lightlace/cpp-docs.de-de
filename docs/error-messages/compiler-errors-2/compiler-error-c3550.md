---
title: Compilerfehler C3550
ms.date: 11/04/2016
f1_keywords:
- C3550
helpviewer_keywords:
- C3550
ms.assetid: 9f2d5ffc-e429-41a1-89e3-7acc4fd47e14
ms.openlocfilehash: dbed14b9f2fa0f2163484edd8b5dfa330af9cbf1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498880"
---
# <a name="compiler-error-c3550"></a>Compilerfehler C3550

In diesem Kontext ist nur ein einfaches "decltype(auto)" zulässig.

Wenn `decltype(auto)` als Platzhalter für den Rückgabetyp einer Funktion dient, muss dieses allein verwendet werden. Es kann nicht als Teil der Zeigerdeklaration (`decltype(auto*)`), einer Verweisdeklaration (`decltype(auto&)`) oder einer anderen Qualifizierung dieser Art verwendet werden.

## <a name="see-also"></a>Siehe auch

[auto](../../cpp/auto-cpp.md)