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
ms.openlocfilehash: 4d64a25475ad7ac40f63d29798768f8f57866b3c
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37941624"
---
# <a name="casting-operators"></a>Umwandlungsoperatoren
Es gibt mehrere Umwandlungsoperatoren, die spezifisch für die Programmiersprache C++ sind. Diese Operatoren sind vorgesehen, um einen Teil der Mehrdeutigkeiten und Gefahren zu beseitigen, die Umwandlungen in der C-Programmiersprache im altem Stil mit sich brachten. Diese Operatoren sind:  
  
-   [Dynamic_cast](../cpp/dynamic-cast-operator.md) für die Konvertierung von polymorphen Typen verwendet.  
  
-   ["static_cast"](../cpp/static-cast-operator.md) für die Konvertierung von nicht polymorphen Typen verwendet.  
  
-   [const_cast-Operator](../cpp/const-cast-operator.md) verwendet, um das Entfernen der **const**, **flüchtige**, und **__unaligned** Attribute.  
  
-   ["reinterpret_cast"](../cpp/reinterpret-cast-operator.md) für einfache Neuinterpretation von Bits verwendet.  
  
-   [Safe_cast](../windows/safe-cast-cpp-component-extensions.md) verwendet, um überprüfbare MSIL zu erzeugen.  
  
 Verwenden Sie `const_cast` und `reinterpret_cast` als letzten Ausweg, da diese Operatoren dieselben Gefahren wie Umwandlungen im alten Stil darstellen. Allerdings sind sie weiterhin erforderlich, um alte Umwandlungen vollständig zu ersetzen.  
  
## <a name="see-also"></a>Siehe auch  
 [Umwandlung](../cpp/casting.md)