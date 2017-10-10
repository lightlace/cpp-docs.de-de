---
title: Compilerfehler C2553 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2553
dev_langs:
- C++
helpviewer_keywords:
- C2553
ms.assetid: 64bc1e9a-627f-4ce9-b7bc-dc911bdb9180
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 623a09c54333ef62de7a7924cc4be02ff1b2c726
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2553"></a>Compilerfehler C2553
'Basisfunktion': Überschreiben der virtuellen Funktion zurückgeben Typ unterscheidet sich von 'Überschreibungsfunktion'  
  
 Eine Funktion in einer abgeleiteten Klasse versucht, eine virtuelle Funktion in einer Basisklasse zu überschreiben, aber die abgeleitete Klassenfunktion verfügte nicht über den gleichen Rückgabetyp als Funktion der Basisklasse.  Eine Außerkraftsetzung Funktionssignatur übereinstimmen die Signatur der Funktion, die überschrieben wird.  
  
 Im folgende Beispiel wird C2553 generiert:  
  
```  
// C2553.cpp  
// compile with: /clr /c  
ref struct C {  
   virtual void f();  
};  
  
ref struct D : C {  
   virtual int f() override ;   // C2553   
  
   // try the following line instead  
   // virtual void f() override;  
};  
```
