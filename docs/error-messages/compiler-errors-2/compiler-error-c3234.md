---
title: Compilerfehler C3234 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3234
dev_langs:
- C++
helpviewer_keywords:
- C3234
ms.assetid: ebefc15a-e40d-424b-a3dd-d7e185d0ed7b
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 96291111e8814eb1500ab0dab42c0c6ab90ccda1
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3234"></a>Compilerfehler C3234
Eine generische Klasse kann nicht von einem generischen Typparameter abgeleitet werden.  
  
 Eine generische Klasse kann nicht von einem generischen Typparameter erben.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3234 generiert:  
  
```  
// C3234.cpp  
// compile with: /clr /c  
generic <class T>  
public ref class C : T {};   // C3234  
// try the following line instead  
// public ref class C {};  
```
