---
title: Compilerfehler C3370 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3370
dev_langs:
- C++
helpviewer_keywords:
- C3370
ms.assetid: ee6d4c85-78fc-42b2-836e-5cc491a3b2ba
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 0085ecc5811be49bf36ecf70b38bed11c3ef3f0b
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3370"></a>Compilerfehler C3370
'IDL_Modulname': 'idl_module' ist noch nicht definiert.  
  
 Vor der Verwendung [Idl_module](../../windows/idl-module.md) um einen Einstiegspunkt in eine DLL-Datei angeben, müssen Sie zunächst mithilfe `idl_module` den DLL-Namen angeben.  
  
 Im folgenden Beispiel wird C3370 generiert:  
  
```  
// C3370.cpp  
[module(name=MyLibrary)];  
// uncomment the following line to resolve the error  
// [idl_module(name="name1", dllname=x.dll)];  
[idl_module(name="name1"), entry(100)] // C3370  
int f1();  
  
int main()  
{  
}  
```
