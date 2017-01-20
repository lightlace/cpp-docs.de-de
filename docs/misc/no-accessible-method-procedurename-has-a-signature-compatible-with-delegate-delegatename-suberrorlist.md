---
title: "Keine zugreifbare &#39;&lt;Prozedurname&gt;&#39;-Methode hat eine Signatur, die mit dem Delegaten &#39;&lt;Delegatname&gt;&#39; kompatibel ist:&lt;Teilfehlerliste&gt;"
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "bc30950"
  - "vbc30950"
helpviewer_keywords: 
  - "BC30950"
ms.assetid: c1938099-2c03-491e-b599-d0c43bf94baf
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "shoag"
manager: "wpickett"
---
# Keine zugreifbare &#39;&lt;Prozedurname&gt;&#39;-Methode hat eine Signatur, die mit dem Delegaten &#39;&lt;Delegatname&gt;&#39; kompatibel ist:&lt;Teilfehlerliste&gt;
In einer Zuweisungsanordnung wird einer Delegatenvariablen die Adresse einer Prozedur zugewiesen, aber der Compiler kann keine Version der Prozedur mit einer übereinstimmenden Signatur finden.  
  
 Wenn der Code die Adresse einer Prozedur verwendet, versucht der Compiler, eine Version dieser Prozedur mit einer Parameterliste zu finden, die mit der des Delegaten übereinstimmt. Wenn die Prozedur in mehreren überladenen Versionen definiert ist, versucht der Compiler eine einzelne Version mit einer übereinstimmenden Signatur zu finden. Weitere Informationen finden Sie unter [Overload Resolution](../Topic/Overload%20Resolution%20\(Visual%20Basic\).md).  
  
 Findet der Compiler keine Version der Prozedur mit einer übereinstimmenden Signatur, generiert er diesen Fehler. Dies kann z. B. der Fall sein, wenn entweder die Prozedur oder der Delegat generisch ist und ein Typargument übergeben wird, das eine Signatur übergibt, die nicht mit der anderen Signatur übereinstimmt.  
  
 **Fehler\-ID:** BC30950  
  
### So beheben Sie diesen Fehler  
  
1.  Definieren Sie entweder die Prozedur oder den Delegaten neu, damit sie übereinstimmende Parameterlisten aufweisen.  
  
     \- oder \-  
  
     Definieren Sie einen neuen Delegaten mit einer Parameterliste, die mit der Liste der Prozedur übereinstimmt, oder definieren Sie eine neue Prozedur mit einer Parameterliste, die mit der Liste des Delegaten übereinstimmt.  
  
2.  Wenn entweder die Prozedur oder der Delegat generisch ist, übergeben sie ein Typargument, das dazu führt, dass die Signaturen übereinstimmen.  
  
## Siehe auch  
 [AddressOf Operator](../Topic/AddressOf%20Operator%20\(Visual%20Basic\).md)   
 [Delegate Statement](../Topic/Delegate%20Statement.md)   
 [NICHT IM BUILD: Delegaten und der AddressOf\-Operator](assetId:///7b2ed932-8598-4355-b2f7-5cedb23ee86f)   
 [Overload Resolution](../Topic/Overload%20Resolution%20\(Visual%20Basic\).md)   
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)