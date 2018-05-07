---
title: Compilerwarnung (Stufe 4) C4207 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4207
dev_langs:
- C++
helpviewer_keywords:
- C4207
ms.assetid: f4e09e3e-ac87-4489-8e3f-c8f76b82e721
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1e5ed69cfcbaa71a6bb0093944aab7de2f516cc3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4207"></a>Compilerwarnung (Stufe 4) C4207
nicht dem Standard entsprechende Erweiterung: Erweiterte Form der Initialisierung  
  
 Mit Microsoft-Erweiterungen (/ Ze), können Sie ein Array ohne Größenangabe von initialisieren `char` mithilfe einer Zeichenfolge in der geschweiften Klammern.  
  
## <a name="example"></a>Beispiel  
  
```  
// C4207.c  
// compile with: /W4  
char c[] = { 'a', 'b', "cdefg" }; // C4207  
  
int main()  
{  
}  
```  
  
 Solche Initialisierungen sind ungültig, ANSI-Kompatibilität (["/ Za"](../../build/reference/za-ze-disable-language-extensions.md)).