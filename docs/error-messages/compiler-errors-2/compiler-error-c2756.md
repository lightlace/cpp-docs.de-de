---
title: Compilerfehler Fehler C2756 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2756
dev_langs: C++
helpviewer_keywords: C2756
ms.assetid: 42eb988d-4043-4dee-8fd4-596949f69a55
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4ca6e01d1c4b2f7dda2a941eeef4599d62241fe3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2756"></a>Compiler-Fehler C2756 generiert
'template type': Bei einer teilweisen Spezialisierung sind Standardvorlagenargumente nicht zulässig  
  
 Die Vorlage für eine teilweise Spezialisierung darf kein Standardargument enthalten.  
  
 Im folgenden Beispiel wird C2756 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2756.cpp  
template <class T>  
struct S {};  
  
template <class T=int>  
// try the following line instead  
// template <class T>  
struct S<T*> {};   // C2756  
```