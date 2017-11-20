---
title: Compilerfehler C2511 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2511
dev_langs:
- C++
helpviewer_keywords:
- C2511
ms.assetid: df999efe-fe2b-418b-bb55-4af6a0592631
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 1ba01f808fb4dd618291777c1da7490b3b95af3c
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2511"></a>Compilerfehler C2511
'Bezeichner': überladene Memberfunktion in "Klasse" nicht gefunden.  
  
 Mit den angegebenen Parametern wird keine Version der Funktion deklariert.  Mögliche Ursachen:  
  
1.  Falsche Parameter an die Funktion übergeben.  
  
2.  In der falschen Reihenfolge übergebene Parameter.  
  
3.  Falsche Schreibweise von Parameternamen.  
  
 Im folgenden Beispiel wird C2511 generiert:  
  
```  
// C2511.cpp  
// compile with: /c  
class C {  
   int c_2;  
   int Func(char *, char *);  
};  
  
int C::Func(char *, char *, int i) {   // C2511  
// try the following line instead  
// int C::Func(char *, char *) {  
   return 0;  
}  
```