---
title: Compilerfehler C2042 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2042
dev_langs:
- C++
helpviewer_keywords:
- C2042
ms.assetid: e111788f-41ce-405a-9824-a4c1c26059e6
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 7907e4407e58e6c05a4c352d78d744d4226153dd
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2042"></a>Compilerfehler C2042
Die Schlüsselwörter "signed/unsigned" schließen sich gegenseitig aus  
  
 Die Schlüsselwörter `signed` und `unsigned` werden innerhalb der gleichen Deklaration verwendet.  
  
 Im folgenden Beispiel wird C2042 generiert:  
  
```  
// C2042.cpp  
unsigned signed int i;   // C2042  
```  
  
 Mögliche Lösung:  
  
```  
// C2042b.cpp  
// compile with: /c  
unsigned int i;  
signed int ii;  
```
