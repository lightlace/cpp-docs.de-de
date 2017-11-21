---
title: Compilerfehler C2197 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2197
dev_langs: C++
helpviewer_keywords: C2197
ms.assetid: 6dd5a6ec-bc80-41b9-a4ac-46f80eaca42d
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3b2f3482a8f66098d42389234924fee9238b7ed0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2197"></a>Compilerfehler C2197
"Funktion": Zu viele Argumente für Aufruf  
  
 Der Compiler hat zu viele Parameter für einen Aufruf der Funktion oder eine falsche Funktionsdeklaration gefunden.  
  
 Im folgenden Beispiel wird C2197 generiert:  
  
```  
// C2197.c  
// compile with: /Za /c  
void func( int );  
int main() {  
   func( 1, 2 );   // C2197 two actual parameters  
   func( 2 );   // OK  
}  
```