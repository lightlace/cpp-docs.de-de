---
title: "Compilerfehler C2597 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2597"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2597"
ms.assetid: 2e48127d-e3ff-4a40-8156-2863e45b1a38
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C2597
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ungültiger Verweis auf nicht statisches Member 'identifier'  
  
 Mögliche Ursachen:  
  
1.  Ein nicht statisches Member wird in einer statischen Memberfunktion angegeben.  Für den Zugriff auf das nicht statische Member müssen Sie eine lokale Instanz der Klasse übergeben oder erstellen und einen Memberzugriffsoperator \(`.` oder `->`\) verwenden.  
  
2.  Der angegebene Bezeichner ist kein Member der Klasse, Struktur oder Union.  Prüfen Sie die Schreibweise des Bezeichners.  
  
3.  Ein Memberzugriffsoperator bezieht sich auf eine Nicht\-Memberfunktion.  
  
4.  Im folgenden Beispiel wird C2597 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2597.cpp  
// compile with: /c  
struct s1 {  
   static void func();  
   static void func2(s1&);  
   int i;  
};  
  
void s1::func() {  
   i = 1;    // C2597 - static function can't access non-static data member  
}  
  
// OK - fix by passing an instance of s1  
void s1::func2(s1& a) {  
   a.i = 1;  
}  
  
```