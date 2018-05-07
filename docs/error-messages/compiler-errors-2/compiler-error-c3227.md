---
title: Compilerfehler C3227 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3227
dev_langs:
- C++
helpviewer_keywords:
- C3227
ms.assetid: 7939c23a-96c8-43c2-89e9-f217d132d155
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c4d156e70a1ac2c0b05e212ace81b8ccc32d8f2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3227"></a>Compilerfehler C3227
'Parameter': 'Schlüsselwort' zuweisen ein generischen Typs können keine  
  
 Um einen Typ zu instanziieren, ist ein geeigneter Konstruktor erforderlich. Der Compiler ist jedoch nicht in der Lage, stellen Sie sicher, dass ein geeigneter Konstruktor verfügbar ist.  
  
 Sie können Vorlagen anstelle von Generika verwenden, um diesen Fehler zu beheben, oder Sie können unterschiedliche Methoden zum Erstellen einer Instanz des Typs.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3227 generiert.  
  
```  
// C3227.cpp  
// compile with: /clr /c  
generic<class T> interface class ICreate {  
   static T Create();  
};  
  
generic <class T>  
where T : ICreate<T>  
ref class C {  
   void f() {  
      T t = new T;   // C3227  
  
      // OK  
      T t2 = ICreate<T>::Create();  
      T t3 = safe_cast<T>( System::Activator::CreateInstance(T::typeid) );  
   }  
};  
```