---
title: Compilerwarnung (Stufe 4) C4201 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4201
dev_langs: C++
helpviewer_keywords: C4201
ms.assetid: 6156f508-9393-4d77-9e73-1ec3e1c32d0d
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5bbc3e5ea23ca9b9e57bb8473b8fb9f9f5ea2196
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4201"></a>Compilerwarnung (Stufe 4) C4201
nicht dem Standard entsprechende Erweiterung: namenlosen Struktur/Union  
  
 Bei Verwendung der Microsoft-Erweiterungen (/ Ze) können Sie eine Struktur ohne Deklaration als Mitglieder einer anderen Struktur oder Union angeben. Diese Strukturen generiert einen Fehler unter ANSI-Kompatibilität (["/ Za"](../../build/reference/za-ze-disable-language-extensions.md)).  
  
## <a name="example"></a>Beispiel  
  
```  
// C4201.cpp  
// compile with: /W4  
struct S  
{  
   float y;  
   struct  
   {  
      int a, b, c;  // C4201  
   };  
} *p_s;  
  
int main()  
{  
}  
```