---
title: Compilerfehler C3653 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3653
dev_langs: C++
helpviewer_keywords: C3653
ms.assetid: 316549d7-f7ef-4578-a2ba-57adc8aac527
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c061e0f8e21b4f0e9fcf8d924729490b325b8edf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3653"></a>Compilerfehler C3653
'Funktion': kann nicht als benannte Überschreibung verwendet werden: eine Funktion, die überschrieben wurde nicht gefunden; haben Sie vergessen, den Funktionsnamen explizit mithilfe einer:: Operator?  
  
 Ein explizites Überschreiben angegeben, eine Funktion, die nicht in einer beliebigen Schnittstelle gefunden wurde. Weitere Informationen finden Sie unter [explizite Überschreibungen](../../windows/explicit-overrides-cpp-component-extensions.md).  
  
 Im folgende Beispiel wird C3653 generiert:  
  
```  
// C3653.cpp  
// compile with: /clr  
public interface struct I {  
   void h();  
};  
  
public ref struct X : public I {  
   virtual void f() new sealed = J {};   // C3653 no J in scope  
   virtual void g() {}   // OK  
   virtual void h() new sealed = I::h {};   // OK  
};  
```