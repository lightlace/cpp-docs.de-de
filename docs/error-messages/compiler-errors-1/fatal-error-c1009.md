---
title: Schwerwiegender Fehler C1009 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1009
dev_langs:
- C++
helpviewer_keywords:
- C1009
ms.assetid: dcc8383c-3362-4c47-9c26-25d2451ebd53
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b1fbd8994be6fd86a764db400d8761a5d697079b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037332"
---
# <a name="fatal-error-c1009"></a>Schwerwiegender Fehler C1009

Compilerlimit: zu tiefe Schachtelung von Makros

Der Compiler hat versucht, zu viele Makros zur gleichen Zeit zu erweitern. Der Compiler hat einen Grenzwert von 256 Ebenen der Schachtelung von Makros. Teilen Sie Schachtelung von Makros in einfachere Makros.