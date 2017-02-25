---
title: "Compilerfehler C2663 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2663"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2663"
ms.assetid: 1e93e368-fd52-42bf-9908-9b6df467c8c9
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2663
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion' : Für Zahl Überladung\(en\) gibt es keine zulässige Konvertierung für den this\-Zeiger  
  
 Der Compiler konnte den `this`\-Zeiger nicht in eine der überladenen Versionen der Memberfunktion konvertieren.  
  
 Dieser Fehler kann auftreten, wenn eine nicht mit `const` deklarierte Memberfunktion eines `const`\-Objekts aufgerufen wird.  Mögliche Lösungen:  
  
1.  Entfernen Sie `const` aus der Objektdeklaration.  
  
2.  Fügen Sie einer der Überladungen der Memberfunktion `const` hinzu.  
  
 Im folgenden Beispiel wird C2663 generiert:  
  
```  
// C2663.cpp  
struct C {  
   void f() volatile {}  
   void f() {}  
};  
  
struct D {  
   void f() volatile;  
   void f() const {}  
};  
  
const C *pcc;  
const D *pcd;  
  
int main() {  
   pcc->f();    // C2663  
   pcd->f();    // OK  
}  
```