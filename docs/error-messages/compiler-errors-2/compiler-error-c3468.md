---
title: Compilerfehler C3468 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3468
dev_langs: C++
helpviewer_keywords: C3468
ms.assetid: cfd320db-2f6e-4e0d-ba02-e79ece87e1e0
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 41fde9cae4697c38dba410fb1fbdb46cd901ae97
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3468"></a>Compilerfehler C3468
"Typ": Sie können einen Typ nur an eine Assembly weiterleiten:  
  
 `file`ist keine Assembly.  
  
 Es können nur Typen in einer Assembly weitergeleitet werden.  
  
 Weitere Informationen finden Sie unter [Typweiterleitung (C + c++ / CLI)](../../windows/type-forwarding-cpp-cli.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Modul erstellt.  
  
```  
// C3468.cpp  
// compile with: /LN /clr  
public ref class R {};  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3468 generiert:  
  
```  
// C3468_b.cpp  
// compile with: /clr /c  
#using "C3468.netmodule"  
[ assembly:TypeForwardedTo(R::typeid) ];   // C3468  
```