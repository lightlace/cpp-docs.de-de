---
title: 'Ressourcencompiler: Fehler RC2144 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2144
dev_langs:
- C++
helpviewer_keywords:
- RC2144
ms.assetid: 1b3ff39a-92cd-4a04-b1a3-b1fa6a805813
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 62f9eb2b25919a2336c36a459ef41eece447a490
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080492"
---
# <a name="resource-compiler-error-rc2144"></a>Ressourcencompiler: Fehler RC2144

Primäre Sprach-ID ist keine Zahl

Primäre Sprach-ID muss eine hexadezimale Sprachen-ID sein. Finden Sie unter [Sprach- und Länder-/Regionszeichenfolgen](../../c-runtime-library/locale-names-languages-and-country-region-strings.md) in die *Run-Time Library Reference* eine Liste der gültigen Sprach-IDs.

Dieser Fehler kann auch auftreten, wenn Sie Ressourcen hinzugefügt und aus der.RC-Datei mithilfe des Tools gelöscht haben. Um dieses Problem zu beheben, öffnen Sie die.RC-Datei in einem Texteditor und bereinigen Sie manuell alle nicht verwendeten Ressourcen.