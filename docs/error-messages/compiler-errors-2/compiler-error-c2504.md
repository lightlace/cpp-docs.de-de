---
title: Compilerfehler C2504 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2504
dev_langs:
- C++
helpviewer_keywords:
- C2504
ms.assetid: c9e002a6-a4ee-4ba7-970e-edf4adb83692
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bac0f8f28955af172590535568289182c3489d6d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229515"
---
# <a name="compiler-error-c2504"></a>Compilerfehler C2504
'Klasse': Basisklasse undefiniert  
  
 Die Basisklasse deklariert, aber nie definiert.  Mögliche Ursachen:  
  
1.  Fehlende Includedatei.  
  
2.  Externe Basisklasse deklariert nicht mit ["extern"](../../cpp/using-extern-to-specify-linkage.md).  
  
 Im folgende Beispiel wird C2504 generiert:  
  
```  
// C2504.cpp  
// compile with: /c  
class A;  
class B : public A {};   // C2504  
```  
  
 OKAY  
  
```  
class C{};  
class D : public C {};  
```