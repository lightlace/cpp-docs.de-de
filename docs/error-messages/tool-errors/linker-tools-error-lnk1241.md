---
title: Linkertoolfehler Lnk1241 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1241
dev_langs:
- C++
helpviewer_keywords:
- LNK1241
ms.assetid: 7b8b52eb-0231-4521-b52a-2bce8d3e8956
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e4c11a97dd99515ff7623b77ff31de5fb8577b5d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040621"
---
# <a name="linker-tools-error-lnk1241"></a>Linkertoolfehler LNK1241

Ressourcendatei "Ressourcendatei" bereits angegeben

Dieser Fehler wird generiert, wenn das Ausführen **Cvtres** manuell über die Befehlszeile und anschließende übergeben der resultierenden OBJ-Datei an den Linker darüber hinaus in weiteren RES-Dateien.

Um mehrere RES-Dateien anzugeben, übergeben sie alle in der Linker als RES-Dateien, nicht aus in OBJ-Dateien erstellt, indem **Cvtres**.