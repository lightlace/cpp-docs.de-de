---
title: Compiler-Fehler C3114 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3114
dev_langs:
- C++
helpviewer_keywords:
- C3114
ms.assetid: b5d2df4f-87d0-4292-9981-25c6a6013c05
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 69001d415167f976d0f30c2dd5a0181cc032d0d1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33246267"
---
# <a name="compiler-error-c3114"></a>Compiler-Fehler C3114 generiert
'Argument': kein gültiges benanntes Attributargument.  
  
 In der Reihenfolge für Datenmember einer Attributklasse ein gültiges benanntes Argument sein, er muss nicht gekennzeichnet werden `static`, `const`, oder `literal`. Wenn eine Eigenschaft, die Eigenschaft muss nicht `static` und verfügen über get- und set-Accessoren müssen.  
  
 Weitere Informationen finden Sie unter [Eigenschaft](../../windows/property-cpp-component-extensions.md) und [benutzerdefinierte Attribute](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3114 generiert.  
  
```  
// C3114.cpp  
// compile with: /clr /c  
public ref class A : System::Attribute {  
public:  
   static property int StaticProp {  
      int get();  
   }  
  
   property int Prop2 {  
      int get();  
      void set(int i);  
   }  
};  
  
[A(StaticProp=123)]   // C3114  
public ref class R {};  
  
[A(Prop2=123)]   // OK  
public ref class S {};  
```