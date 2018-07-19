---
title: Compilerfehler C3917 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3917
dev_langs:
- C++
helpviewer_keywords:
- C3917
ms.assetid: a24cd0c9-262f-46e5-9488-1c01f945933d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8bfed588ba24775f9ef793cbae3dc1542af9fc40
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33270602"
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