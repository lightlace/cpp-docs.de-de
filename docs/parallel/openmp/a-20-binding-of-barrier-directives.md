---
title: "A.20   Binding of barrier Directives"
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
ms.assetid: a3fdcc26-6873-429b-998e-de451401483b
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# A.20   Binding of barrier Directives
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der Aufruf richtungweisende Bindungsregel, damit **Barriere**\-Direktiven nächsten übergeordneten `parallel` die Direktive binden.  Weitere Informationen zu richtungweisende Bindung finden Sie unter [Abschnitt 2.8](../../parallel/openmp/2-8-directive-binding.md) auf Seite 32.  
  
 Im folgenden Beispiel ist der Aufruf von *main* zu *sub2* kompatibel, da **Barriere** \(in *sub3*\) zum parallelen Bereichs in *sub2*bindet.  Der Aufruf von *main* zu *sub1* kompatibel ist, da **Barriere** zum parallelen Bereichs in der Unterroutine *sub2*bindet.  Der Aufruf von *main* zu *sub3* kompatibel ist, da **Barriere** keinem parallelen Bereich gebunden wird und wird ignoriert.  Beachten Sie außerdem, dass **Barriere** nur das Team von Threads im einschließenden parallelen Bereich und nicht in allen Threads synchronisiert *sub1*erstellt werden.  
  
```  
int main()  
{  
    sub1(2);  
    sub2(2);  
    sub3(2);  
}  
  
void sub1(int n)  
{  
    int i;  
    #pragma omp parallel private(i) shared(n)  
    {  
        #pragma omp for  
        for (i=0; i<n; i++)  
            sub2(i);  
    }  
}  
  
void sub2(int k)  
{  
     #pragma omp parallel shared(k)  
     sub3(k);  
}  
  
void sub3(int n)  
{  
    work(n);  
    #pragma omp barrier  
    work(n);  
}  
```