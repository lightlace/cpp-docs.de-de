---
title: Compilerfehler Fehler C2086 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2086
dev_langs:
- C++
helpviewer_keywords:
- C2086
ms.assetid: 4329bf72-90c8-444c-8524-4ef75e6b2139
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 04f1a21c06adeeda5d9db428e984da51f06addb5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2086"></a>Compilerfehler Fehler C2086
'Bezeichner': Neudefinition  
  
 Der Bezeichner mehrfach definiert ist, oder eine nachfolgende Deklaration unterscheidet sich von einer vorherigen.  
  
 C2086 kann auch das Ergebnis der inkrementellen Buildvorgangs für eine C#-Assembly sein. Erstellen Sie zum Beheben dieses Fehlers die C#-Assembly neu.  
  
 Im folgenden Beispiel wird C2086 generiert:  
  
```  
// C2086.cpp  
main() {  
  int a;  
  int a;   // C2086 not an error in ANSI C  
}  
```