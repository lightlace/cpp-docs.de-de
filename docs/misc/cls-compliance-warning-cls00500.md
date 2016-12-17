---
title: "CLS-Kompatibilit&#228;tswarnung CLS00500"
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CLS00500"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS00500"
ms.assetid: faaf377e-3738-4c0d-9a51-09db4073564e
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "douge"
---
# CLS-Kompatibilit&#228;tswarnung CLS00500
Alle Namen in einem CLS\-kompatiblen Bereich müssen in ihrer Art eindeutig unabhängig sein.  
  
 Alle Namen, die in einem CLS\-kompatiblen Bereich eingeführt werden, müssen in ihrer Art eindeutig unabhängig sein, außer bei identischen Namen, die durch Überladen aufgelöst werden. Für CLS sind zwei Namen identisch, wenn ihre kleingeschriebenen Zuordnungen identisch sind. Nur Eigenschaften und Funktionen können überladen werden. Wenn sie überladen sind, sollten Eigenschaften und Funktionen allein basierend auf der Anzahl und den Typen ihrer Parameter überladen werden, außer den Konvertierungsoperatoren, die auch auf Grundlage des Rückgabetyps überladen werden können. Weitere Informationen finden Sie unter [Benutzerdefinierte Konvertierungen](../dotnet/user-defined-conversions-cpp-cli.md).  
  
 Weitere Informationen zur CLS\-Kompatibilitätsprüfung finden Sie unter [CLS\-kompatible Assemblys](assetId:///3320b57e-ea55-4697-a17d-f509a36a3c93).  
  
 Im folgenden Beispiel wird CLS00500 generiert:  
  
```  
// CLS00500.cpp // compile with: /clr /LD // CLS00500 expected using namespace System; using namespace System::Reflection; [assembly:AssemblyKeyFile("clscompliance.snk")]; [assembly:System::CLSCompliant(true)]; public ref class a {}; public ref class A {};   // CLS00500  
```