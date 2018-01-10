---
title: Compilerfehler C2243 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2243
dev_langs: C++
helpviewer_keywords: C2243
ms.assetid: b90065bb-d251-4ba9-8b4c-280ee13fa9c0
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8ae7349cce7e824af5621fba121e762aeccffa9e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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