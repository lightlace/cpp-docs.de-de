---
title: Compilerwarnung (Stufe 1) C4678 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4678
dev_langs:
- C++
helpviewer_keywords:
- C4678
ms.assetid: 0c588f34-595d-4e5c-9470-8723fca2cc06
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 81eb7df618f97300c2654cc0f4f7a58d18215b26
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46076098"
---
# <a name="compiler-warning-level-1-c4678"></a>Compilerwarnung (Stufe 1) C4678

Basisklasse "base_type" hat eine stärkere Zugriffsbeschränkung als "derived_type"

Ein öffentlicher Typ wurde von einem privaten Typ abgeleitet. Wenn der öffentliche Typ in einer referenzierten Assembly instanziiert wird, sind die Member des privaten Basistyps nicht zugänglich.

C4678 ist nur über die veraltete Compileroption erreichbar **oldSyntax**. Es ist ein Fehler auf, wenn mit **"/ CLR"**, um eine Basisklasse verfügen, die weniger zugegriffen werden kann, der abgeleiteten Klasse.
