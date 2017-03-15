---
title: "Compilerwarnung (Stufe 3) C4800 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4800"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4800"
ms.assetid: 4f409799-a250-45ed-bb5f-657691b0d9f7
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 3) C4800
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ': Variable wird auf booleschen Wert \('true' oder 'false'\) festgelegt \(Auswirkungen auf Leistungsverhalten möglich\)  
  
 Diese Warnung wird erzeugt, wenn ein Wert, der nicht vom Typ `bool` ist, einem Wert vom Typ `bool` zugewiesen oder eine solche Typumwandlung erzwungen wird.  Normalerweise wird diese Meldung dadurch verursacht, dass `int`\-Variablen `bool`\-Variablen zugewiesen werden, wobei die `int`\-Variable nur die Werte **true** und **false** enthält und als Typ `bool` neu deklariert werden könnte.  Wenn es nicht möglich ist, den Ausdruck unter Verwendung des Typs `bool` umzuschreiben, können Sie dem Ausdruck "`!=0`" hinzufügen, was den Ausdruckstyp `bool` ergibt.  Durch die Typumwandlung des Ausdrucks in den Typ `bool` wird die Warnung aus Entwurfsgründen nicht deaktiviert.  
  
 Im folgenden Beispiel wird C4800 generiert:  
  
```  
// C4800.cpp  
// compile with: /W3  
int main() {  
   int i = 0;  
  
   // try..  
   // bool i = 0;  
  
   bool j = i;   // C4800  
   j++;  
}  
```