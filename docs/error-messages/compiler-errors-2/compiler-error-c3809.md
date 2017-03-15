---
title: "Compilerfehler C3809 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3809"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3809"
ms.assetid: 37eca584-c20c-464e-8e45-a987214b7ce4
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C3809
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class': Ein verwalteter oder WinRT\-Typ kann weder über Friends, Funktionen, Klassen noch Schnittstellen verfügen  
  
 Friends werden durch verwaltete und Windows\-Runtime\-Typen nicht unterstützt.  Deklarieren Sie zum Beheben dieses Fehlers Friends nicht innerhalb von verwalteten oder Windows\-Runtime\-Typen.  
  
 Im folgenden Beispiel wird C3809 generiert.  
  
```  
// C3809a.cpp  
// compile with: /clr  
ref class A {};  
  
ref class B  
{  
public:  
   friend ref class A;   // C3809  
};  
  
int main()  
{  
}  
```