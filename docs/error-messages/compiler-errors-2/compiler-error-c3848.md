---
title: Compilerfehler C3848 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3848
dev_langs: C++
helpviewer_keywords: C3848
ms.assetid: 32d3ccef-01ec-4f8b-bbff-fb9b1a76b4c4
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3220d3d278c0b5d877273b96defc23ac5852e066
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3848"></a>Compilerfehler C3848
Ausdruck mit Typ 'Typ' würden einige Const-Volatile-Qualifizierer 'Function' für den Aufruf verlieren  
  
 Eine Variable mit einem angegebenen Const-Volatile-Typ kann Member nur mit dieselbe oder eine höhere Const-Volatile-Qualifikationen definierten Funktionen aufrufen.  
  
 In den folgenden Beispielen wird C3848 generiert:  
  
```  
// C3848.cpp  
void glbFunc1()  
{  
}  
  
typedef void (* pFunc1)();  
  
struct S3  
{  
   operator pFunc1() // const  
   {  
      return &glbFunc1;  
   }  
};  
  
int main()  
{  
   const S3 s3;  
   s3();   // C3848, uncomment const qualifier  
}  
```