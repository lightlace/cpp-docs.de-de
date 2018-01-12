---
title: Compilerfehler C3364 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3364
dev_langs: C++
helpviewer_keywords: C3364
ms.assetid: 98654741-60fe-4472-a6af-e580f8c0a6e1
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cdf9f9a6d4ae6584ff3b30e71a0c74b0ca777afe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3364"></a>Compilerfehler C3364
'Delegat': Delegatkonstruktor: Argument muss ein Zeiger auf Memberfunktion einer verwalteten Klasse oder einer globalen Funktion sein  
  
 Der zweite Parameter des Delegatkonstruktors akzeptiert die Adresse einer Memberfunktion oder die Adresse einer statischen Memberfunktion einer beliebigen Klasse. Beide werden als einfache Adressen behandelt.  
  
 Im folgende Beispiel wird C3364 generiert:  
  
```  
// C3364_2.cpp  
// compile with: /clr  
  
delegate int D( int, int );  
  
ref class C {  
public:  
   int mf( int, int ) {  
      return 1;  
   }  
};  
  
int main() {  
   C^ pC = gcnew C;  
   System::Delegate^ pD = gcnew D( pC,pC->mf( 1, 2 ) ); // C3364  
  
   // try the following line instead  
   // System::Delegate^ pD = gcnew D(pC, &C::mf);  
}  
```  
