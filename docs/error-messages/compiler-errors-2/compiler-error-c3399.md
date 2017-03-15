---
title: "Compilerfehler C3399 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3399"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3399"
ms.assetid: 306ad199-d150-4f6c-bcf1-24a7948b93be
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# Compilerfehler C3399
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ': Beim Erstellen einer Instanz eines generischen Parameters können Argumente nicht bereitgestellt werden.  
  
 Wenn Sie die `gcnew()`\-Einschränkung angeben, geben Sie auch an, dass der Einschränkungstyp über einen parameterlosen Konstruktor verfügt. Aus diesem Grund tritt bei dem Versuch ein Fehler auf, diesen Typ zu instanziieren und einen Parameter zu übergeben.  
  
 Weitere Informationen finden Sie unter [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3399 generiert:  
  
```  
// C3399.cpp // compile with: /clr /c generic <class T> where T : gcnew() void f() { T t = gcnew T(1);   // C3399 T t2 = gcnew T();   // OK }  
```