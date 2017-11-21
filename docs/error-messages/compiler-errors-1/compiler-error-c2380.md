---
title: Compilerfehler C2380 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2380
dev_langs: C++
helpviewer_keywords: C2380
ms.assetid: 717b1e6e-ddfe-4bac-a5f3-7f9a4dcb1572
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fdb96a1440fce617260c338e1b965b4a3fb9e791
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2380"></a>Compilerfehler C2380
Typ(en) vor 'Bezeichner' (Konstruktor mit dem Rückgabetyp oder ungültige Neudefinition des aktuellen Class-Name)?  
  
 Ein Konstruktor gibt einen Wert zurück oder Klassenname.  
  
 Im folgenden Beispiel wird C2326 generiert:  
  
```  
// C2380.cpp  
// compile with: /c  
class C {  
public:  
   int C();   // C2380, specifies an int return  
   int C;   // C2380, redefinition of i  
   C();   // OK  
};  
```