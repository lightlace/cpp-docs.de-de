---
title: Compilerfehler C3839 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3839
dev_langs:
- C++
helpviewer_keywords:
- C3839
ms.assetid: 0957faff-1e9f-439b-876b-85bd8d2c578d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cbb5541e07d168df36bae83f81b7b8a8a7273665
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33269513"
---
# <a name="compiler-error-c3839"></a>Compilerfehler C3839
Ändern der Ausrichtung in einem verwalteten oder WinRT-Typ nicht möglich  
  
 Die Ausrichtung von Variablen in verwalteten oder Windows-Runtime-Typen wird durch die CLR oder Windows-Runtime gesteuert und kann nicht geändert werden, mit [ausrichten](../../cpp/align-cpp.md).  
  
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