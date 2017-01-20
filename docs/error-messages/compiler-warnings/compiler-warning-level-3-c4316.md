---
title: "Compilerwarnung (Stufe 3) C4316"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4316"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4316"
ms.assetid: 10371f01-aeb8-40ac-a290-59e63efa5ad4
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 3) C4316
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Das Objekt, das auf dem Heap zugewiesen wird, ist für diesen Typ möglicherweise nicht ausgerichtet.  
  
 Ein über\-ausgerichtetes Objekt, das mithilfe von `operator new` zugeordnet wird, hat möglicherweise nicht die angegebene Ausrichtung.  Überschreiben Sie [new\-Operator](../../c-runtime-library/operator-new-crt.md) und [delete\-Operator](../../c-runtime-library/operator-delete-crt.md) für über\-ausgerichtete Typen, sodass diese die ausgerichteten Speicherbelegungsroutinen verwenden – z. B. [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md) und [\_aligned\_free](../../c-runtime-library/reference/aligned-free.md).  Im folgenden Beispiel wird C4316 generiert:  
  
```cpp  
// C4316.cpp  
// Test: cl /W3 /c C4316.cpp  
  
__declspec(align(32)) struct S {}; // C4324  
  
int main() {  
    new S; // C4316  
}  
```