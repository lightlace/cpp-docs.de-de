---
title: Umwandlungsoperatoren | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: 'index-page '
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], casting
- casting operators [C++]
ms.assetid: 16240348-26bc-4f77-8eab-57253f00ce52
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5bc7f1b0c2df820c3dc9e76b76dfcc72794e1906
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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