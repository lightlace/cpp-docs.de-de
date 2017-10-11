---
title: Compilerfehler C2534 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2534
dev_langs:
- C++
helpviewer_keywords:
- C2534
ms.assetid: 481f9f54-5b51-4aa0-8eea-218f10807705
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: ee5b0e009833ca4f67f87bb234881b044215d5f0
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2534"></a>Compilerfehler C2534
'Bezeichner': Konstruktor kann keinen Wert zurückgeben  
  
 Ein Konstruktor kann keinen Wert zurück oder einen Rückgabetyp haben (auch eine `void` Rückgabetyp).  
  
 Dieser Fehler kann behoben werden, durch das Entfernen der `return` Anweisung aus der Konstruktordefinition.  
  
 Im folgende Beispiel wird C2534 generiert:  
  
```  
// C2534.cpp  
class A {  
public:  
   int i;  
   A() { return i; }   // C2534  
};  
```
