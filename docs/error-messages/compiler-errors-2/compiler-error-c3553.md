---
title: Compilerfehler C3553 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3553
dev_langs: C++
helpviewer_keywords: C3553
ms.assetid: 7f84bf37-6419-4ad3-ab30-64266100b930
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9ad1e4d6f59d0cad99935eda97b8a7d7ac358666
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3553"></a>Compilerfehler C3553
"decltype" erwartet einen Ausdruck und keinen Typ.  
  
 Das `decltype()` -Schlüsselwort benötigt einen Ausdruck als Argument, nicht den Namen eines Typs. Im folgenden Codefragment wird beispielsweise durch die letzte Anweisung der Fehler C3553 verursacht.  
  
 `int x = 0;`  
  
 `decltype(x+1);`  
  
 `decltype(int); // C3553`