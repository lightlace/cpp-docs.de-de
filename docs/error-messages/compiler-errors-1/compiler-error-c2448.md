---
title: Compilerfehler C2448 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2448
dev_langs: C++
helpviewer_keywords: C2448
ms.assetid: e255df3c-f861-4b4d-a193-8768cef061a5
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f289baff628ad2139940f023de36b7f936775b61
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2448"></a>Compilerfehler C2448
'Bezeichner': im Funktionsformat Initialisierer anscheinend einer Funktionsdefinition  
  
 Definition der Funktion ist falsch.  
  
 Dieser Fehler kann durch eine Programmiersprache C-Parameterliste im alten Stil verursacht werden.  
  
 Im folgende Beispiel wird C2448 generiert:  
  
```  
// C2448.cpp  
void func(c)  
   int c;  
{}   // C2448  
```