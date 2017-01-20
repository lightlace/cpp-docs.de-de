---
title: "CLS-Kompatibilit&#228;t: Warnung CLS03506"
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
  - "CLS03506"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS03506"
ms.assetid: baec820c-aabb-44c4-b0cd-043c3ca9c537
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "douge"
---
# CLS-Kompatibilit&#228;t: Warnung CLS03506
**Nach der CLS sind öffentlich sichtbare erforderliche Modifizierer \(modreq\) nicht zulässig, allerdings sind optionale Modifizierer \(modopt\), die sie nicht versteht, zulässig.**  
  
 Nach der CLS sind öffentlich sichtbare erforderliche Modifizierer \(modreq\) nicht zulässig, allerdings sind optionale Modifizierer \(modopt\), die sie nicht versteht, zulässig.  
  
 Stellen Sie sicher, dass Methodensignaturen keine Typen enthalten, die mit öffentlich sichtbaren, erforderlichen Modifizierern gekennzeichnet sind.  
  
 Weitere Informationen zur Überprüfung der CLS\-Kompatibilität \(Common Language Subset\) finden Sie unter [CLS\-kompatible Assemblys](assetId:///3320b57e-ea55-4697-a17d-f509a36a3c93).  
  
 Im folgenden Beispiel wird CLS03506 generiert:  
  
```  
// CLS03506.cpp // compile with: /clr /LD // CLS03506 expected using namespace System; using namespace System::Reflection; using namespace cli::language; [assembly:CLSCompliant (true)]; [assembly:AssemblyKeyFile("clscompliance.snk")]; public ref class One { public: void F1(volatile Int32 parameter) {}   // CLS03506 void F2( Int32 parameter) {}   // OK };  
```