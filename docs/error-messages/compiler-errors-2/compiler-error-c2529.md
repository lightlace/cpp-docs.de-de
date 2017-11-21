---
title: Compilerfehler C2529 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2529
dev_langs: C++
helpviewer_keywords: C2529
ms.assetid: 73a99e55-b91e-488d-9b72-cc80faaeb436
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7c0a693af458818b8c5ac44e160272d8b15fa5f5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2529"></a>Compilerfehler C2529
'Name': Verweis auf Verweis ist nicht zulässig  
  
 Dieser Fehler kann möglicherweise behoben werden, indem mithilfe der Zeigersyntax und das Deklarieren eines Verweises auf einen Zeiger.  
  
 Im folgende Beispiel wird C2529 generiert:  
  
```  
// C2529.cpp  
// compile with: /c  
int i;  
int &ri = i;  
int &(&rri) = ri;   // C2529  
```