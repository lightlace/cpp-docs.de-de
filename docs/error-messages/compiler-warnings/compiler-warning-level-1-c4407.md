---
title: "Compilerwarnung (Stufe 1) C4407"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4407"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4407"
ms.assetid: 32bc2c21-363a-4bb8-b486-725faeaededc
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4407
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Umwandeln von verschiedenen Zeigern in Memberrepräsentationen. Der Compiler generiert möglicherweise den falschen Code.  
  
 Es wurde eine falsche Typumwandlung entdeckt.  
  
 C4407 kann aufgrund einer Verbesserung der Compilerkonformität in Visual C\+\+ 2005 ausgegeben werden.  "pointer\-to\-member" muss jetzt mit einem qualifizierten Namen und dem Adressoperator \(&\).  
  
 C4407 kann auftreten, wenn Sie einen Memberzeiger für mehrfache Vererbung in einen Memberzeiger für einfache Vererbung umwandeln.  In manchen Fällen treten hierbei keine Probleme auf, in anderen Fällen stehen jedoch mit der Darstellung des Memberzeigers für einfache Vererbung nur unzureichende Informationen zur Verfügung.  Das Problem kann u. U. behoben werden, indem Sie mit der **\/vmm**\-Option kompilieren \(weitere Informationen finden Sie unter [\/vmm, \/vms, \/vmv \(Immer allgemeiner Zweck\)](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)\).  Eine weitere Möglichkeit besteht darin, die Basisklassen neu anzuordnen. Vom Compiler wird in der Konvertierung ein Datenverlust erkannt, da eine Basisklasse bezüglich der abgeleiteten Klasse über einen Offset ungleich 0 \(null\) verfügt.  
  
 Im folgenden Beispiel wird C4407 generiert:  
  
```  
// C4407.cpp  
// compile with: /W1 /c  
struct C1 {};  
struct C2 {};  
struct C3 : C1, C2 {};  
  
typedef void(C3::*PMF_C3)();  
typedef void(C2::*PMF_C2)();  
  
PMF_C2 f1(PMF_C3 pmf) {  
   return (PMF_C2)pmf;   // C4407, change type of cast,  
   // or reverse base class inheritance of C3 (i.e. : C2, C1)  
}  
```