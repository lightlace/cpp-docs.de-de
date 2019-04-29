---
title: Compilerfehler C3728
ms.date: 11/04/2016
f1_keywords:
- C3728
helpviewer_keywords:
- C3728
ms.assetid: 6b510cb1-887f-4fcd-9a1f-3bb720417ed1
ms.openlocfilehash: 68aa23843b0470f15f409b6f3b58624f979ccfae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328106"
---
# <a name="compiler-error-c3728"></a>Compilerfehler C3728

'Ereignis': Ereignis hat keine Raise-Methode

Metadaten erstellt mit einer anderen Sprache, wie z. B. c#, die kein Ereignis zulässt, von außerhalb der Klasse ausgelöst werden, in dem sie definiert wurde, enthalten war die [#using](../../preprocessor/hash-using-directive-cpp.md) Richtlinie und eine CLR-Programmierung, es wurde versucht, mit Visual C++-Programm Auslösen des Ereignisses an.

Zum Auslösen eines Ereignisses in einem Programm, das in einer Sprache wie c# entwickelt muss die Klasse, die das Ereignis enthält auch eine öffentliche Methode definieren, die das Ereignis auslöst.