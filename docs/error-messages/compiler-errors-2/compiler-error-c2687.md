---
title: Compiler-Fehler C2687 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2687
dev_langs: C++
helpviewer_keywords: C2687
ms.assetid: 1d24b24a-cd0f-41cc-975c-b08dcfb7f402
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6e74167bcc9637d2d9f0c39d0d3d36f960db5efa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2687"></a>Compiler-Fehler C2687 generiert
'Typ': Exception-Deklaration kann nicht "void" sein oder einen unvollständigen Typ oder Zeiger oder Verweis auf einen unvollständigen Typ zu kennzeichnen  
  
 Für einen Typ einer Ausnahmedeklaration angehören muss er definiert ist und nicht "void" sein.  
  
 Im folgende Beispiel wird C2687 generiert:  
  
```  
// C2687.cpp  
class C;  
  
int main() {  
   try {}  
   catch (C) {}   // C2687 error  
}  
```  
  
 Mögliche Lösung:  
  
```  
// C2687b.cpp  
// compile with: /EHsc  
class C {};  
  
int main() {  
   try {}  
   catch (C) {}  
}  
```