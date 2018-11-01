---
title: Schwerwiegender Fehler C1005
ms.date: 11/04/2016
f1_keywords:
- C1005
helpviewer_keywords:
- C1005
ms.assetid: 150daf8e-a38a-4669-9c1a-a05b5a1f65ef
ms.openlocfilehash: a84791367656729b1cbd50ca180368f6c01531a4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614460"
---
# <a name="fatal-error-c1005"></a>Schwerwiegender Fehler C1005

Zeichenfolge zu lang für Puffer

Eine Zeichenfolge in einer Zwischendatei des Compilers hat zu einem Pufferüberlauf geführt.

Sie erhalten diesen Fehler möglicherweise, wenn der an die Compileroptionen [/Fd](../../build/reference/fd-program-database-file-name.md) oder [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) übergebene Parameter größer als 256 Bytes ist.