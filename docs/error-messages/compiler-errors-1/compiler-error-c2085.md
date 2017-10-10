---
title: Compilerfehler Fehler C2085 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2085
dev_langs:
- C++
helpviewer_keywords:
- C2085
ms.assetid: 0a86785c-8e6f-481b-8c7b-412220c1950d
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 45805bbea2eca77ae81922088471e99de26be1e4
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2085"></a>Compilerfehler Fehler C2085
'Bezeichner': nicht in der Liste formaler Parameter  
  
 Der Bezeichner wurde in einer Funktionsdefinition, aber nicht in der Liste formaler Parameter deklariert. (Nur ANSI-C)  
  
 Im folgende Beispiel wird C2085 generiert:  
  
```  
// C2085.c  
void func1( void )  
int main( void ) {}   // C2085  
```  
  
 Mögliche Lösung:  
  
```  
// C2085b.c  
void func1( void );  
int main( void ) {}  
```  
  
 Das Semikolon fehlt, `func1()` einer Funktionsdefinition, nicht um einen Prototyp, deshalb sieht `main` ist definiert in `func1()`, generieren Fehler C2085 für Bezeichner `main`.
