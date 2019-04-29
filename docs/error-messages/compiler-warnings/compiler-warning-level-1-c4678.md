---
title: Compilerwarnung (Stufe 1) C4678
ms.date: 11/04/2016
f1_keywords:
- C4678
helpviewer_keywords:
- C4678
ms.assetid: 0c588f34-595d-4e5c-9470-8723fca2cc06
ms.openlocfilehash: 9e61d919f08bbbf4f3e74da7ba4f2388516d3152
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374520"
---
# <a name="compiler-warning-level-1-c4678"></a>Compilerwarnung (Stufe 1) C4678

Basisklasse "base_type" hat eine stärkere Zugriffsbeschränkung als "derived_type"

Ein öffentlicher Typ wurde von einem privaten Typ abgeleitet. Wenn der öffentliche Typ in einer referenzierten Assembly instanziiert wird, sind die Member des privaten Basistyps nicht zugänglich.

C4678 ist nur über die veraltete Compileroption erreichbar **oldSyntax**. Es ist ein Fehler auf, wenn mit **"/ CLR"**, um eine Basisklasse verfügen, die weniger zugegriffen werden kann, der abgeleiteten Klasse.
