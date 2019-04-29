---
title: Schwerwiegender Fehler C1061
ms.date: 11/04/2016
f1_keywords:
- C1061
helpviewer_keywords:
- C1061
ms.assetid: 9366c0bc-96e0-4967-aa7d-4ebf098de806
ms.openlocfilehash: 1733a13e697af775653609ddfcc22f7297dad240
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363959"
---
# <a name="fatal-error-c1061"></a>Schwerwiegender Fehler C1061

Compilerlimit: Blöcke zu tief geschachtelt

Die Schachtelungstiefe für Codeblöcke überschreitet die maximale Anzahl von 128 Ebenen. Hierbei handelt es sich um einen festen Grenzwert im Compiler im 32-Bit- und 64-Bit-Toolsatz von C und C++. Alle Verhaltensweisen, durch die ein Gültigkeitsbereich oder ein Block erstellt wird, können die Anzahl der Schachtelungsebenen erhöhen. So können z. B. Namespaces, Direktiven, Präprozessorerweiterungen, Vorlagenerweiterungen, Ausnahmebehandlungen, Schleifenkonstrukte und elseif-Klauseln zur Erhöhung der vom Compiler erkannten Schachtelungsebene beitragen.

Um diesen Fehler zu beheben, müssen Sie den Code umgestalten. In jedem Fall ist tief geschachtelter Code nur schwer nachzuvollziehen. Eine Reduzierung der Schachtelungsebenen des Codes verbessert die Codequalität und vereinfacht die Verwaltung. Gliedern Sie daher tief geschachtelten Code in Funktionen auf, die in ihrem ursprünglichen Kontext aufgerufen werden. Beschränken Sie die Anzahl von Schleifen oder verketteten elseif-Klauseln innerhalb eines Blocks.