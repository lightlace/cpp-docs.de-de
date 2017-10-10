---
title: Compilerfehler C2466 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2466
dev_langs:
- C++
helpviewer_keywords:
- C2466
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 3c3ad19ce37aa51bd6b670da6e857d7eccce04ca
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2466"></a>Compilerfehler C2466
ein Array von Konstanten Größe 0 kann nicht zugeordnet werden.  
  
 Ein Array ist reserviert oder mit der Größe 0 (null) deklariert. Der Konstante Ausdruck für die Arraygröße muss eine ganze Zahl größer als 0 (null) sein. Eine Arraydeklaration eine Nullindex ist zulässig, nur für eine Klasse, Struktur oder union-Member und nur mit Microsoft-Erweiterungen (["/ Ze"](../../build/reference/za-ze-disable-language-extensions.md)).  
  
 Im folgende Beispiel wird C2466 generiert:  
  
```  
// C2466.cpp  
// compile with: /c  
int i[0];   // C2466  
int j[1];   // OK  
char *p;  
```
