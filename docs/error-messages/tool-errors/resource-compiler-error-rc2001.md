---
title: 'Ressourcencompiler: Fehler RC2001'
ms.date: 11/04/2016
f1_keywords:
- RC2001
helpviewer_keywords:
- RC2001
ms.assetid: 92bfb4c0-1879-4606-bb9f-ef7368707b4a
ms.openlocfilehash: f4755e04a744d94636b4b37aaf727e0d733008ef
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62346690"
---
# <a name="resource-compiler-error-rc2001"></a>Ressourcencompiler: Fehler RC2001

Zeilenvorschub in Konstante.

Eine Zeichenfolgenkonstante wurde in einer zweiten Zeile ohne einen umgekehrten Schrägstrich fortgesetzt (**\\**) oder geschlossen, und öffnen die doppelten Anführungszeichen (**"**).

Führen Sie eine der folgenden Schritte aus, um eine Zeichenfolgenkonstante, die in zwei Zeilen in der Quelldatei zu unterbrechen:

- Das Ende der ersten Zeile mit dem Zeilenfortsetzungszeichen, einen umgekehrten Schrägstrich.

- Schließen Sie die Zeichenfolge in der ersten Zeile mit einem doppelten Anführungszeichen, und öffnen Sie ein weiteres Anführungszeichen der Zeichenfolge in der nächsten Zeile.

Es ist nicht ausreichend, um die erste Zeile \n, die-Escapesequenz für das Einbetten von einem Newline-Zeichen in eine Zeichenfolgenkonstante enden.