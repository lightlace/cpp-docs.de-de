---
title: Umwandlungsoperatoren | Microsoft-Dokumentation
ms.custom: index-page
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], casting
- casting operators [C++]
ms.assetid: 16240348-26bc-4f77-8eab-57253f00ce52
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 341812299d8cf95e351a087e9957dc0425cb25b2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46075942"
---
# <a name="casting-operators"></a>Umwandlungsoperatoren

Es gibt mehrere Umwandlungsoperatoren, die spezifisch für die Programmiersprache C++ sind. Diese Operatoren sind vorgesehen, um einen Teil der Mehrdeutigkeiten und Gefahren zu beseitigen, die Umwandlungen in der C-Programmiersprache im altem Stil mit sich brachten. Diese Operatoren sind:

- [Dynamic_cast](../cpp/dynamic-cast-operator.md) für die Konvertierung von polymorphen Typen verwendet.

- ["static_cast"](../cpp/static-cast-operator.md) für die Konvertierung von nicht polymorphen Typen verwendet.

- [const_cast-Operator](../cpp/const-cast-operator.md) verwendet, um das Entfernen der **const**, **flüchtige**, und **__unaligned** Attribute.

- ["reinterpret_cast"](../cpp/reinterpret-cast-operator.md) für einfache Neuinterpretation von Bits verwendet.

- [Safe_cast](../windows/safe-cast-cpp-component-extensions.md) verwendet, um überprüfbare MSIL zu erzeugen.

Verwendung **"const_cast"** und **"reinterpret_cast"** als letzte Möglichkeit, da diese Operatoren dieselben Gefahren wie alte Umwandlungen vorhanden. Allerdings sind sie weiterhin erforderlich, um alte Umwandlungen vollständig zu ersetzen.

## <a name="see-also"></a>Siehe auch

[Umwandlung](../cpp/casting.md)