---
title: "Laufzeit-Typinformationen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "index-page "
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RTTI-Compileroption"
  - "Laufzeit, Typüberprüfung"
  - "Laufzeitüberprüfungen, Typüberprüfung"
  - "Laufzeit-Typinformationen"
  - "Typinformationen, Laufzeittypüberprüfung"
ms.assetid: becbd0e5-0439-4c61-854f-8a74f7160c54
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Laufzeit-Typinformationen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Laufzeittypinformationen \(Run\-Time Type Information, RTTI\) sind ein Mechanismus, mit dem der Typ eines Objekts während der Programmausführung bestimmt werden kann.  Laufzeittypinformationen wurden zur Programmiersprache C\+\+ hinzugefügt, da viele Anbieter von Klassenbibliotheken diese Funktion selbst implementiert haben.  Dies verursachte Inkompatibilitäten zwischen Bibliotheken.  Deshalb wurde es offensichtlich, dass eine Unterstützung der Laufzeittypinformationen auf Sprachebene erforderlich war.  
  
 Aus Gründen der Übersichtlichkeit wird die Erläuterung der Laufzeittypinformationen nahezu ausschließlich auf Zeiger beschränkt.  Jedoch gelten die erläuterten Konzepte auch für Verweise.  
  
 Es gibt drei primäre Sprachelemente von C\+\+ zur Ausführung von Laufzeittypinformationen:  
  
-   Der Operator [dynamic\_cast](../cpp/dynamic-cast-operator.md).  
  
     Wird zur Konvertierung von polymorphen Typen verwendet.  
  
-   Der Operator [typeid](../cpp/typeid-operator.md).  
  
     Wird zum Kennzeichnen des genauen Typ eines Objekts verwendet.  
  
-   Die Klasse [type\_info](../cpp/type-info-class.md).  
  
     Wird verwendet, um die Typinformationen zu speichern, die vom `typeid`\-Operator zurückgegeben werden.  
  
## Siehe auch  
 [Umwandlung von Typen](../cpp/casting.md)