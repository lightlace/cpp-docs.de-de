---
title: Compilerfehler C2299 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2299
dev_langs: C++
helpviewer_keywords: C2299
ms.assetid: d001c2bc-f6fd-47aa-8e42-0eb824d6441d
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4c0b18818ac45dea56d94b6046c8772710f02f56
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2299"></a>Compilerfehler C2299
"Function": verhaltensänderung: eine explizite Spezialisierung darf nicht sein, ein Kopierkonstruktor oder Kopierzuweisungsoperator  
  
 Dieser Fehler kann außerdem infolge einer konformitätsverbesserung für Visual C++ 2005 erstellt wurde, die generiert werden: vorherige Versionen von Visual C++ explizite spezialisierungen für einen Kopierkonstruktor oder einen Kopierzuweisungsoperator zulässig.  
  
 Stellen Sie zum Beheben von C2299 nicht den Kopierkonstruktor oder Zuweisungsoperator eine Vorlagenfunktion jedoch stattdessen eine Vorlagenfunktionen, die einen Klassentyp akzeptiert. Jeglicher Code, der den Kopierkonstruktor oder Zuweisungsoperator aufruft, durch die explizite Angabe der Vorlagenargumente muss die Vorlagenargumente zu entfernen.  
  
 Im folgenden Beispiel wird C2299 generiert:  
  
```  
// C2299.cpp  
// compile with: /c  
class C {  
   template <class T>  
   C (T t);  
  
   template <> C (const C&);   // C2299  
   C (const C&);   // OK  
};  
```