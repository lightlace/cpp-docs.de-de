---
title: Compilerfehler Fehler C3166 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3166
dev_langs:
- C++
helpviewer_keywords:
- C3166
ms.assetid: ec3e330d-c15d-4158-8268-09101486c566
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: aa933235f14f2ab6f11c86e6cbd3e23dc15481ec
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3166"></a>Compilerfehler Fehler C3166
"Zeiger": einen Zeiger auf einen internen __gc-Zeiger als Member von "Type" kann nicht deklariert werden  
  
Der Compiler hat eine ungültige Zeigerdeklaration gefunden (ein `__nogc` Zeiger auf eine `__gc` Zeiger.). 
  
C3166 ist nur über die veraltete Compileroption erreichbar **/CLR: oldSyntax**.  
