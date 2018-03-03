---
title: Compilerwarnung (Stufe 1) C4138 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4138
dev_langs:
- C++
helpviewer_keywords:
- C4138
ms.assetid: 65ebf929-bba0-4237-923b-c1b66adfe17d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 568c12beecfcfc7f5fd8cece4b19f10fa38e54e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4138"></a>Compilerwarnung (Stufe 1) C4138
"*/" wurde außerhalb des Kommentars gefunden  
  
 Dem schließenden Kommentartrennzeichen geht kein öffnendes Kommentartrennzeichen voran. Der Compiler nimmt an, dass zwischen dem Sternchen (**\***) und dem Schrägstrich (/) ein Leerzeichen steht.  
  
## <a name="example"></a>Beispiel  
  
```  
// C4138a.cpp  
// compile with: /W1  
int */*comment*/ptr;   // C4138 Ambiguous first delimiter causes warning  
int main()  
{  
}  
```  
  
 Diese Warnung kann auf den Versuch zurückzuführen sein, Kommentare zu schachteln.  
  
 Die Warnung kann behoben werden, wenn Sie Codeabschnitte, die Kommentare enthalten, auskommentieren, den Code in einen **#if/#endif** -Block einschließen und den steuernden Ausdruck auf 0 (null) festlegen:  
  
```  
// C4138b.cpp  
// compile with: /W1  
#if 0  
int my_variable;   /* Declaration currently not needed */  
#endif  
int main()  
{  
}  
```