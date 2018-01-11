---
title: Compilerwarnung (Stufe 1) C4377 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4377
dev_langs: C++
helpviewer_keywords: C4377
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b2cf61aa35bcfc40a40febb9e066caba6decd682
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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