---
title: Laufzeit-Typeninformation | Microsoft Docs
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
- RTTI compiler option
- run-time type information
- run time, type checking
- type information, run-time type checking
- run-time checks, type checking
ms.assetid: becbd0e5-0439-4c61-854f-8a74f7160c54
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: ec36acfdba274a0eaf36c099da11f4462f2aad70
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

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
