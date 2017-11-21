---
title: Compiler-Fehler C2745 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2745
dev_langs: C++
helpviewer_keywords: C2745
ms.assetid: a1c45f13-7667-4678-aa16-265304a449a1
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d1eafe372c3acf8cc824e49066d2fd2c29fc0a88
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2745"></a>Compiler-Fehler C2745 generiert
"token": dieses Token kann nicht in einen Bezeichner konvertiert werden  
  
 Bezeichner müssen zulässiger Zeichen bestehen.  
  
 Im folgende Beispiel wird C2745 generiert:  
  
```  
// C2745.cpp  
// compile with: /clr  
int main() {  
   int __identifier([));   // C2745  
}  
```