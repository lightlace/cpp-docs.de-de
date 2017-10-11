---
title: Compilerfehler C3917 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3917
dev_langs:
- C++
helpviewer_keywords:
- C3917
ms.assetid: a24cd0c9-262f-46e5-9488-1c01f945933d
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 87ff4bde3b37e630f4d6a4a64f12039cf98ff2be
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3917"></a>Compilerfehler C3917
"*Eigenschaft*": Veralteter Deklarationsstil Konstrukt  
  
Die Definition einer Eigenschaft oder Ereignis verwendet die Syntax von einer Version vor Visual Studio 2005.  
  
Weitere Informationen finden Sie unter [property](../../windows/property-cpp-component-extensions.md).  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// C3917.cpp  
// compile with: /clr /c  
public ref class  C {  
private:  
   int m_length;  
public:  
   C() {  
      m_length = 0;  
   }  
  
   property int get_Length();   // C3917  
  
   // The correct property definition:  
   property int Length {  
      int get() {  
         return m_length;  
      }  
  
      void set( int i ) {  
         m_length = i;  
      }  
   }  
};  
```
