---
title: "Zusätzliche Überlegungen zum Starten | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- program startup [C++]
- startup code
- initializing before main
ms.assetid: 0e942aa6-8342-447c-b068-8980ed7622bd
caps.latest.revision: 6
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
ms.openlocfilehash: cb437729d2c60f15bc798438ecbbba0637bf3d22
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

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
