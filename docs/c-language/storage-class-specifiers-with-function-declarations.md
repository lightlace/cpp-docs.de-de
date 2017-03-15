---
title: "Speicherklassenspezifizierer mit Funktionsdeklarationen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Deklarieren von Funktionen, Bezeichner"
  - "Externe Deklarationen"
  - "Externe Verknüpfung, Funktionsdeklarationen"
  - "Externe Verknüpfung, Speicherklassenspezifizierer"
  - "Funktionsspezifizierer, Speicherklasse"
  - "Bezeichner, Funktion"
ms.assetid: 801d7df2-efa9-4924-a725-274a5654cfd4
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Speicherklassenspezifizierer mit Funktionsdeklarationen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können in Funktionsdeklarationen entweder den **static**\-Speicherklassenspezifizierer oder den `extern`\-Speicherklassenspezifizierer verwenden.  Funktionen besitzen immer eine globale Lebensdauer.  
  
 **Microsoft\-spezifisch**  
  
 Funktionsdeklarationen auf der internen Ebene haben dieselbe Bedeutung wie Funktionsdeklarationen auf externer Ebene.  Dies bedeutet, dass eine Funktion nach der Deklaration in der gesamten Übersetzungseinheit sichtbar ist, selbst wenn sie im lokalen Gültigkeitsbereich deklariert wurde.  
  
 **END Microsoft\-spezifisch**  
  
 Die Sichtbarkeitsregeln für Funktionen weichen geringfügig von den Regeln für Variablen ab:  
  
-   Eine Funktion, die als **static** deklariert wird, ist nur innerhalb der Quelldatei sichtbar, in der sie definiert ist.  Funktionen in derselben Quelldatei können die **static**\-Funktion aufrufen, aber Funktionen in anderen Quelldateien können auf sie nicht direkt anhand ihres Namens zugreifen.  Sie können eine weitere **static**\-Funktion mit demselben Namen in einer anderen Quelldatei deklarieren, ohne dass ein Konflikt auftritt.  
  
-   Die Funktionen, die als `extern` deklariert werden, sind in allen Quelldateien im Programm sichtbar \(es sei denn, dass Sie später eine solche Funktion erneut als **static** deklarieren\).  Jede Funktion kann eine `extern`\-Funktion aufrufen.  
  
-   Funktionsdeklarationen, die die Speicherklassenspezifizierer auslassen, sind standardmäßig `extern`.  
  
 **Microsoft\-spezifisch**  
  
 Microsoft lässt eine Neudefinition eines `extern`\-Bezeichners als **static** zu.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [C\-Speicherklassen](../c-language/c-storage-classes.md)