---
title: Compilerfehler C3381 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3381
dev_langs: C++
helpviewer_keywords: C3381
ms.assetid: d276c89f-8377-4cb6-a8d4-7770885f06c4
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6b1a56658874eb5a62db7d272b40612e34bfc94a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3381"></a>Compilerfehler C3381
'Assembly': Assemblyzugriffsspezifizierer sind nur in Code verfügbar, der mit einer /clr-Option kompiliert wurde  
  
 Systemeigene Typen können außerhalb der Assembly sichtbar sein, aber Sie können nur Assemblyzugriff für systemeigene Typen in einem **"/ CLR"** Kompilierung.  
  
 Weitere Informationen finden Sie unter [geben Sichtbarkeit](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) und [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3381 generiert.  
  
```  
// C3381.cpp  
// compile with: /c  
public class A {};   // C3381  
```