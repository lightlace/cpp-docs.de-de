---
title: Compilerwarnung (Stufe 1) C4183 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4183
dev_langs:
- C++
helpviewer_keywords:
- C4183
ms.assetid: dc48312c-4b34-44dd-80ff-eb5f11d5ca47
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2a271c12facaacdd07b4a664396c36c7301ac2f4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33277471"
---
# <a name="compiler-warning-level-1-c4183"></a>Compilerwarnung (Stufe 1) C4183 generiert
'Bezeichner': Rückgabetyp fehlt; Angenommen, dass eine Memberfunktion, die Rückgabe von "Int" sein  
  
 Die Inlinedefinition einer Memberfunktion in einer Klasse oder Struktur keinen Rückgabetyp. Diese Memberfunktion steht für ein Standardwert, der Rückgabetyp ist `int`.  
  
 Im folgende Beispiel wird C4183 generiert:  
  
```  
// C4183.cpp  
// compile with: /W1 /c  
#pragma warning(disable : 4430)  
class MyClass1;  
class MyClass2 {  
   MyClass1() {};   // C4183  
};  
```