---
title: Compilerfehler C2144 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2144
dev_langs:
- C++
helpviewer_keywords:
- C2144
ms.assetid: 49f3959b-324f-4c06-9588-c0ecef5dc5b3
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0f541465009dcc137b8853351d10ceb9d5db4d05
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2144"></a>Compilerfehler C2144
Syntaxfehler: 'Typ' soll 'Token' voranstehen  
  
 Der Compiler erwartet `token` und `type` stattdessen.  
  
 Dieser Fehler kann durch eine fehlende schließende Klammer gefunden, schließende Klammern oder durch Semikolons verursacht werden.  
  
 C2144 kann auch auftreten, wenn Sie versuchen, erstellen Sie ein Makro aus einem CLR-Schlüsselwort, das ein Leerzeichen enthält.  
  
 C2144 möglicherweise auch angezeigt, wenn Sie versuchen, die Weiterleitung eingeben. Finden Sie unter [Typweiterleitung (C + c++ / CLI)](../../windows/type-forwarding-cpp-cli.md) für Weitere Informationen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2144 generiert.  
  
```  
// C2144.cpp  
// compile with: /clr /c  
#define REF ref  
REF struct MyStruct0;   // C2144  
  
// OK  
#define REF1 ref struct  
REF1 MyStruct1;  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2144 generiert.  
  
```  
// C2144_2.cpp  
// compile with: /clr /c  
ref struct X {  
  
   property double MultiDimProp[,,] {   // C2144  
   // try the following line instead  
   // property double MultiDimProp[int , int, int] {  
      double get(int, int, int) { return 1; }  
      void set(int i, int j, int k, double l) {}  
   }  
  
   property double MultiDimProp2[] {   // C2144  
   // try the following line instead  
   // property double MultiDimProp2[int] {  
      double get(int) { return 1; }  
      void set(int i, double l) {}  
   }  
};  
```
