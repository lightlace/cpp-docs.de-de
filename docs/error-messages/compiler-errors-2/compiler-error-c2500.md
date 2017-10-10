---
title: Compilerfehler C2500 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2500
dev_langs:
- C++
helpviewer_keywords:
- C2500
ms.assetid: 6bff8161-dc9a-48ca-91f1-fd2eefdbbc93
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 2b869ca0ba959e9b774a005298ef4456d0995156
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

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
