---
title: Schwerwiegender Fehler C1311
ms.date: 11/04/2016
f1_keywords:
- C1311
helpviewer_keywords:
- C1311
ms.assetid: 6590a06c-ce9d-4f17-8f62-c809343143b8
ms.openlocfilehash: ba2b797c9bf521533e7c2ccff8d358b6216d392f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62266465"
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