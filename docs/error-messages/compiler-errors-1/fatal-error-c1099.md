---
title: Schwerwiegender Fehler C1099
ms.date: 11/04/2016
f1_keywords:
- C1099
helpviewer_keywords:
- C1099
ms.assetid: c050b074-a06a-4026-9e10-569029cc0739
ms.openlocfilehash: 673a54f705a8ff46ad94167a4458ab538df69c88
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387005"
---
# <a name="fatal-error-c1099"></a>Schwerwiegender Fehler C1099

Kompilierungsabbruch durch Engine für Bearbeiten und Fortfahren

Durch Bearbeiten und Fortfahren wurde eine vorkompilierte Headerdatei in Vorbereitung für das Kompilieren von Codeänderungen geladen, aber nachfolgende Maßnahmen (z. B. Codeänderungen vor der vorkompilierten `#include` -Headeranweisung oder das Beenden des Debuggers) verhindern, dass die Kompilierung mit diesem Prozess von „Bearbeiten und Fortfahren“ beendet wird. Sie müssen keine Maßnahmen ergreifen, um diesen Fehler zu beheben.