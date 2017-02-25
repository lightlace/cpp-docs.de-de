---
title: "Compilerwarnung (Stufe 1) C4540 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4540"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4540"
ms.assetid: 8085e748-5f4d-43c2-b06d-eaf794edbf72
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 1) C4540
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der Operator dynamic\_cast wird zur Konvertierung in eine nicht verfügbare oder mehrdeutige Basisklasse verwendet; Laufzeittest wird fehlschlagen \('Typ1' in 'Typ2'\)  
  
 Sie haben `dynamic_cast` für die Umwandlung von einem Typ in einen anderen verwendet.  Der Compiler hat bestimmt, dass diese Typumwandlung immer fehlschlägt \(**NULL** zurückgibt\), da eine Basisklasse entweder nicht zugänglich \(z. B. `private`\) oder mehrdeutig ist \(d. h., sie kommt mehr als einmal in der Klassenhierarchie vor\).  
  
 Im Folgenden ein Beispiel für diese Warnung.  Klasse **B** wird von Klasse **A** abgeleitet.  Das Programm verwendet `dynamic_cast`, um von Klasse **B** \(der abgeleiteten Klasse\) in Klasse **A** umzuwandeln. Dies wird immer fehlschlagen, da Klasse **B** `private` ist und somit nicht auf sie zugegriffen werden kann.  Das Problem kann durch Ändern des Zugriffs für **A** in **public** vermieden werden.  
  
```  
// C4540.cpp  
// compile with: /W1  
  
struct A {   
   virtual void g() {}  
};  
  
struct B : private A {  
   virtual void g() {}  
};  
  
int main() {  
   B b;  
   A * ap = dynamic_cast<A*>(&b);   // C4540  
}  
```