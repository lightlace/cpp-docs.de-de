---
title: Compilerfehler C2243 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2243
dev_langs:
- C++
helpviewer_keywords:
- C2243
ms.assetid: b90065bb-d251-4ba9-8b4c-280ee13fa9c0
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d9725239c7e7b8899c23584aa56d26ed77bd757a
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2243"></a>Compilerfehler C2243
'Konvertierungstyp'-Konvertierung von 'Typ1' zu 'Typ2' ist vorhaden, jedoch kann darauf nicht zugegriffen werden  
  
 Zugriffsschutz (`protected` oder `private`) hat die Konvertierung von einem Zeiger in eine abgeleitete Klasse eines Zeiger in eine Basisklasse verhindert.  
  
 Das folgende Beispiel generiert C2243:  
  
```  
// C2243.cpp  
// compile with: /c  
class B {};  
class D : private B {};  
class E : public B {};  
  
D d;  
B *p = &d;   // C2243  
  
E e;  
B *p2 = &e;  
```  
  
 Basisklassen mit `protected`- oder `private`-Zugriff sind auf Clients der abgeleiteten Klasse nicht zugänglich. Diese Ebenen der Zugriffssteuerung werden verwendet, um anzugeben, dass die Basisklasse ein Implementierungsdetail ist, das für Clients nicht sichtbar sein sollte. Verwenden Sie die öffentliche Ableitung, wenn Sie möchten, dass Clients der abgeleiteten Klasse Zugriff auf die implizite Konvertierung eines abgeleiteten Klassenzeigers auf einen Zeiger auf die Basisklasse haben sollen.
