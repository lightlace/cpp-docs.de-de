---
title: Laufzeit-Typeninformation | Microsoft Docs
ms.custom: index-page
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- RTTI compiler option
- run-time type information
- run time, type checking
- type information, run-time type checking
- run-time checks, type checking
ms.assetid: becbd0e5-0439-4c61-854f-8a74f7160c54
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b23188b3dd49afb619576fa9cdcece69feca94f3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="run-time-type-information"></a>Laufzeit-Typinformationen
Laufzeittypinformationen (Run-Time Type Information, RTTI) sind ein Mechanismus, mit dem der Typ eines Objekts während der Programmausführung bestimmt werden kann. Laufzeittypinformationen wurden zur Programmiersprache C++ hinzugefügt, da viele Anbieter von Klassenbibliotheken diese Funktion selbst implementiert haben. Dies verursachte Inkompatibilitäten zwischen Bibliotheken. Deshalb wurde es offensichtlich, dass eine Unterstützung der Laufzeittypinformationen auf Sprachebene erforderlich war.  
  
 Aus Gründen der Übersichtlichkeit wird die Erläuterung der Laufzeittypinformationen nahezu ausschließlich auf Zeiger beschränkt. Jedoch gelten die erläuterten Konzepte auch für Verweise.  
  
 Es gibt drei primäre Sprachelemente von C++ zur Ausführung von Laufzeittypinformationen:  
  
-   Die [Dynamic_cast](../cpp/dynamic-cast-operator.md) Operator.  
  
     Wird zur Konvertierung von polymorphen Typen verwendet.  
  
-   Die [Typeid](../cpp/typeid-operator.md) Operator.  
  
     Wird zum Kennzeichnen des genauen Typ eines Objekts verwendet.  
  
-   Die [Type_info](../cpp/type-info-class.md) Klasse.  
  
     Wird verwendet, um die Typinformationen zu speichern, die vom `typeid`-Operator zurückgegeben werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Umwandlung](../cpp/casting.md)