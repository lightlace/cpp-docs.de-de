---
title: Schwerwiegender Fehler C1905 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1905
dev_langs:
- C++
helpviewer_keywords:
- C1905
ms.assetid: fefc6769-477f-45a2-9878-6f0a5f42472c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 263bf0ff63d71f381e68ea33b294abd423f59bf4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058444"
---
# <a name="fatal-error-c1905"></a>Schwerwiegender Fehler C1905

Front-End und Back-End sind nicht kompatibel (müssen auf denselben Prozessor ausgerichtet sein).

Dieser Fehler tritt auf, wenn eine OBJ-Datei wird von einem Compiler-Front-End (C1.dll) einen Prozessor, z. B. X86, ARM oder X64 generiert, aber durch ein Back-End (C2.dll), die einen anderen Zielprozessor gelesen wird.

Stellen Sie zur Behebung dieses Problems sicher, dass Front-End und Back-End kompatibel sind. Dies ist die Standardeinstellung für Projekte, die in Visual Studio erstellt wurden. Dieser Fehler kann auftreten, wenn Sie die Projektdatei bearbeitet und dabei verschiedene Pfade zu den Compilertools verwendet haben. Wenn Sie den Pfad für die Compilertools nicht ausdrücklich festgelegt haben, kann dieser Fehler auftreten, wenn die Visual Studio-Installation beschädigt ist. Beispielsweise können Sie Compiler-DLL-Dateien von einem Speicherort zu einem anderen kopiert haben. Verwendung **Programme und Funktionen** in der Windows-Systemsteuerung zu reparieren oder installieren Sie Visual Studio.