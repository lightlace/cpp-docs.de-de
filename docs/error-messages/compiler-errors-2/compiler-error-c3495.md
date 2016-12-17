---
title: "Compilerfehler C3495"
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
  - "C3495"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3495"
ms.assetid: 1fd40cb8-8373-403d-b8a8-f08424a50807
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3495
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var': Eine Lambdaerfassung muss eine automatische Speicherdauer aufweisen.  
  
 Variablen, die keine automatische Speicherdauer aufweisen, etwa eine als `static` oder `extern` markierte Variable, können nicht erfasst werden.  
  
### So beheben Sie diesen Fehler  
  
-   Übergeben Sie keine `static`\- oder `extern`\-Variable an die Erfassungsliste des Lambdaausdrucks.  
  
## Beispiel  
 Im folgenden Beispiel wird C3495 generiert, da die `static`\-Variable `n` in der Erfassungsliste eines Lambda\-Ausdrucks auftritt:  
  
```  
// C3495.cpp int main() { static int n = 66; [&n]() { return n; }(); // C3495 }  
```  
  
## Siehe auch  
 [Lambda\-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)   
 [\(NICHT IM BUILD\) Speicherklassenspezifizierer](assetId:///10b3d22d-cb40-450b-994b-08cf9a211b6c)