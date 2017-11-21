---
title: Compilerfehler C2562 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2562
dev_langs: C++
helpviewer_keywords: C2562
ms.assetid: 2c41e511-9952-4b98-9976-6b1523613e1b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bcd98e241abd5cfd8cfce16224069470493d89b5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2562"></a>Compilerfehler C2562
'Bezeichner': 'void'-Funktion einen Wert zurückgeben  
  
 Die Funktion wird deklariert als `void` aber einen Wert zurückgibt.  
  
 Dieser Fehler kann durch einen falschen Funktionsprototyp verursacht werden.  
  
 Dieser Fehler möglicherweise behoben werden, wenn Sie den Rückgabetyp in der Funktionsdeklaration angeben.  
  
 Im folgende Beispiel wird C2562 generiert:  
  
```  
// C2562.cpp  
// compile with: /c  
void testfunc() {  
   int i;  
   return i;   // C2562 delete the return to resolve  
}  
```