---
title: Compilerfehler C2514 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2514
dev_langs:
- C++
helpviewer_keywords:
- C2514
ms.assetid: 4b7085e5-6714-4261-80b7-bc72e64ab3e8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 255459a7ba9829b3db817662e2fc1139191b6385
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33227974"
---
# <a name="compiler-error-c2514"></a>Compilerfehler C2514
'Klasse': Klasse besitzt keine Konstruktoren  
  
 Die Klasse, Struktur oder Union verfügt über keinen Konstruktor mit einer Parameterliste, die den Parametern, die verwendet wird, um sie zu instanziieren übereinstimmt.  
  
 Eine Klasse muss vollständig deklariert werden, bevor es instanziiert werden kann.  
  
 Im folgende Beispiel wird C2514 generiert:  
  
```  
// C2514.cpp  
// compile with: /c  
class f;  
  
class g {  
public:  
    g (int x);  
};  
  
class fmaker {  
   f *func1() {  
      return new f(2);   // C2514  
   }  
  
   g *func2() {  
      return new g(2);   // OK  
   }  
};   
```