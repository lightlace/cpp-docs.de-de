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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9a7be7320c21469536f6ddada99abd862812d882
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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