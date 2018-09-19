---
title: Compilerfehler C3201 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3201
dev_langs:
- C++
helpviewer_keywords:
- C3201
ms.assetid: ec19cd64-1789-40a3-b2db-dff2852b9d98
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 466899de89e1f8760ec78e7d346ef949fab667be
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074252"
---
# <a name="compiler-error-c3201"></a>Compilerfehler C3201

Die Vorlagenparameterliste für die Klassenvorlage "template" stimmt nicht mit der Vorlagenparameterliste für den Vorlagenparameter "template" überein.

Sie haben eine Klassenvorlage im Argument an eine Klassenvorlage übergeben, die keinen Vorlagenparameter verwendet, oder Sie haben eine nicht übereinstimmende Anzahl Vorlagenargumente für das Standardvorlagenargument übergeben.

```
// C3201.cpp
template<typename T1, typename T2>
class X1
{
};

template<template<typename T> class U = X1>   // C3201
class X2
{
};

template<template<typename T, typename V> class U = X1>   // OK
class X3
{
};
```