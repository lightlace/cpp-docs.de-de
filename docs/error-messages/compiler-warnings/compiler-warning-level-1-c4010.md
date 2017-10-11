---
title: Compilerwarnung (Stufe 1) C4010 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4010
dev_langs:
- C++
helpviewer_keywords:
- C4010
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b6a0c84d5138cf2ae8a7a6279d9dc0fde9fe9512
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-level-1-c4010"></a>Compilerwarnung (Stufe 1) C4010 generiert
einzeiliger Kommentar enthält Zeilenfortsetzungszeichen  
  
 Ein einzeiliger Kommentar, indem eingeführt / / enthält einen umgekehrten Schrägstrich (\\), die als ein Zeilenfortsetzungszeichen dient. Der Compiler betrachtet die nächste Zeile als Fortsetzung und als Kommentar interpretiert.  
  
 Einige Syntax-geleitet, wobei Editoren keine die Zeile als Kommentar-Fortsetzungszeichen nach anzeigen. Syntaxfarben für alle Zeilen, die dazu führen, diese Warnung dass zu ignorieren.  
  
 Im folgende Beispiel wird C4010 generiert:  
  
```  
// C4010.cpp  
// compile with: /WX  
int main() {  
   // the next line is also a comment because of the backslash \  
   int a = 3; // C4010  
   a++;  
}  
```
