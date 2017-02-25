---
title: "Compilerfehler C3270 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3270"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3270"
ms.assetid: 70e6e76b-7415-48f5-a61e-2ed50caf08e4
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C3270
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Feld": Das FieldOffset\-Attribut ist im Kontext von "StructLayout\(Explicit\)" erforderlich und kann nur in diesem Kontext verwendet werden  
  
 Ein Feld wurde mit [FieldOffset](frlrfSystemRuntimeInteropServicesFieldOffsetAttributeClassTopic) gekennzeichnet. Dies ist jedoch nur zulässig, wenn [StructLayout](frlrfSystemRuntimeInteropServicesStructLayoutAttributeClassTopic) explizit definiert ist.  
  
 Im folgenden Beispiel wird C3270 generiert:  
  
```  
// C3270_2.cpp // compile with: /clr /c using namespace System::Runtime::InteropServices; [ StructLayout(LayoutKind::Sequential) ] // try the following line instead // [ StructLayout(LayoutKind::Explicit) ] public value struct MYUNION { [FieldOffset(0)] int a;   // C3270 // ... };  
```  
  
 Im folgenden Beispiel wird C3270 generiert:  
  
```  
// C3270.cpp // compile with: /clr:oldSyntax /LD #using <mscorlib.dll> using namespace System::Runtime::InteropServices; [ StructLayout(LayoutKind::Sequential) ] // try the following line instead // [ StructLayout(LayoutKind::Explicit) ] public __value struct MYUNION { [FieldOffset(0)] int a;   // C3270 // ... };  
```