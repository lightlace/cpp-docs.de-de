---
title: Compilerfehler Fehler C2086 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2086
dev_langs:
- C++
helpviewer_keywords:
- C2086
ms.assetid: 4329bf72-90c8-444c-8524-4ef75e6b2139
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 36270e50049889e5c6819a22b6b6e35d4c7d2caf
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2086"></a>Compilerfehler Fehler C2086
'Bezeichner': Neudefinition  
  
 Der Bezeichner mehrfach definiert ist, oder eine nachfolgende Deklaration unterscheidet sich von einer vorherigen.  
  
 C2086 kann auch das Ergebnis der inkrementellen Buildvorgangs für eine C#-Assembly sein. Erstellen Sie zum Beheben dieses Fehlers die C#-Assembly neu.  
  
 Im folgenden Beispiel wird C2086 generiert:  
  
```  
// C2086.cpp  
main() {  
  int a;  
  int a;   // C2086 not an error in ANSI C  
}  
```
