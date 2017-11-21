---
title: Compilerfehler C3480 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3480
dev_langs: C++
helpviewer_keywords: C3480
ms.assetid: 7b2e055a-9604-4d13-861b-b38bda1a6940
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d84314d20ea00e880981e418c2b5b11008f74229
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3480"></a>Compilerfehler C3480
"Var": Eine Lambdaerfassungsvariable muss aus einem einschließenden Funktionsbereich stammen.  
  
 Die Lambdaerfassungsvariable stammt nicht aus einem einschließenden Funktionsbereich.  
  
### <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entfernen Sie die Variable aus der Erfassungsliste des Lambda-Ausdrucks.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3480 generiert, da die Variable `global` nicht aus einem einschließenden Funktionsbereich stammt:  
  
```  
// C3480a.cpp  
  
int global = 0;  
int main()  
{  
   [&global] { global = 5; }(); // C3480  
}  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3480 durch Entfernen der Variablen `global` aus der Erfassungsliste des Lambdaausdrucks behoben:  
  
```  
// C3480b.cpp  
  
int global = 0;  
int main()  
{  
   [] { global = 5; }();  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Lambda-Ausdrücke](../../cpp/lambda-expressions-in-cpp.md)