---
title: Compilerfehler C3399 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3399
dev_langs:
- C++
helpviewer_keywords:
- C3399
ms.assetid: 306ad199-d150-4f6c-bcf1-24a7948b93be
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: abcf9e59df1562bd5b6b430c2c63554e87340abb
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

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
