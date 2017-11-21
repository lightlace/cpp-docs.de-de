---
title: Compilerfehler C2936 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2936
dev_langs: C++
helpviewer_keywords: C2936
ms.assetid: 5d1ba0fc-0c78-4a37-a83b-1ef8527763be
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c7949f958a6656c5e29210fcc4533c5730d18e02
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2936"></a>Compilerfehler C2936
'Klasse': Die Typ-Klassen-ID wird als lokale Datenvariable neu definiert.  
  
 Eine generische oder Vorlagenklasse kann nicht als globale Datenvariable verwendet werden.  
  
 Dieser Fehler kann dadurch verursacht werden, dass geschweifte Klammern nicht korrekt übereinstimmen.  
  
 Im folgenden Beispiel wird C2936 generiert:  
  
```  
// C2936.cpp  
// compile with: /c  
template<class T> struct TC { };   
int TC<int>;   // C2936  
  
// OK  
struct TC2 { };   
int TC2;  
```  
  
 C2936 kann auch auftreten, wenn Generika verwendet werden:  
  
```  
// C2936b.cpp  
// compile with: /clr /c  
generic<class T>  
ref struct GC {};  
int GC<int>;   // C2936  
  
// OK  
ref struct GC2 {};  
int GC2;  
```