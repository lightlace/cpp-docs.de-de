---
title: "Laufzeit-Typinformationen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
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
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
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