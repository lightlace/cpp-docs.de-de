---
title: "CLS-Kompatibilit&#228;tswarnung CLS03606"
ms.custom: na
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CLS03606"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS03606"
ms.assetid: 567b0b18-7487-4f48-a9ae-a4a4db53a409
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "douge"
---
# CLS-Kompatibilit&#228;tswarnung CLS03606
Globale static\-Methoden sind nicht CLS\-kompatibel.  
  
 Globale static\-Felder und Methoden sind nicht CLS\-kompatibel.  
  
 Weitere Informationen zur Überprüfung der CLS\-Kompatibilität \(Common Language Subset\) finden Sie unter [CLS\-kompatible Assemblys](assetId:///3320b57e-ea55-4697-a17d-f509a36a3c93).  
  
 Im folgenden Beispiel wird CLS03606 generiert:  
  
```  
// CLS03606.cpp // compile with: /clr /LD // CLS03606 expected using namespace System; using namespace System::Reflection; [assembly:CLSCompliant (true)]; [assembly:AssemblyKeyFile("clscompliance.snk")]; void MyGlobalFunction1() {}   // CLS03606 public ref class MyClass { public: void MemberFunction() {}   // OK };  
```