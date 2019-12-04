---
title: Compilerfehler C3201
ms.date: 11/04/2016
f1_keywords:
- C3201
helpviewer_keywords:
- C3201
ms.assetid: ec19cd64-1789-40a3-b2db-dff2852b9d98
ms.openlocfilehash: 4da6616c59ea4b8a720c8e2dc9742e37a9939171
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738764"
---
# <a name="compiler-error-c3201"></a>Compilerfehler C3201

Die Vorlagenparameterliste für die Klassenvorlage "template" stimmt nicht mit der Vorlagenparameterliste für den Vorlagenparameter "template" überein.

Sie haben eine Klassenvorlage im Argument an eine Klassenvorlage übergeben, die keinen Vorlagenparameter verwendet, oder Sie haben eine nicht übereinstimmende Anzahl Vorlagenargumente für das Standardvorlagenargument übergeben.

```cpp
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
