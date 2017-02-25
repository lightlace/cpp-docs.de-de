---
title: "Compilerfehler C3284 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3824"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3284"
ms.assetid: e582f316-e9db-4d27-9c70-fdfa737a9d5f
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C3284
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Einschränkungen für den generischen Parameter 'Parameter' der 'Funktion'\-Funktion müssen mit den Einschränkungen für den generischen Parameter 'Parameter' der 'Funktion'\-Funktion übereinstimmen.  
  
 Eine virtuelle generische Funktion muss die gleichen Einschränkungen wie eine virtuelle Funktion mit demselben Namen und Satz von Argumenten in der Basisklasse verwenden.  
  
 Im folgenden Beispiel wird C3284 generiert:  
  
```  
// C3284.cpp // compile with: /clr /c // C3284 expected public interface class IGettable { int Get(); }; public interface class B { generic<typename T> where T : IGettable virtual int mf(T t); }; public ref class D : public B { public: generic<typename T> // Uncomment the following line to resolve. // where T : IGettable virtual int mf(T t) { return 4; } };  
```