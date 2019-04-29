---
title: Compilerfehler C2212
ms.date: 11/04/2016
f1_keywords:
- C2212
helpviewer_keywords:
- C2212
ms.assetid: 3fdab304-272c-4d07-bfd4-fad75170e536
ms.openlocfilehash: a632aaf9809cd306354320a21cb03b993d60a95f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400421"
---
# <a name="compiler-error-c2212"></a>Compilerfehler C2212

"Bezeichner": __based ist nicht verfügbar für Zeiger auf Funktionen

Zeiger auf Funktionen können nicht deklariert werden `__based`. Wenn Sie Code basierende Daten benötigen, verwenden Sie die `__declspec` Schlüsselwort oder `data_seg` Pragma.