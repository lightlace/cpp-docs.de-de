---
title: Compilerfehler C3671 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3671
dev_langs: C++
helpviewer_keywords: C3671
ms.assetid: d684e4ae-87e2-4424-80bb-6f346652c831
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e9e7b79fd8f45bb85a34506c3a288bb1c8a5042e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3671"></a>Compilerfehler C3671
'Funktion_1': Funktion überschreibt keine 'Funktion_2'  
  
 Bei der expliziten Überschreibungssyntax zu verwenden, generiert der Compiler einen Fehler aus, wenn eine Funktion nicht überschrieben wird.  Finden Sie unter [explizite Überschreibungen](../../windows/explicit-overrides-cpp-component-extensions.md) für Weitere Informationen.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3671 generiert.  
  
```  
// C3671.cpp  
// compile with: /clr /c  
ref struct S {  
   virtual void f();  
};  
  
ref struct S1 : S {  
   virtual void f(int) new sealed = S::f;   // C3671  
   virtual void f() new sealed = S::f;  
};  
```