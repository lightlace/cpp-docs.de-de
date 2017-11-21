---
title: "Zusätzliche Überlegungen zum Starten | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- program startup [C++]
- startup code
- initializing before main
ms.assetid: 0e942aa6-8342-447c-b068-8980ed7622bd
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 13471dae28bec066ebe8aeec785a1a060c7f975f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="additional-startup-considerations"></a>Zusätzliche Überlegungen zum Starten
In C++ können Objektkonstruktion und -zerstörung das Ausführen von Benutzercode beinhalten. Daher ist es wichtig zu verstehen, welche Initialisierungen vor dem Eintritt in geschehen **main** und welche Destruktoren aufgerufen werden, nach dem Verlassen von **main**. (Ausführliche Informationen zur Erstellung und Zerstörung von Objekten finden Sie unter [Konstruktoren](../cpp/constructors-cpp.md) und [Destruktoren](../cpp/destructors-cpp.md).)  
  
 Die folgenden Initialisierungen vor dem Eintritt in **main**:  
  
-   Standardinitialisierung von statischen Daten auf Null. Alle statischen Daten ohne explizite Initialisierer werden vor dem Ausführen eines beliebigen anderen Codes auf Null gesetzt, einschließlich der Laufzeitinitialisierung. Statische Datenmember müssen noch explizit definiert werden.  
  
-   Initialisierung eines globalen statischen Objekts in einer Übersetzungseinheit. Dies kann auftreten, entweder vor dem Eintritt in **main** oder vor der ersten Verwendung einer Funktion oder eines Objekts in der Übersetzungseinheit des Objekts.  
  
 **Microsoft-spezifisch**  
  
 In Microsoft C++ werden globale statische Objekte vor dem Eintritt in initialisiert **main**.  
  
 **Ende Microsoft-spezifisch**  
  
 Globale statische Objekte, die wechselseitig voneinander abhängig sind, sich jedoch in unterschiedlichen Übersetzungseinheiten befinden, können möglicherweise ein falsches Verhalten verursachen.  
  
## <a name="see-also"></a>Siehe auch  
 [Starten und beenden](../cpp/startup-and-termination-cpp.md)