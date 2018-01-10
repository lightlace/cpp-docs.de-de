---
title: Compilerwarnung (Stufe 1) C4667 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4667
dev_langs: C++
helpviewer_keywords: C4667
ms.assetid: 5d2b7fe0-4f0e-4cd6-b432-ca02c3d194ab
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d66b4e92eebecc746391add492222fd1779bf6ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4667"></a>Compilerwarnung (Stufe 1) C4667
'Funktion': keine Funktionsvorlage definiert, die entspricht erforderlichen Instanziierung  
  
 Eine Funktionsvorlage, die nicht deklariert wurde, kann nicht instanziiert werden.  
  
 Im folgende Beispiel wird C4667 verursacht:  
  
```  
// C4667a.cpp  
// compile with: /LD /W1  
template  
void max(const int &, const int &); // C4667 expected  
```  
  
 Um diese Warnung zu vermeiden, müssen Sie zuerst deklarieren Sie die Funktionsvorlage:  
  
```  
// C4667b.cpp  
// compile with: /LD  
// Declare the function template  
template<typename T>  
const T &max(const T &a, const T &b) {  
   return (a > b) ? a : b;  
}  
// Then forcibly instantiate it with a desired type ... i.e. 'int'  
//  
template  
const int &max(const int &, const int &);  
```