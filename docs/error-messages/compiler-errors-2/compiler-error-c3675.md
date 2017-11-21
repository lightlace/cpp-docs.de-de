---
title: Compilerfehler C3675 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3675
dev_langs: C++
helpviewer_keywords: C3675
ms.assetid: 87461613-6633-430b-b95d-c7cb1bb63776
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d45236fc32fd0d10e9617b6946683d8ebd73ef0e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3675"></a>Compilerfehler C3675
'Funktion': ist reserviert, da 'Eigenschaft' definiert ist  
  
 Wenn Sie eine einfache Eigenschaft deklarieren, generiert der Compiler die Get- und Set-Zugriffsmethoden und den Namen in den Bereich des Programms vorhanden sind.  Die vom Compiler generierte gebildet vorangestellt Get_ und Set_ des Eigenschaftennamens.  Aus diesem Grund können Sie Funktionen mit dem gleichen Namen wie die vom Compiler generierten Accessoren nicht deklarieren.  
  
 Weitere Informationen finden Sie unter [property](../../windows/property-cpp-component-extensions.md) .  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3675 generiert.  
  
```  
// C3675.cpp  
// compile with: /clr /c  
ref struct C {  
public:  
   property int Size;  
   int get_Size() { return 0; }   // C3675  
};  
```