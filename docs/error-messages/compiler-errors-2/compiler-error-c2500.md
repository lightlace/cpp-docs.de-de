---
title: Compilerfehler C2500 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2500
dev_langs:
- C++
helpviewer_keywords:
- C2500
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c05ffd59e415375dd3c7f94ae9bc377c0fc2b9e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229221"
---
# <a name="compiler-error-c2500"></a>Compilerfehler C2500
"Bezeichner1": "Bezeichner2" ist bereits eine direkte Basisklasse  
  
 Eine Klasse oder Struktur wird mehr als einmal in einer Liste von Basisklassen angezeigt.  
  
 Eine direkte Basisklasse ist in der Basisliste aufgeführt sind. Eine indirekte Basisklasse ist eine Basisklasse für eine der Klassen in der Basisliste.  
  
 Eine Klasse kann nicht als eine direkte Basisklasse mehr als einmal angegeben werden. Eine Klasse kann mehrmals als indirekte Basisklasse verwendet werden.  
  
 Im folgenden Beispiel wird C2500 generiert:  
  
```  
// C2500.cpp  
// compile with: /c  
class A {};  
class B : public A, public A {};    // C2500  
  
// OK  
class C : public A {};  
class D : public A {};  
class E : public C, public D {};  
```