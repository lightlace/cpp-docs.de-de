---
title: Compilerfehler C3399 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3399
dev_langs: C++
helpviewer_keywords: C3399
ms.assetid: 306ad199-d150-4f6c-bcf1-24a7948b93be
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a55a6d40d6d39b368c31a2716c14d05e0e49a78c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3399"></a>Compilerfehler C3399
'Typ': Beim Erstellen einer Instanz eines generischen Parameters können Argumente nicht bereitgestellt werden.  
  
 Wenn Sie die `gcnew()` -Einschränkung angeben, geben Sie auch an, dass der Einschränkungstyp über einen parameterlosen Konstruktor verfügt. Aus diesem Grund tritt bei dem Versuch ein Fehler auf, diesen Typ zu instanziieren und einen Parameter zu übergeben.  
  
 Finden Sie unter [Einschränkungen für generische Typparameter (C + c++ / CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md) für Weitere Informationen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3399 generiert:  
  
```  
// C3399.cpp  
// compile with: /clr /c  
generic <class T>   
where T : gcnew()  
void f() {  
   T t = gcnew T(1);   // C3399  
   T t2 = gcnew T();   // OK  
}  
```