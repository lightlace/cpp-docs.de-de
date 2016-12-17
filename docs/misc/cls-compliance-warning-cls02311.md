---
title: "CLS-Kompatibilit&#228;tswarnung CLS02311"
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
  - "CLS02311"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS02311"
ms.assetid: 2faddffb-866d-417f-9ff3-9c61616030fb
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "douge"
---
# CLS-Kompatibilit&#228;tswarnung CLS02311
Eine CLS\-kompatible Klasse muss von einer CLS\-kompatiblen Klasse erben.  
  
 Eine CLS\-kompatible Klasse muss von einer CLS\-kompatiblen Klasse erben.  Beispiel: 'System::Object'.  
  
 Weitere Informationen zur CLS\-Kompatibilitätsprüfung finden Sie unter [CLS\-kompatible Assemblys](assetId:///3320b57e-ea55-4697-a17d-f509a36a3c93).  
  
 Im folgenden Beispiel wird CLS02311 generiert:  
  
```  
// CLS02311.cpp // compile with: /clr /LD // CLS02311 expected using namespace System; using namespace System::Reflection; [assembly:CLSCompliant (true)]; [assembly:AssemblyKeyFile("clscompliance.snk")]; [CLSCompliant(true)] public ref class CompliantType {}; [CLSCompliant(false)] public ref class NotCompliantType {}; public ref class One : public NotCompliantType {};   // CLS02311 public ref class Two : public CompliantType {};   // OK  
```