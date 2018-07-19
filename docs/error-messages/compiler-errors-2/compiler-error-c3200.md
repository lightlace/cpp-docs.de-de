---
title: Compilerfehler C3200 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3200
dev_langs:
- C++
helpviewer_keywords:
- C3200
ms.assetid: 44bb5e77-f0ec-421c-a732-b9ee7c0a3529
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6aa34ea006b06138290417387bd393589b630aa4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33251306"
---
# <a name="compiler-error-c3200"></a>Compilerfehler C3200
'Template': Ungültiges Vorlagenargument für den Vorlagenparameter 'Parameter'. Klassenvorlage erwartet  
  
 Sie haben ein ungültiges Argument an eine Klassenvorlage übergeben. Die Klassenvorlage erwartet Vorlage als Parameter an. Im folgenden Beispiel Aufrufen `Y<int, int> aY` C3200 generiert. Der erste Parameter muss eine Vorlage sein, z. B. `Y<X, int> aY`.  
  
```  
// C3200.cpp  
template<typename T>  
class X  
{  
};  
  
template<template<typename U> class T1, typename T2>  
class Y  
{  
};  
  
int main()  
{  
   Y<int, int> y;   // C3200  
}  
```