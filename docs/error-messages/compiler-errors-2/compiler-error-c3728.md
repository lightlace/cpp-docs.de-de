---
title: Compilerfehler C3728 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3728
dev_langs:
- C++
helpviewer_keywords:
- C3728
ms.assetid: 6b510cb1-887f-4fcd-9a1f-3bb720417ed1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e412824bd2afdadfc21d71b73f38eb8ba5ace82d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46108416"
---
# <a name="compiler-error-c3728"></a>Compilerfehler C3728

'Ereignis': Ereignis hat keine Raise-Methode

Metadaten erstellt mit einer anderen Sprache, wie z. B. c#, die kein Ereignis zulässt, von außerhalb der Klasse ausgelöst werden, in dem sie definiert wurde, enthalten war die [#using](../../preprocessor/hash-using-directive-cpp.md) Richtlinie und eine CLR-Programmierung, es wurde versucht, mit Visual C++-Programm Auslösen des Ereignisses an.

Zum Auslösen eines Ereignisses in einem Programm, das in einer Sprache wie c# entwickelt muss die Klasse, die das Ereignis enthält auch eine öffentliche Methode definieren, die das Ereignis auslöst.