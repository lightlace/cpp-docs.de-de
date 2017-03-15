---
title: "Compilerfehler C3062 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3062"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3062"
ms.assetid: 78632e6d-255f-42c3-b124-31a9194ff86d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C3062
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Enumeration': Für den Enumerator ist ein Wert erforderlich, da der zugrunde liegende Typ 'Typ' ist  
  
 Sie können für eine Enumeration einen zugrunde liegenden Typ angeben.  Für einige Typen ist es jedoch erfordelich, jedem Enumerator Werte zuzuweisen.  
  
 Weitere Informationen über Enumerationen finden Sie unter [enum class](../../windows/enum-class-cpp-component-extensions.md).  
  
 Im folgenden Beispiel wird C3062 generiert:  
  
```  
// C3062.cpp  
// compile with: /clr  
  
enum class MyEnum : bool { a };   // C3062  
enum class MyEnum2 : bool { a = true};   // OK  
```