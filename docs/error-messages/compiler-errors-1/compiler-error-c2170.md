---
title: Compilerfehler C2170
ms.date: 11/04/2016
f1_keywords:
- C2170
helpviewer_keywords:
- C2170
ms.assetid: d5c663f0-2459-4e11-a8bf-a52b62f3c71d
ms.openlocfilehash: 04d41a50bc0d5e811e47e5f9d146362a543f26f9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174678"
---
# <a name="compiler-error-c2170"></a>Compilerfehler C2170

'Bezeichner': nicht als Funktion deklariert, kann nicht systemintern sein

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Pragma `intrinsic` wird für ein anderes Element als eine Funktion verwendet.

1. Pragma `intrinsic` für eine Funktion mit kein systeminterner Form verwendet wird.