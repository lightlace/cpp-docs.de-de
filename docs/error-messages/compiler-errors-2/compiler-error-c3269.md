---
title: Compilerfehler C3269 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3269
dev_langs: C++
helpviewer_keywords: C3269
ms.assetid: c575f067-244d-4dd5-bf58-9e7630ea58b7
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8b78b9342d29910271ee7f9cadaa6e2814b7f5b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3269"></a>Compilerfehler C3269
'Funktion': eine Memberfunktion einer verwalteten oder WinRTtype kann nicht mit "..." deklariert werden  
  
Verwaltete und WinRT-Klassenmemberfunktionen können keine Parameterlisten variabler Länge deklarieren.  
  
Im folgenden Beispiel wird C3269 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3269_2.cpp  
// compile with: /clr  
  
ref struct A  
{  
   void func(int i, ...)   // C3269  
   // try the following line instead  
   // void func(int i )  
   {  
   }  
};  
  
int main()  
{  
}  
```  
