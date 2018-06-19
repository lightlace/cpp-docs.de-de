---
title: Compilerfehler C3848 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3848
dev_langs:
- C++
helpviewer_keywords:
- C3848
ms.assetid: 32d3ccef-01ec-4f8b-bbff-fb9b1a76b4c4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 37354d30ab20820657fc048cac0f87aa1a958dfa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33267172"
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