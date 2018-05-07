---
title: Compilerfehler C3809 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3809
dev_langs:
- C++
helpviewer_keywords:
- C3809
ms.assetid: 37eca584-c20c-464e-8e45-a987214b7ce4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4b9fabec4da63bfe881e0020e99cd5c49a51789
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3809"></a>Compilerfehler C3809
'class': Ein verwalteter oder WinRT-Typ kann weder über Friends, Funktionen, Klassen noch Schnittstellen verfügen  
  
 Friends werden durch verwaltete und Windows-Runtime-Typen nicht unterstützt. Deklarieren Sie zum Beheben dieses Fehlers Friends nicht innerhalb von verwalteten oder Windows-Runtime-Typen.  
  
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