---
title: Compiler-Fehler C2624 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2624
dev_langs:
- C++
helpviewer_keywords:
- C2624
ms.assetid: 32f2ec15-a7cd-4049-a64b-131746d3152b
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c70165fc0d57d753dadd2bed207a00e3dd3498aa
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2624"></a>Compiler-Fehler C2624 generiert
lokale Klassen können nicht verwendet werden, um "Extern" Variablen zu deklarieren  
  
 Eine lokale Klasse oder Struktur nicht zur deklarieren `extern` Variablen.  
  
 Im folgende Beispiel wird C2624 generiert:  
  
```  
// C2624.cpp  
int main() {  
   struct C {};  
   extern C ac;   // C2624  
}  
```
