---
title: Einschränkungen der main-Funktion
ms.date: 11/04/2016
f1_keywords:
- Main
helpviewer_keywords:
- main function, restrictions on using
ms.assetid: 7b3df731-344b-44a8-850c-11cbcbfbfa83
ms.openlocfilehash: 9ccea987b05c7854e78ba1621fd6c0a065d73d5a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555734"
---
# <a name="main-function-restrictions"></a>Einschränkungen der main-Funktion

Mehrere Einschränkungen gelten für die **main** -Funktion, die nicht für andere C++-Funktionen gelten. Die **main** Funktion:

- Kann nicht überladen werden (siehe [Funktionsüberladung](function-overloading.md)).

- Kann nicht deklariert werden, als **Inline**.

- Kann nicht deklariert werden, als **statische**.

- Ihre Adresse kann nicht übernommen werden.

- Kann nicht aufgerufen werden.

## <a name="see-also"></a>Siehe auch

[main: Programmstart](../cpp/main-program-startup.md)