---
title: Compilerfehler Fehler C2601 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2601
dev_langs:
- C++
helpviewer_keywords:
- C2601
ms.assetid: 88275582-5f37-45d7-807d-05f06ba00965
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 49598223c3f68271065cc6212da19767020c51e9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230824"
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