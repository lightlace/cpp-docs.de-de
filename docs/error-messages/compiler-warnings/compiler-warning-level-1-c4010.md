---
title: Compilerwarnung (Stufe 1) C4010 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4010
dev_langs:
- C++
helpviewer_keywords:
- C4010
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 06ab6307a34887fe2d8a8719e20c31da9728664b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33274653"
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