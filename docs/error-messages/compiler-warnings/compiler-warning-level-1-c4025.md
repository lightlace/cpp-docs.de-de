---
title: Compilerwarnung (Stufe 1) C4025
ms.date: 11/04/2016
f1_keywords:
- C4025
helpviewer_keywords:
- C4025
ms.assetid: c4f6a651-0641-4446-973e-8290065e49ad
ms.openlocfilehash: 50e5ad586a754723cbb66685a14de2e23f0bdb7c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62151772"
---
# <a name="compiler-warning-level-1-c4025"></a>Compilerwarnung (Stufe 1) C4025

"Anzahl": Zeiger auf ein separates Segment an Funktion mit variablen Argumenten übergeben: Parameteranzahl

Die Übergabe eines basierten Zeigers an eine Funktion mit variablen Argumenten bewirkt, dass der Zeiger normalisiert wird. Dies kann unvorhersehbare Folgen haben. Übergeben Sie keine basierten Zeiger an Funktionen mit variablen Argumenten.