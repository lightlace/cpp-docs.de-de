---
title: Compilerfehler C2356 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2356
dev_langs: C++
helpviewer_keywords: C2356
ms.assetid: 84d5a816-9a61-4d45-9978-38e485bbf767
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 99f29fb1e651c8182c8aa4dc037fc8cd6af6c6cc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2356"></a>Compilerfehler C2356
Initialisierungssegment muss während der Übersetzungseinheit nicht geändert.  
  
 Mögliche Ursachen:  
  
-   `#pragma init_seg`Segmentinitialisierungscode vorangestellt  
  
-   `#pragma init_seg`durch eine andere voranstehen`#pragma init_seg`  
  
 Um zu beheben, verschieben Sie Segmentinitialisierungscode an den Anfang des Moduls. Verschieben Sie mehrere Bereiche initialisiert werden müssen, sie um Module zu trennen.  
  
 Im folgende Beispiel wird C2356 generiert:  
  
```  
// C2356.cpp  
#pragma warning(disable : 4075)  
  
int __cdecl myexit(void (__cdecl *)());  
int __cdecl myexit2(void (__cdecl *)());  
  
#pragma init_seg(".mine$m",myexit)  
#pragma init_seg(".mine$m",myexit2)   // C2356  
```