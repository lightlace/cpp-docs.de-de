---
title: Compilerfehler C3208 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3208
dev_langs:
- C++
helpviewer_keywords:
- C3208
ms.assetid: 6d060bfe-52cf-4599-8f70-bdeb5a670df3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fead75aa4eb245bb6be924ae5f04e1ce28cd8206
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3208"></a>Compilerfehler C3208
"Funktion": Die Vorlagenparameterliste für die Klassenvorlage "Klasse" stimmt nicht mit der Vorlagenparameterliste für den Vorlagenparameter "Parameter" überein  
  
 Ein Vorlagenparameter hat nicht die gleiche Anzahl von Vorlagenparametern wie die angegebene Klassenvorlage.  
  
 Im folgenden Beispiel wird C3208 generiert:  
  
```  
// C3208.cpp  
template <template <class T> class TT >  
int f();  
  
template <class T1, class T2>  
struct S;  
  
template <class T1>  
struct R;  
  
int i = f<S>();   // C3208  
// try the following line instead  
// int i = f<R>();  
```