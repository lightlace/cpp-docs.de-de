---
title: Projektbuildfehler prj0030 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0030
dev_langs:
- C++
helpviewer_keywords:
- PRJ0030
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 964fedd40f577a8b337c4ad0c20ba80d33ed2a23
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099902"
---
# <a name="project-build-error-prj0030"></a>Projektbuildfehler PRJ0030

Makrofehler-Erweiterung. Werten Sie Überprüfungsrekursion überschritt 32 Ebenen für $(Makro) ein.

Dieser Fehler wird durch die Rekursion in Makros verursacht. Wenn Sie festlegen, z. B. die **Zwischenverzeichnis** Eigenschaft (finden Sie unter [Eigenschaftenseite "Allgemein" (Projekt)](../../ide/general-property-page-project.md)) auf $(intdir), werden Sie Rekursion haben.

Um diesen Fehler zu beheben, ist nicht definiert, Makros oder Eigenschaften in Bezug auf die Makros, die sie verwendet werden, um zu definieren.