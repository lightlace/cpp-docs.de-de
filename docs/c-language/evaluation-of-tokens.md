---
title: "Auswertung von Tokens"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Token, Auswerten"
ms.assetid: 28870b62-dff6-4644-8b75-d58f340b48d2
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Auswertung von Tokens
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn der Compiler Token interpretiert, schließt er so viele Zeichen wie möglich in einem einzelnen Token ein, bevor er mit dem nächsten Token fortfährt.  Aufgrund dieses Verhaltens interpretiert der Compiler möglicherweise die Token nicht wie beabsichtigt, wenn sie nicht ordnungsgemäß durch Leerzeichen getrennt werden.  Betrachten Sie hierzu den folgenden Ausdruck:  
  
```  
i+++j  
```  
  
 In diesem Beispiel erstellt der Compiler zunächst den längsten möglichen Operator \(`++`\) aus den drei Pluszeichen, dann verarbeitet er das verbleibende Pluszeichen als Addition\-Operator \(`+`\).  Daher wird der Ausdruck als `(i++) + (j)` und nicht als `(i) + (++j)` interpretiert.  Verwenden Sie in diesem und ähnlichen Fällen Leerzeichen und Klammern, um Mehrdeutigkeiten zu vermeiden und eine ordnungsgemäße Ausdrucksbewertung sicherzustellen.  
  
 **Microsoft\-spezifisch**  
  
 Der C\-Compiler behandelt ein STRG\+Z\-Zeichen als Dateiendeindikator.  Er ignoriert jeden Text nach STRG\+Z.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [C\-Tokens](../c-language/c-tokens.md)