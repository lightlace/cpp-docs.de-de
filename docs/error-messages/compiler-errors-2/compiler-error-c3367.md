---
title: "Compilerfehler C3367"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C3367"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3367"
ms.assetid: e675d42b-f5b0-4d43-aab1-1f5024233102
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3367
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'static\_member\_function': Eine statische Funktion kann nicht zum Erstellen eines ungebundenen Delegaten verwendet werden.  
  
 Wenn Sie einen ungebundenen Delegaten aufrufen, müssen Sie eine Instanz eines Objekts übergeben. Da eine statische Memberfunktion über den Klassennamen aufgerufen wird, können Sie nur einen ungebundenen Delegaten mit einer Instanzmemberfunktion instanziieren.  
  
 Weitere Informationen finden Sie unter [Nicht gebundene Delegate](../../misc/unbound-delegates.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3367 generiert:  
  
```  
// C3367.cpp // compile with: /clr ref struct R { void b() {} static void f() {} }; delegate void Del(R^); int main() { Del ^ a = gcnew Del(&R::b);   // OK Del ^ b = gcnew Del(&R::f);   // C3367 }  
```