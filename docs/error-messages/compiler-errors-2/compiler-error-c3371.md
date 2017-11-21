---
title: Compilerfehler C3371 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3371
dev_langs: C++
helpviewer_keywords: C3371
ms.assetid: f7ecf1aa-ed0a-4f73-81e5-62cf98f88ea1
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1bc5af03841fe0a06b1ae0a31887565a3c1eb197
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3371"></a>Compilerfehler C3371
"idl_module": Hier ist nur die "name"-Eigenschaft zulässig  
  
 Die direkte Verwendung von[idl_module](../../windows/idl-module.md) in einer Funktionsdeklaration kann keine anderen Parameter als „name“ aufweisen.  
  
 Im folgenden Beispiel wird C3371 generiert:  
  
```  
// C3371.cpp  
[idl_module(name="Name", dllname="Some.dll")];  
[idl_module(name="Name", helpstring="Some help")]   // C3371  
int f1();  
// try  
// [idl_module(name="Name")]  
// int f1();  
  
int main()  
{  
}  
```