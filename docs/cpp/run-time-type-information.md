---
title: Laufzeit-Typeninformation | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: 'index-page '
dev_langs: C++
helpviewer_keywords:
- RTTI compiler option
- run-time type information
- run time, type checking
- type information, run-time type checking
- run-time checks, type checking
ms.assetid: becbd0e5-0439-4c61-854f-8a74f7160c54
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0b0b0124a69a0110bda94055964fbcdb54e5a754
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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