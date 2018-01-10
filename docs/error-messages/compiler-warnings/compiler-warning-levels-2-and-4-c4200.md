---
title: Compilerwarnung (Stufen 2 und 4) C4200 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4200
dev_langs: C++
helpviewer_keywords: C4200
ms.assetid: e44d6073-937f-42b7-acc1-65e802b475c6
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f160476deb2ab3e4ad0ff00100305c934dfb14c3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-levels-2-and-4-c4200"></a>Compilerwarnung (Stufen 2 und 4) C4200
nicht dem Standard entsprechende Erweiterung: Null-Array in Struktur/Union  
  
 Gibt an, dass eine Struktur oder Union ein Array mit Größe Null enthält.  
  
 Die Deklaration eines Arrays der Größe 0 (null) ist eine Microsoft-Erweiterung. Dadurch wird eine Warnung der Stufe 2 bei der Kompilierung einer C++-Datei und eine Warnung der Stufe 4 kompiliert, wenn C-Datei kompiliert wird. C++-Kompilierung ermöglicht auch diese Warnung: "Kann nicht generiert-Kopierkonstruktor oder kopierzuweisung Operator, wenn UDT ein Array der Größe 0 (null) enthält." In diesem Beispiel wird die Warnung C4200 generiert:  
  
```cpp  
// C4200.cpp  
// compile by using: cl /W4 c4200.cpp  
struct A {  
    int a[0];  // C4200  
};  
int main() {  
}  
```  
  
 Diese nicht standardisierte Erweiterung wird häufig zum Verknüpfen von Code mit externen Datenstrukturen verwendet, die eine variable Länge haben. Wenn dieses Szenario für Ihren Code gilt, können Sie die Warnung deaktivieren:  
  
## <a name="example"></a>Beispiel  
  
```cpp  
// C4200b.cpp  
// compile by using: cl /W4 c4200a.cpp  
#pragma warning(disable : 4200)  
struct A {  
    int a[0];  
};  
int main() {  
}  
```