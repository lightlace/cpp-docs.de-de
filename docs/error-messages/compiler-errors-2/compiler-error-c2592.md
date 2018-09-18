---
title: Compilerfehler C2592 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2592
dev_langs:
- C++
helpviewer_keywords:
- C2592
ms.assetid: 833a4d7b-66ef-4d4c-ae83-a533c2b0eb07
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3f2377f48eb8102771705f2dedc67a7a15f6fa95
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030984"
---
# <a name="compiler-error-c2592"></a>Compilerfehler C2592

„Klasse“: „base_class_2“ wird von „base_class_1“ geerbt und kann nicht erneut angegeben werden.

Sie können nur Basisklassen angeben, die nicht von anderen Basisklassen erben. In diesem Fall ist nur `base_class_1` in der Spezifikation von `class` erforderlich, da `base_class_1` bereits `base_class_2` erbt.