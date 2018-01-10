---
title: Compilerfehler C2384 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2384
dev_langs: C++
helpviewer_keywords: C2384
ms.assetid: 8145f7ad-31b1-406d-ac43-0d557feab635
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a7494c38c787a0e0877496a8f65556d568d77f7d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2384"></a>Compilerfehler C2384
„Member“ : __declspec(thread) kann nicht auf einen Member einer managed- oder WinRT-Klasse angewendet werden.  
  
 Die [Thread](../../cpp/thread.md) `__declspec` Modifizierer kann nicht auf einen Member eines verwalteten oder Windows-Runtime-Klasse verwendet werden.  
  
 Der statische threadlokale Speicher kann im verwalteten Code nur für statisch geladene DLLs verwendet werden; die DLL muss bei Prozessstart statisch geladen sein. Windows-Runtime unterstützt keinen lokalen Threadspeicher.  
  
 Mit der folgenden Zeile wird C2384 generiert und gezeigt, wie dieser Fehler im C++-/CLI-Code behoben werden kann:  
  
```  
// C2384.cpp  
// compile with: /clr /c  
public ref class B {  
public:  
   __declspec( thread ) static int tls_i = 1;   // C2384  
  
   // OK - declare with attribute instead  
   [System::ThreadStaticAttribute]  
   static int tls_j;  
};  
```