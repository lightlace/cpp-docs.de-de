---
title: Mathematischer Fehler M6108
ms.date: 11/04/2016
f1_keywords:
- M6108
helpviewer_keywords:
- M6108
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
ms.openlocfilehash: d60e9b6284c79828fda1f7af542fcf197f189ad0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50451011"
---
# <a name="math-error-m6108"></a>Mathematischer Fehler M6108

Quadratwurzel

Der Operand in einem Vorgang Quadratwurzel war negativ.

Das Programm mit Exitcode 136 wird beendet.

> [!NOTE]
>  Die `sqrt` Funktion in der C-Laufzeitbibliothek und die FORTRAN-Funktion **"SQRT"** Generieren dieser Fehler nicht. Das C `sqrt` Funktion überprüft das Argument vor dem Ausführen des Vorgangs und gibt einen Fehlerwert zurück, wenn der Operand negativ ist. Die FORTRAN **"SQRT"** Funktion generiert die Domänenfehler [M6201](../../error-messages/tool-errors/math-error-m6201.md) anstelle dieses Fehlers.