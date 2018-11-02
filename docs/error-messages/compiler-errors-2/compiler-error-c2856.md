---
title: Compilerfehler C2856
ms.date: 11/04/2016
f1_keywords:
- C2856
helpviewer_keywords:
- C2856
ms.assetid: fe616c51-124e-49e3-9dd8-883ec1660680
ms.openlocfilehash: 1e515f250c8ab9d1008ded91b99176f1d86d7cd1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499605"
---
# <a name="compiler-error-c2856"></a>Compilerfehler C2856

\#Pragma-Hdrstop kann nicht innerhalb eines #if-Block befinden.

Die `hdrstop` Pragma kann nicht innerhalb des Texts eines Blocks für die bedingte Kompilierung nicht platziert werden.

Verschieben der `#pragma hdrstop` Anweisung, um einen Bereich, der nicht in enthalten ist ein `#if/#endif` Block.