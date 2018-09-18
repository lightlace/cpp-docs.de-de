---
title: Compilerfehler C3398 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3398
dev_langs:
- C++
helpviewer_keywords:
- C3398
ms.assetid: 26f8c8a4-526f-415b-8047-155c5cd4f180
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 336494ea9581289efd9a41e604a28984125ae61a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018131"
---
# <a name="compiler-error-c3398"></a>Compilerfehler C3398

'Operator': Konvertierung von 'function_signature' in 'function_pointer' nicht möglich. Der Quellausdruck muss ein Funktionssymbol sein.

Wenn die [__clrcall](../../cpp/clrcall.md) -Aufrufkonvention bei der Kompilierung mit **/clr**nicht angegeben ist, generiert der Compiler zwei Einstiegspunkte (Adressen) für jede Funktion, einen systemeigener Einstiegspunkt und einen verwalteten Einstiegspunkt.

Standardmäßig gibt der Compiler den systemeigenen Einstiegspunkt zurück, aber es gibt einige Fälle, in denen der verwaltete Einstiegspunkt erwünscht ist (z. B. beim Zuweisen der Adresse zu einem `__clrcall` -Funktionszeiger). Damit der Compiler den verwalteten Einstiegspunkt in einer Zuordnung zuverlässig auswählen kann, muss die rechte Seite ein Funktionssymbol sein.