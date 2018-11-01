---
title: Compilerfehler C2410
ms.date: 11/04/2016
f1_keywords:
- C2410
helpviewer_keywords:
- C2410
ms.assetid: b69b2de1-56f3-4ebc-8913-04ac57ffe8a1
ms.openlocfilehash: 8b01a2f7b9c55fb57c880df5033538f4e45f76b4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643689"
---
# <a name="compiler-error-c2410"></a>Compilerfehler C2410

'Bezeichner': Mehrdeutiger Elementname in 'Kontext'

Der Bezeichner ist ein Mitglied von mehr als eine Struktur oder Union in diesem Kontext.

Verwenden Sie einen Struktur oder Union-Spezifizierer für die Operanden, der den Fehler verursacht hat. Eine Struktur oder Union ist ein Bezeichner des Typs `struct` oder `union` (eine `typedef` Name oder eine Variable des gleichen Typs wie die Struktur oder Union, die auf die verwiesen wird). Der Bezeichner muss der linke Operand des der ersten Objektmember-auswahloperators (.) mit der Operand sein.