---
title: Schwerwiegender Fehler C1311 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1311
dev_langs:
- C++
helpviewer_keywords:
- C1311
ms.assetid: 6590a06c-ce9d-4f17-8f62-c809343143b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d93aa28d0cef3c07fd469349d485c4009fa4771d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091061"
---
# <a name="fatal-error-c1311"></a>Schwerwiegender Fehler C1311

Das COFF-Format kann "Var" mit der Anzahl Byte(s) einer Adresse nicht statisch initialisieren

Eine Adresse, deren Wert zum Zeitpunkt der Kompilierung nicht bekannt ist, kann nicht statisch einer Variablen zugewiesen werden, dessen Typ Speicher mit weniger als vier Bytes ist.

Dieser Fehler kann auftreten, auf den Code, die C++-gültig.

Das folgende Beispiel zeigt eine Bedingung, die C1311 verursachen können.

```
char c = (char)"Hello, world";   // C1311
char *d = (char*)"Hello, world";   // OK
```