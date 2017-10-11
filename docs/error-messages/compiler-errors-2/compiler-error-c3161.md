---
title: Compiler-Fehler C3161 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3161
dev_langs:
- C++
helpviewer_keywords:
- C3161
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 4be981b2af166d85a3a83209a901f3e3e51b6246
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3161"></a>Compiler-Fehler C3161 generiert
'Schnittstelle': Schachteln von Klasse, Struktur, Union oder eine Schnittstelle in einer Schnittstelle ist nicht zulässig. Schachteln einer Schnittstelle in einer Klasse, Struktur oder Union ist nicht zulässig  
  
 Ein [__interface](../../cpp/interface.md) kann nur verwendet werden, im globalen Gültigkeitsbereich oder innerhalb eines Namespace. Eine Klasse, Struktur oder Union kann nicht in einer Schnittstelle angezeigt.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3161 generiert.  
  
```  
// C3161.cpp  
// compile with: /c  
__interface X {  
   __interface Y {};   // C3161 A nested interface  
};  
```
