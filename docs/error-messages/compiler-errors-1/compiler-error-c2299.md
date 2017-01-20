---
title: "Compilerfehler C2299"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2299"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2299"
ms.assetid: d001c2bc-f6fd-47aa-8e42-0eb824d6441d
caps.latest.revision: 16
caps.handback.revision: "16"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2299
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Verhaltensänderung: Eine explizite Spezialisierung darf kein Kopierkonstruktor oder Kopierzuweisungsoperator sein.  
  
 Dieser Fehler kann auch infolge einer Verbesserung der Compilerkonformität für Visual C\+\+ 2005 ausgegeben werden: In früheren Versionen von Visual C\+\+ werden explizite Spezialisierungen für einen Kopierkonstruktor oder einen Kopierzuweisungsoperator unterstützt.  
  
 Um den Fehler C2299 zu vermeiden, darf der Kopierkonstruktor oder Zuweisungsoperator keine Vorlagenfunktion sein, sondern vielmehr eine nicht auf Vorlagen basierende Funktion, die einen Klassentyp akzeptiert.  Durch jeden Code, der den Kopierkonstruktor oder Zuweisungsoperator durch explizite Angabe der Vorlagenargumente aufruft, müssen die Vorlagenargumente entfernt werden.  
  
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