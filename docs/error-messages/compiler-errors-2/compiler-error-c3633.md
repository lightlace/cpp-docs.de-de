---
title: Compilerfehler C3633 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3633
dev_langs: C++
helpviewer_keywords: C3633
ms.assetid: 7d65babf-2191-4d67-a69f-f5c4c2ddf946
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 982075cdaa72ddd5b1a4fdafdeaaf433b27bcf77
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3633"></a>Compilerfehler C3633
'Member' kann nicht als Member des verwalteten 'Typs' definiert werden.  
  
CLR-Verweisklassendatenmember darf nicht von einer nicht - POD-C++-Typ sein.  Sie können nur einen systemeigenen POD-Typ in einen CLR-Typ instanziieren.  Beispielsweise darf kein POD-Typ einen Kopierkonstruktor oder Zuweisungsoperator enthalten.  
  
## <a name="example"></a>Beispiel  
Im folgende Beispiel wird C3633 generiert.  
  
```  
// C3633.cpp  
// compile with: /clr /c  
#pragma warning( disable : 4368 )  
  
class A1 {  
public:  
   A1() { II = 0; }  
   int II;  
};  
  
ref class B {  
public:  
   A1 a1;   // C3633  
   A1 * a2;   // OK  
   B() : a2( new A1 ) {}  
    ~B() { delete a2; }  
};  
```  
