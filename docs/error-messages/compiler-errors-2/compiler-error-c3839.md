---
title: "Compilerfehler C3839 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3839"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3839"
ms.assetid: 0957faff-1e9f-439b-876b-85bd8d2c578d
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Compilerfehler C3839
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ändern der Ausrichtung in einem verwalteten oder WinRT\-Typ nicht möglich  
  
 Die Ausrichtung der Variablen in verwalteten oder Windows\-Runtime\-Typen wird durch die CLR oder Windows\-Runtime gesteuert und kann nicht mithilfe der Option zum Ausrichten [](../../cpp/align-cpp.md "align (C++)") geändert werden.  
  
 Im folgenden Beispiel wird C3839 generiert:  
  
```  
// C3839a.cpp  
// compile with: /clr  
ref class C  
{  
public:  
   __declspec(align(32)) int m_j; // C3839  
};  
  
int main()  
{  
}  
  
```