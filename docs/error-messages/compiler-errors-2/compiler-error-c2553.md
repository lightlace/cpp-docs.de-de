---
title: Compilerfehler C2553 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2553
dev_langs:
- C++
helpviewer_keywords:
- C2553
ms.assetid: 64bc1e9a-627f-4ce9-b7bc-dc911bdb9180
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8cfb09f2701b418ab5570641a78c465ff72ed943
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33232533"
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