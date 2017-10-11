---
title: Compiler-Fehler C3194 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3194
dev_langs:
- C++
helpviewer_keywords:
- C3194
ms.assetid: 49d3ffc6-eff6-4b46-865b-18811692a8bb
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 4ddfc0c87f4f58850eec595dcf35436590177283
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3194"></a>Compiler-Fehler C3194 generiert
'Member': ein Werttyp keinen Zuweisungsoperator  
  
 Spezielle Memberfunktionen, die automatischen Aufruf durch den Compiler, z. B. ein Kopierkonstruktor oder Kopierzuweisungsoperator erfordern werden innerhalb einer Wertklasse nicht unterstützt.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3194 generiert.  
  
```  
// C3194.cpp  
// compile with: /clr /c  
value struct MyStruct {  
   MyStruct& operator= (const MyStruct& i) { return *this; }   // C3194  
};  
  
ref struct MyStruct2 {  
   MyStruct2% operator= (const MyStruct2% i) { return *this; }   // OK  
};  
```
