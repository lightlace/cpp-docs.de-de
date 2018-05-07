---
title: Compilerwarnung (Stufen 2 und 4) C4200 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4200
dev_langs:
- C++
helpviewer_keywords:
- C4200
ms.assetid: e44d6073-937f-42b7-acc1-65e802b475c6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6ffc789c3c4da5caf50f0657e17ddabe40a5773c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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