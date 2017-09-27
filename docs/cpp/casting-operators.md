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
- casting operators
ms.assetid: 16240348-26bc-4f77-8eab-57253f00ce52
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: a516297b687db349a6bcc867fc94dcd85118a8a5
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

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
