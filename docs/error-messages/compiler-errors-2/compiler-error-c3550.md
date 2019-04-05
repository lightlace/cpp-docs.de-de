---
title: Compilerfehler C3550
ms.date: 11/04/2016
f1_keywords:
- C3550
helpviewer_keywords:
- C3550
ms.assetid: 9f2d5ffc-e429-41a1-89e3-7acc4fd47e14
ms.openlocfilehash: 106ac93496eebb25ee603251d84680053e1310b7
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59032335"
---
# <a name="compiler-error-c3550"></a>Compilerfehler C3550

In diesem Kontext ist nur ein einfaches "decltype(auto)" zulässig.

Wenn `decltype(auto)` als Platzhalter für den Rückgabetyp einer Funktion dient, muss dieses allein verwendet werden. Es kann nicht als Teil der Zeigerdeklaration (`decltype(auto*)`), einer Verweisdeklaration (`decltype(auto&)`) oder einer anderen Qualifizierung dieser Art verwendet werden.

## <a name="see-also"></a>Siehe auch

[auto](../../cpp/auto-cpp.md)