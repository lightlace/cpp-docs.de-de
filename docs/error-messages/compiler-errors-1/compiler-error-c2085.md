---
title: Compilerfehler Fehler C2085 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2085
dev_langs:
- C++
helpviewer_keywords:
- C2085
ms.assetid: 0a86785c-8e6f-481b-8c7b-412220c1950d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c0fe489dbdd0934926a056bbc7e5539f40ca1ba8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33169841"
---
# <a name="compiler-error-c2085"></a>Compilerfehler Fehler C2085
'Bezeichner': nicht in der Liste formaler Parameter  
  
 Der Bezeichner wurde in einer Funktionsdefinition, aber nicht in der Liste formaler Parameter deklariert. (Nur ANSI-C)  
  
 Im folgende Beispiel wird C2085 generiert:  
  
```  
// C2085.c  
void func1( void )  
int main( void ) {}   // C2085  
```  
  
 Mögliche Lösung:  
  
```  
// C2085b.c  
void func1( void );  
int main( void ) {}  
```  
  
 Das Semikolon fehlt, `func1()` einer Funktionsdefinition, nicht um einen Prototyp, deshalb sieht `main` ist definiert in `func1()`, generieren Fehler C2085 für Bezeichner `main`.