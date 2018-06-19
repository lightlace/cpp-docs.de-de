---
title: Compilerwarnung (Stufe 1) C4142 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4142
dev_langs:
- C++
helpviewer_keywords:
- C4142
ms.assetid: 1fdfc3dc-60a2-4f00-b133-20e400f9b7a6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c87b7689cf11ab28c1a6377ff85e1594fd1b5fc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33284432"
---
# <a name="compiler-warning-level-1-c4142"></a>Compilerwarnung (Stufe 1) C4142 generiert
keine Auswirkungen Neudefinition des Typs  
  
 Ein Typ ist neu in einer Weise definiert, die hat keine Auswirkung auf den generierten Code.  
  
 Dieser Fehler kann eine der folgenden Ursachen haben:  
  
-   Eine Memberfunktion einer abgeleiteten Klasse verfügt über einen anderen Rückgabetyp als die entsprechenden Member-Funktion der Basisklasse.  
  
-   Ein Typ definiert, mit der `typedef` Befehl erneut mit einer anderen Syntax definiert.  
  
 Im folgende Beispiel wird C4142 generiert:  
  
```  
// C4142.c  
// compile with: /W1  
float X2;  
X2 = 2.0 + 1.0;   // C4142  
  
int main() {  
   float X2;  
   X2 = 2.0 + 1.0;   // OK  
}  
```