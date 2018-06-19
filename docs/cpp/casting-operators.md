---
title: Umwandlungsoperatoren | Microsoft Docs
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
ms.openlocfilehash: bf4204e55811cd33fa48e2b3a07d3058100729ac
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32411646"
---
# <a name="casting-operators"></a>Umwandlungsoperatoren
Es gibt mehrere Umwandlungsoperatoren, die spezifisch für die Programmiersprache C++ sind. Diese Operatoren sind vorgesehen, um einen Teil der Mehrdeutigkeiten und Gefahren zu beseitigen, die Umwandlungen in der C-Programmiersprache im altem Stil mit sich brachten. Diese Operatoren sind:  
  
-   [Dynamic_cast](../cpp/dynamic-cast-operator.md) für die Konvertierung von polymorphen Typen verwendet.  
  
-   [Static_cast](../cpp/static-cast-operator.md) zur Konvertierung von nicht polymorphen Typen verwendet.  
  
-   [Const_cast](../cpp/const-cast-operator.md) verwendet, um das Entfernen der `const`, `volatile`, und `__unaligned` Attribute.  
  
-   [Reinterpret_cast](../cpp/reinterpret-cast-operator.md) für einfache Neuinterpretation von Bits verwendet.  
  
-   ["safe_cast"](../windows/safe-cast-cpp-component-extensions.md) verwendet, um überprüfbare MSIL zu erzeugen.  
  
 Verwenden Sie `const_cast` und `reinterpret_cast` als letzten Ausweg, da diese Operatoren dieselben Gefahren wie Umwandlungen im alten Stil darstellen. Allerdings sind sie weiterhin erforderlich, um alte Umwandlungen vollständig zu ersetzen.  
  
## <a name="see-also"></a>Siehe auch  
 [Umwandlung](../cpp/casting.md)