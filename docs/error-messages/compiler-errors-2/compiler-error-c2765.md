---
title: Compiler-Fehler C2765 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2765
dev_langs:
- C++
helpviewer_keywords:
- C2765
ms.assetid: 47ad86f3-a7e0-47ad-85ff-0f5534458cb9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 926cc1657db67530f866a2b2e00e4b23f4ccd0bb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2765"></a>Compiler-Fehler C2765 generiert
'Funktion': eine explizite Spezialisierung einer Funktionsvorlage darf Standardargumente haben  
  
 Standardargumente sind für eine explizite Spezialisierung einer Funktionsvorlage nicht zulässig. Weitere Informationen finden Sie unter [explizite Spezialisierung von Funktionsvorlagen](../../cpp/explicit-specialization-of-function-templates.md).  
  
 Im folgende Beispiel wird C2765 generiert:  
  
```  
// C2765.cpp  
template<class T> void f(T t) {};  
  
template<> void f<char>(char c = 'a') {}   // C2765  
// try the following line instead  
// template<> void f<char>(char c) {}  
```