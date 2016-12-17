---
title: "Compilerfehler C3271"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C3271"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3271"
ms.assetid: 16d8bd1d-2e30-4c6a-a07f-0c4f3342fab5
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3271
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Member": Ungültiger Wert "Wert" für das FieldOffset\-Attribut.  
  
 Es wurde eine negative Zahl an das [FieldOffset](frlrfSystemRuntimeInteropServicesFieldOffsetAttributeClassTopic)\-Attribut übergeben.  
  
 Im folgenden Beispiel wird C3271 generiert:  
  
```  
// C3271.cpp // compile with: /clr /c using namespace System; using namespace System::Runtime::InteropServices; [StructLayout(LayoutKind::Explicit)] value class MyStruct1 { public: [FieldOffset(0)] int a; public: [FieldOffset(-1)] long b;   // C3271 };  
```  
  
 Im folgenden Beispiel wird C3271 generiert:  
  
```  
// C3271_2.cpp // compile with: /clr:oldSyntax using namespace System; using namespace System::Runtime::InteropServices; [StructLayout(LayoutKind::Explicit)] __value class MyStruct1 { public: [FieldOffset(0)] int a; public: [FieldOffset(-1)] long b;   // C3271 }; static int main() { MyStruct1* a = __nogc new MyStruct1(); };  
```