---
title: Compilerfehler C3874 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3874
dev_langs:
- C++
helpviewer_keywords:
- C3874
ms.assetid: fd55fc05-69a7-4237-b3b7-dca1d5400b4f
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: cd30858e2118a7305583736c31b84ed56ab7095a
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3874"></a>Compilerfehler C3874
Rückgabetyp "Funktion" sollte "Int" anstelle von "Typ" sein.  
  
 Eine Funktion besitzt nicht den Rückgabetyp, der vom Compiler erwartet wurde.  
  
 Im folgende Beispiel wird C3874 generiert:  
  
```  
// C3874b.cpp  
double main()  
{   // C3874  
}  
```