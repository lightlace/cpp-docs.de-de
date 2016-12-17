---
title: "Zus&#228;tzliche &#220;berlegungen zum Starten"
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
  - "Initialisierung vor Main"
  - "Programmstart [C++]"
  - "Startcode"
ms.assetid: 0e942aa6-8342-447c-b068-8980ed7622bd
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Zus&#228;tzliche &#220;berlegungen zum Starten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In C\+\+ können Objektkonstruktion und \-zerstörung das Ausführen von Benutzercode beinhalten.  Daher ist es wichtig zu verstehen, welche Initialisierungen vor dem Eintritt in **main** erfolgen und welche Destruktoren nach dem Verlassen von **main** aufgerufen werden. \(Ausführliche Informationen zur Konstruktion und Zerstörung von Objekten finden Sie unter [Konstruktoren](../cpp/constructors-cpp.md) und [Destruktoren](../cpp/destructors-cpp.md)\).  
  
 Die folgenden Initialisierungen finden vor dem Eintritt in **main** statt:  
  
-   Standardinitialisierung von statischen Daten auf Null.  Alle statischen Daten ohne explizite Initialisierer werden vor dem Ausführen eines beliebigen anderen Codes auf Null gesetzt, einschließlich der Laufzeitinitialisierung.  Statische Datenmember müssen noch explizit definiert werden.  
  
-   Initialisierung eines globalen statischen Objekts in einer Übersetzungseinheit.  Dies kann entweder vor dem Eintritt in **main** oder vor der ersten Verwendung einer Funktion oder eines Objekts in der Übersetzungseinheit des Objekts auftreten.  
  
 **Microsoft\-spezifisch**  
  
 In Microsoft C\+\+ werden globale statische Objekte vor Eintritt in **main** initialisiert.  
  
 **END Microsoft\-spezifisch**  
  
 Globale statische Objekte, die wechselseitig voneinander abhängig sind, sich jedoch in unterschiedlichen Übersetzungseinheiten befinden, können möglicherweise ein falsches Verhalten verursachen.  
  
## Siehe auch  
 [Starten und Beenden](../cpp/startup-and-termination-cpp.md)