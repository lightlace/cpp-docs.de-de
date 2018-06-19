---
title: Compiler-Fehler C2736 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2736
dev_langs:
- C++
helpviewer_keywords:
- C2736
ms.assetid: 95a6bc28-c0cb-49dc-87e6-e993dbbba881
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e3a7ad6d4259a5df0d85fd1f208df6d322430ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230676"
---
# <a name="compiler-error-c2736"></a>Compiler-Fehler C2736 generiert
' Schlüsselwort ' ist in Typumwandlung nicht zulässig.  
  
 Das Schlüsselwort ist in einer Typumwandlung ungültig.  
  
 Im folgende Beispiel wird C2736 generiert:  
  
```  
// C2736.cpp  
int main() {  
   return (virtual) 0;   // C2736  
   // try the following line instead  
   // return 0;  
}  
```