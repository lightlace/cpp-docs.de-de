---
title: "Memberzugriff"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Memberzugriff, Überladene Operatoren"
  - "Memberauswahloperatoren"
  - "Operatoren überladen, Operatoren für den Memberzugriff"
  - "Zeiger, Intelligent"
  - "Intelligente Zeiger"
  - "Intelligente Zeiger, Definition"
ms.assetid: 8c7b2c43-eb92-4d42-9a8e-61aa37d71333
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Memberzugriff
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Klassenmemberzugriff kann gesteuert werden, indem der Memberzugriffsoperator \(**–\>**\) überladen wird.  Dieser Operator wird bei dieser Verwendung als unärer Operator betrachtet, und die überladene Operatorfunktion muss eine Klassenmemberfunktion sein.  Daher ist die Deklaration für eine solche Funktion:  
  
## Syntax  
  
```  
  
class-type *operator–>()  
```  
  
## Hinweise  
 wobei *class\-type* der Name der Klasse ist, zu dem dieser Operator gehört.  Die Operatorfunktion für den Memberzugriff muss eine nicht statische Memberfunktion sein.  
  
 Dieser Operator wird \(oft in Verbindung mit dem Zeiger\-Dereferenzierungsoperator\) verwendet, um "intelligente Zeiger" zu implementieren, die vor einer Dereferenzierung oder Zählung validiert werden.  
  
 Der **.**\-Memberzugriffsoperator kann nicht überladen werden.  
  
## Siehe auch  
 [Überladen von Operatoren](../cpp/operator-overloading.md)