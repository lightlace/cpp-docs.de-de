---
title: Compilerfehler C2692 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2692
dev_langs:
- C++
helpviewer_keywords:
- C2692
ms.assetid: 02ade3b4-b757-448b-b065-d7d71bc3f441
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 03a9006889c5853e77b5603484ea9d18f2474241
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088370"
---
# <a name="compiler-error-c2692"></a>Compilerfehler C2692

"Funktionsname": vollständige Funktionen mit Prototyp erforderlich sind, im C-Compiler mit der "/ Clr" Option

Wenn Code Kompilieren für .NET verwaltet werden, erfordert der C-Compiler Funktionsdeklarationen ANSI. Darüber hinaus, wenn eine Funktion keine Parameter akzeptiert, sie müssen explizit deklarieren `void` als Parametertyp.