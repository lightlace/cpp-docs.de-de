---
title: Mathematischer Fehler M6108 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- M6108
dev_langs:
- C++
helpviewer_keywords:
- M6108
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1624a89b472733b4adb5563c8ba52e0b03dcaa2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46048616"
---
# <a name="math-error-m6108"></a>Mathematischer Fehler M6108

Quadratwurzel

Der Operand in einem Vorgang Quadratwurzel war negativ.

Das Programm mit Exitcode 136 wird beendet.

> [!NOTE]
>  Die `sqrt` Funktion in der C-Laufzeitbibliothek und die FORTRAN-Funktion **"SQRT"** Generieren dieser Fehler nicht. Das C `sqrt` Funktion überprüft das Argument vor dem Ausführen des Vorgangs und gibt einen Fehlerwert zurück, wenn der Operand negativ ist. Die FORTRAN **"SQRT"** Funktion generiert die Domänenfehler [M6201](../../error-messages/tool-errors/math-error-m6201.md) anstelle dieses Fehlers.