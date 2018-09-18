---
title: Compilerfehler C3166 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3166
dev_langs:
- C++
helpviewer_keywords:
- C3166
ms.assetid: ec3e330d-c15d-4158-8268-09101486c566
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c568f1732a4be5d890a5a654b09638828385383
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035512"
---
# <a name="compiler-error-c3166"></a>Compilerfehler C3166

"Zeiger": Deklarieren Sie einen Zeiger auf einen internen __gc-Zeiger kann nicht als Member von 'Typ'

Der Compiler hat eine ungültige Zeigerdeklaration gefunden (eine `__nogc` Zeiger auf eine `__gc` Zeiger.).

C3166 ist nur über die veraltete Compileroption erreichbar **oldSyntax**.
