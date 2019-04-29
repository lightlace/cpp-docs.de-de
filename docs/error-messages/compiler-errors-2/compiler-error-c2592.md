---
title: Compilerfehler C2592
ms.date: 11/04/2016
f1_keywords:
- C2592
helpviewer_keywords:
- C2592
ms.assetid: 833a4d7b-66ef-4d4c-ae83-a533c2b0eb07
ms.openlocfilehash: 2ea5919f073f2fd608dca332e721be0669760a0a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387018"
---
# <a name="compiler-error-c2592"></a>Compilerfehler C2592

„Klasse“: „base_class_2“ wird von „base_class_1“ geerbt und kann nicht erneut angegeben werden.

Sie können nur Basisklassen angeben, die nicht von anderen Basisklassen erben. In diesem Fall ist nur `base_class_1` in der Spezifikation von `class` erforderlich, da `base_class_1` bereits `base_class_2` erbt.