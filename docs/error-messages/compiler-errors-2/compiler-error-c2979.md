---
title: Compilerfehler C2979 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2979
dev_langs: C++
helpviewer_keywords: C2979
ms.assetid: 98bd9043-ec44-451e-a482-3a8e35fc7464
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: de9cff3ec44bc0a44055264f6aab0b54ca5f543e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2979"></a>Compilerfehler C2979
Explizite Spezialisierungen werden für Generika nicht unterstützt.  
  
 Eine generische Klasse wurde falsch deklariert.  Finden Sie unter [Generika](../../windows/generics-cpp-component-extensions.md) für Weitere Informationen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2979 generiert.  
  
```  
// C2979.cpp  
// compile with: /clr /c  
generic <>   
ref class Utils {};   // C2979 error  
  
generic <class T>  
ref class Utils2 {};   // OK  
```