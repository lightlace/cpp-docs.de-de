---
title: Einschränkungen der Main-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- Main
dev_langs:
- C++
helpviewer_keywords:
- main function, restrictions on using
ms.assetid: 7b3df731-344b-44a8-850c-11cbcbfbfa83
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93f5cce15d4db9f7f6d4e3361d22028fccd676f2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117360"
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