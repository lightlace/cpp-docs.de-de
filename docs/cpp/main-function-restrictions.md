---
title: Einschränkungen der main-Funktion
ms.date: 11/04/2016
f1_keywords:
- Main
helpviewer_keywords:
- main function, restrictions on using
ms.assetid: 7b3df731-344b-44a8-850c-11cbcbfbfa83
ms.openlocfilehash: 9ccea987b05c7854e78ba1621fd6c0a065d73d5a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301837"
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