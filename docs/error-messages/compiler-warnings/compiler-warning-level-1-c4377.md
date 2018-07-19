---
title: Compilerwarnung (Stufe 1) C4377 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4377
dev_langs:
- C++
helpviewer_keywords:
- C4377
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ef049f85cd17bfeaba243b84da9fca93ae4036b0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33274780"
---
# <a name="compiler-warning-level-1-c4377"></a>Compilerwarnung (Stufe 1) C4377
systemeigene Typen sind standardmäßig privat. -d1PrivateNativeTypes ist veraltet.  
  
 In früheren Versionen waren systemeigene Typen in Assemblys standardmäßig und einer internen, nicht dokumentierten Compileroption öffentliche (**/d1PrivateNativeTypes**) wurde verwendet, um sie als privat kennzeichnen.  
  
 Alle Typen, systemeigen und CLR, sind nun in einer Assembly standardmäßig privat damit **/d1PrivateNativeTypes** wird nicht mehr benötigt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C4377 generiert.  
  
```  
// C4377.cpp  
// compile with: /clr /d1PrivateNativeTypes /W1  
// C4377 warning expected  
int main() {}  
```