---
title: Compilerfehler Fehler C2601 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2601
dev_langs: C++
helpviewer_keywords: C2601
ms.assetid: 88275582-5f37-45d7-807d-05f06ba00965
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cdffa40b751232525920d1d92affd9e3778d2f61
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2601"></a>Compilerfehler Fehler C2601
"Function": Lokale Funktionsdefinitionen sind nicht zulässig  
  
 Code versucht, eine Funktion innerhalb einer Funktion definieren.  
  
 Oder es gibt möglicherweise eine zusätzliche geschweifte Klammer in Ihrem Quellcode vor dem Auftreten des Fehlers C2601.  
  
 Im folgenden Beispiel wird C2601 generiert:  
  
```  
// C2601.cpp  
int main() {  
   int i = 0;  
  
   void funcname(int j) {   // C2601  
      j++;  
   }  
}  
```