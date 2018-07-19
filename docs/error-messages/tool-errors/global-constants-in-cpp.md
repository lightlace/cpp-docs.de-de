---
title: Globale Konstanten in C++ | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- global constants
- constants, global
ms.assetid: df5a9bd4-d0a8-4c1c-956e-b481d0bded7d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1f1ee5fdf3d50f30e02bd48fe3664c10d26a8449
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33297335"
---
# <a name="global-constants-in-c"></a>Globale Konstanten in C++
Globale Konstanten in C++ haben statische Verknüpfung. Dies ist anders als C. Wenn Sie versuchen, einen globalen erhalten Konstante in C++ in mehreren Dateien Sie nicht aufgelösten externe Fehler. Der Compiler globale Konstanten werden optimiert, sodass kein Platz für die Variable reserviert.  
  
 Eine Möglichkeit zum Beheben dieses Fehlers besteht darin die const Initialisierungen enthalten, in einer Headerdatei einfügen und diesen Header in die CPP-Dateien bei Bedarf, als ob es sich um Funktionsprototyp wurde. Eine andere Möglichkeit besteht darin, Sie deklarieren die Variable als nicht konstant und verwenden einen konstanten Verweis, wenn Sie darauf zugreifen.  
  
 Im folgende Beispiel wird C2019 generiert:  
  
```  
// global_constants.cpp  
// LNK2019 expected  
void test(void);  
const int lnktest1 = 0;  
  
int main() {  
   test();  
}  
```  
  
 und anschließend  
  
```  
// global_constants_2.cpp  
// compile with: global_constants.cpp  
extern int lnktest1;  
  
void test() {  
  int i = lnktest1;   // LNK2019  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Linkertoolfehler LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)