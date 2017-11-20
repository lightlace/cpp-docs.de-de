---
title: Compilerwarnung (Stufe 1) C4142 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4142
dev_langs: C++
helpviewer_keywords: C4142
ms.assetid: 1fdfc3dc-60a2-4f00-b133-20e400f9b7a6
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7426b1ff7b22382617e2ab6cec4e54456a117aec
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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