---
title: Compilerfehler C3665 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3665
dev_langs:
- C++
helpviewer_keywords:
- C3665
ms.assetid: 893bb47e-8de1-43aa-af7d-fa47ad149ee9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e55be277f5016be2440987864e67dfc54f4cd094
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3665"></a>Compilerfehler C3665
'Destruktor': Der Überschreibungsspezifizierer 'Schlüsselwort' ist für einen Destruktor/Finalizer nicht zulässig  
  
 Es wurde ein Schlüsselwort verwendet, das für einen Destruktor oder Finalizer nicht zulässig ist.  
  
 Es kann beispielsweise für einen Destruktor oder Finalizer kein neuer Slot angefordert werden.  Weitere Informationen finden Sie unter [explizite Überschreibungen](../../windows/explicit-overrides-cpp-component-extensions.md) und [Destruktoren und Finalizer](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
 Im folgende Beispiel wird C3665 generiert:  
  
```  
// C3665.cpp  
// compile with: /clr  
public ref struct R {  
   virtual ~R() { }  
   virtual void a() { }  
};  
  
public ref struct S : R {  
   virtual ~S() new {}   // C3665  
   virtual void a() new {}   // OK  
};  
```