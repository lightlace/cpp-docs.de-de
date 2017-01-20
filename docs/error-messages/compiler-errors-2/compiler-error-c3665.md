---
title: "Compilerfehler C3665"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C3665"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3665"
ms.assetid: 893bb47e-8de1-43aa-af7d-fa47ad149ee9
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3665
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Destruktor': Der Überschreibungsspezifizierer 'Schlüsselwort' ist für einen Destruktor\/Finalizer nicht zulässig  
  
 Es wurde ein Schlüsselwort verwendet, das für einen Destruktor oder Finalizer nicht zulässig ist.  
  
 Es kann beispielsweise für einen Destruktor oder Finalizer kein neuer Slot angefordert werden.  Weitere Informationen finden Sie unter [Explizite Überschreibungen](../../windows/explicit-overrides-cpp-component-extensions.md) und [Destruktoren und Finalizer](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
 Im folgenden Beispiel wird C3665 generiert:  
  
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